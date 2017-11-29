---
title: Zaman uyumsuz derinlemesine
description: "Ne zaman uyumsuz g/Ç-bağlı ve CPU bağımlı kod yazma basit .NET görev tabanlı zaman uyumsuz modelini kullanarak olduğunu öğrenin."
keywords: .NET, .NET core, .NET standart
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 1e38f9d9-8f84-46ee-a15f-199aec4f2e34
ms.openlocfilehash: 4591ec591d9aba41e303bacdb6ed94c6663376be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="async-in-depth"></a><span data-ttu-id="17a4b-104">Zaman uyumsuz derinlemesine</span><span class="sxs-lookup"><span data-stu-id="17a4b-104">Async in depth</span></span>

<span data-ttu-id="17a4b-105">G/ç ve CPU sınır yazmayı zaman uyumsuz basit .NET görev tabanlı zaman uyumsuz modelini kullanarak kodudur.</span><span class="sxs-lookup"><span data-stu-id="17a4b-105">Writing I/O- and CPU-bound asynchronous code is straightforward using the .NET Task-based async model.</span></span> <span data-ttu-id="17a4b-106">Model tarafından sunulan `Task` ve `Task<T>` türleri ve `async` ve `await` C# ve Visual Basic anahtar sözcükleri.</span><span class="sxs-lookup"><span data-stu-id="17a4b-106">The model is exposed by the `Task` and `Task<T>` types and the `async` and `await` keywords in C# and Visual Basic.</span></span> <span data-ttu-id="17a4b-107">(Dile özgü kaynaklar içinde bulunan [Ayrıca bkz.](#see-also) bölümüne.) Bu makalede .NET zaman uyumsuz kullanılmasını açıklar ve perde arkasında kullanılan zaman uyumsuz framework bir anlayış sağlar.</span><span class="sxs-lookup"><span data-stu-id="17a4b-107">(Language-specific resources are found in the [See also](#see-also) section.) This article explains how to use .NET async and provides insight into the async framework used under the covers.</span></span>

## <a name="task-and-tasklttgt"></a><span data-ttu-id="17a4b-108">Görev ve görev&lt;T&gt;</span><span class="sxs-lookup"><span data-stu-id="17a4b-108">Task and Task&lt;T&gt;</span></span>

<span data-ttu-id="17a4b-109">Görevlerdir olarak bilinen uygulamak için kullanılan yapılar [, Promise modeli eşzamanlılık](https://en.wikipedia.org/wiki/Futures_and_promises).</span><span class="sxs-lookup"><span data-stu-id="17a4b-109">Tasks are constructs used to implement what is known as the [Promise Model of Concurrency](https://en.wikipedia.org/wiki/Futures_and_promises).</span></span>  <span data-ttu-id="17a4b-110">Kısacası, bunlar sonraki bir noktada, "iş promise" tamamlanacak promise temiz bir API ile birlikte koordine imkan sağlar.</span><span class="sxs-lookup"><span data-stu-id="17a4b-110">In short, they offer you a "promise" that work will be completed at a later point, letting you coordinate with the promise with a clean API.</span></span>

*   <span data-ttu-id="17a4b-111">`Task`bir değer döndürmüyor tek bir işlemde temsil eder.</span><span class="sxs-lookup"><span data-stu-id="17a4b-111">`Task` represents a single operation which does not return a value.</span></span>
*   <span data-ttu-id="17a4b-112">`Task<T>`türünde bir değer döndüren tek bir işlemi temsil eden `T`.</span><span class="sxs-lookup"><span data-stu-id="17a4b-112">`Task<T>` represents a single operation which returns a value of type `T`.</span></span>

<span data-ttu-id="17a4b-113">Zaman uyumsuz olarak gerçekleştiği iş soyutlamalar görevler hakkında neden önemlidir ve *değil* iş parçacığı üzerinde bir Özet.</span><span class="sxs-lookup"><span data-stu-id="17a4b-113">It’s important to reason about tasks as abstractions of work happening asynchronously, and *not* an abstraction over threading.</span></span> <span data-ttu-id="17a4b-114">Varsayılan olarak, işletim sistemine uygun şekilde geçerli iş parçacığı ve temsilci iş görevleri yürütün.</span><span class="sxs-lookup"><span data-stu-id="17a4b-114">By default, tasks execute on the current thread and delegate work to the Operating System, as appropriate.</span></span> <span data-ttu-id="17a4b-115">İsteğe bağlı olarak, görevleri açıkça ayrı bir iş parçacığı çalıştırmayı istenebilir `Task.Run` API.</span><span class="sxs-lookup"><span data-stu-id="17a4b-115">Optionally, tasks can be explicitly requested to run on a separate thread via the `Task.Run` API.</span></span>

<span data-ttu-id="17a4b-116">Görevleri izleme, üzerinde bekleyen ve sonuç değeri erişmek için bir API Protokolü kullanıma (durumunda `Task<T>`) bir görev.</span><span class="sxs-lookup"><span data-stu-id="17a4b-116">Tasks expose an API protocol for monitoring, waiting upon and accessing the result value (in the case of `Task<T>`) of a task.</span></span> <span data-ttu-id="17a4b-117">Dil Tümleştirmesi ile `await` anahtar sözcüğü, görevler kullanma için üst düzey bir Özet sağlar.</span><span class="sxs-lookup"><span data-stu-id="17a4b-117">Language integration, with the `await` keyword, provides a higher-level abstraction for using tasks.</span></span> 

<span data-ttu-id="17a4b-118">Kullanarak `await` görev yapılana kadar denetim çağırıcısına sağlayan tarafından bir görev çalışırken yararlı işlerini yapmak için uygulama veya hizmet sağlar.</span><span class="sxs-lookup"><span data-stu-id="17a4b-118">Using `await` allows your application or service to perform useful work while a task is running by yielding control to its caller until the task is done.</span></span> <span data-ttu-id="17a4b-119">Geri aramalar veya görevi tamamlandıktan sonra yürütmeye devam etmek için olayları yararlanmayı kodunuzu gerekmez.</span><span class="sxs-lookup"><span data-stu-id="17a4b-119">Your code does not need to rely on callbacks or events to continue execution after the task has been completed.</span></span> <span data-ttu-id="17a4b-120">Dili ve görev API tümleştirme yapar, sizin için.</span><span class="sxs-lookup"><span data-stu-id="17a4b-120">The language and task API integration does that for you.</span></span> <span data-ttu-id="17a4b-121">Kullanıyorsanız, `Task<T>`, `await` anahtar sözcüğü ayrıca "kaydırma" Görev tamamlandığında, döndürülen değer.</span><span class="sxs-lookup"><span data-stu-id="17a4b-121">If you’re using `Task<T>`, the `await` keyword will additionally "unwrap" the value returned when the Task is complete.</span></span>  <span data-ttu-id="17a4b-122">Bunun nasıl çalıştığı ayrıntılarını daha aşağıda açıklanmıştır.</span><span class="sxs-lookup"><span data-stu-id="17a4b-122">The details of how this works are explained further below.</span></span>

<span data-ttu-id="17a4b-123">Görevleri ve onlarla etkileşime farklı yolları hakkında daha fazla bilgiyi [görev tabanlı zaman uyumsuz desen (TAP)](~/docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) konu.</span><span class="sxs-lookup"><span data-stu-id="17a4b-123">You can learn more about tasks and the different ways to interact with them in the [Task-based Asynchronous Pattern (TAP)](~/docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) topic.</span></span>

## <a name="deeper-dive-into-tasks-for-an-io-bound-operation"></a><span data-ttu-id="17a4b-124">Bir g/Ç-bağlama işlemi için görevler halinde daha derin Dalış</span><span class="sxs-lookup"><span data-stu-id="17a4b-124">Deeper Dive into Tasks for an I/O-Bound Operation</span></span>

<span data-ttu-id="17a4b-125">Aşağıdaki bölümde tipik zaman uyumsuz g/ç çağrısı ile neler 10.000 kaplama alanı görünümü açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="17a4b-125">The following section describes a 10,000 foot view of what happens with a typical async I/O call.</span></span> <span data-ttu-id="17a4b-126">Birkaç örnek ile başlayalım.</span><span class="sxs-lookup"><span data-stu-id="17a4b-126">Let's start with a couple examples.</span></span>

<span data-ttu-id="17a4b-127">İlk örnek bir zaman uyumsuz yöntemini çağırır ve, henüz tamamlamak büyük olasılıkla etkin bir görev döndürür.</span><span class="sxs-lookup"><span data-stu-id="17a4b-127">The first example calls an async method and returns an active task, likely yet to complete.</span></span>

```csharp
public Task<string> GetHtmlAsync()
{
    // Execution is synchronous here
    var client = new HttpClient();
    
    return client.GetStringAsync("http://www.dotnetfoundation.org");
}
```

<span data-ttu-id="17a4b-128">İkinci örnek kullanımını ekler `async` ve `await` görev üzerinde çalışması için anahtar sözcükler.</span><span class="sxs-lookup"><span data-stu-id="17a4b-128">The second example adds the use of the `async` and `await` keywords to operate on the task.</span></span>

```csharp
public async Task<string> GetFirstCharactersCountAsync(string url, int count)
{
    // Execution is synchronous here
    var client = new HttpClient();
    
    // Execution of GetFirstCharactersCountAsync() is yielded to the caller here
    // GetStringAsync returns a Task<string>, which is *awaited*
    var page = await client.GetStringAsync("http://www.dotnetfoundation.org");
    
    // Execution resumes when the client.GetStringAsync task completes,
    // becoming synchronous again.
    
    if (count > page.Length)
    {
        return page;
    }
    else
    {
        return page.Substring(0, count);
    }
}
```

<span data-ttu-id="17a4b-129">Çağrı `GetStringAsync()` çağrıları bu kadar düşük düzeyli .NET kitaplıkları (belki de diğer zaman uyumsuz yöntemleri çağırma) üzerinden ulaştığında bir yerel ağ kitaplığındaki bir P/Invoke birlikte çalışabilirlik çağrısı.</span><span class="sxs-lookup"><span data-stu-id="17a4b-129">The call to `GetStringAsync()` calls through lower-level .NET libraries (perhaps calling other async methods) until it reaches a P/Invoke interop call into a native networking library.</span></span> <span data-ttu-id="17a4b-130">Yerel Kitaplığı daha sonra sistem API çağrısını çağırabilir (gibi `write()` Linux üzerinde bir yuva için).</span><span class="sxs-lookup"><span data-stu-id="17a4b-130">The native library may subsequently call into a System API call (such as `write()` to a socket on Linux).</span></span> <span data-ttu-id="17a4b-131">Yerel ve yönetilen sınırında, büyük olasılıkla kullanarak bir görev nesnesi oluşturulacak [TaskCompletionSource](xref:System.Threading.Tasks.TaskCompletionSource%601.SetResult(%600)).</span><span class="sxs-lookup"><span data-stu-id="17a4b-131">A task object will be created at the native/managed boundary, possibly using [TaskCompletionSource](xref:System.Threading.Tasks.TaskCompletionSource%601.SetResult(%600)).</span></span> <span data-ttu-id="17a4b-132">Görev nesnesi olması katmanları aktarılabilir, büyük olasılıkla üzerinde çalıştırılan veya doğrudan döndürülen, sonunda ilk yapana.</span><span class="sxs-lookup"><span data-stu-id="17a4b-132">The task object will be passed up through the layers, possibly operated on or directly returned, eventually returned to the initial caller.</span></span> 

<span data-ttu-id="17a4b-133">İkinci yukarıdaki örnekte, bir `Task<T>` nesnesi, gelen döndürülecek `GetStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="17a4b-133">In the second example above, a `Task<T>` object will be returned from `GetStringAsync`.</span></span> <span data-ttu-id="17a4b-134">Kullanımını `await` anahtar sözcüğü bir yeni oluşturulan görev nesnesi döndürmek yöntemin neden olur.</span><span class="sxs-lookup"><span data-stu-id="17a4b-134">The use of the `await` keyword causes the method to return a newly created task object.</span></span> <span data-ttu-id="17a4b-135">Denetim bu konumda bulunan çağırana döndürür `GetFirstCharactersCountAsync` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="17a4b-135">Control returns to the caller from this location in the `GetFirstCharactersCountAsync` method.</span></span> <span data-ttu-id="17a4b-136">Özellikleri ve yöntemleri [görev&lt;T&gt; ](xref:System.Threading.Tasks.Task%601) etkinleştir arayanlar GetFirstCharactersCountAsync kalan kodda çalıştırıldığında tamamlayacak görev ilerlemesini izlemek için nesne.</span><span class="sxs-lookup"><span data-stu-id="17a4b-136">The methods and properties of the [Task&lt;T&gt;](xref:System.Threading.Tasks.Task%601) object enable callers to monitor the progress of the task, which will complete when the remaining code in GetFirstCharactersCountAsync has executed.</span></span>

<span data-ttu-id="17a4b-137">Sistem API çağrısı sonra isteği şimdi çekirdek alanında ağ alt sisteminin yolu işletim sisteminin yapıyor (gibi `/net` Linux Çekirdeği'nde).</span><span class="sxs-lookup"><span data-stu-id="17a4b-137">After the System API call, the request is now in kernel space, making its way to the networking subsystem of the OS (such as `/net` in the Linux Kernel).</span></span>  <span data-ttu-id="17a4b-138">İşletim sistemi ağ isteği burada işleyecek *zaman uyumsuz olarak*.</span><span class="sxs-lookup"><span data-stu-id="17a4b-138">Here the OS will handle the networking request *asynchronously*.</span></span>  <span data-ttu-id="17a4b-139">Ayrıntılar kullanılan işletim sistemi bağlı olarak farklı olabilir (aygıt sürücüsü araması çalışma zamanına gönderilen sinyal olarak zamanlanmış olabilir veya bir aygıt sürücüsü çağrı yapılır ve *sonra* geri gönderilen sinyal), ancak çalışma zamanı sonunda bildirilir Ağ isteği devam ediyor.</span><span class="sxs-lookup"><span data-stu-id="17a4b-139">Details may be different depending on the OS used (the device driver call may be scheduled as a signal sent back to the runtime, or a device driver call may be made and *then* a signal sent back), but eventually the runtime will be informed that the networking request is in progress.</span></span>  <span data-ttu-id="17a4b-140">Şu anda aygıt sürücüsü için iş ya da zamanlanan, devam eden veya zaten tamamlandı (istek çıkışı "kablo üzerinden" zaten) - ancak bu tüm gerçekleştiği zaman uyumsuz olarak olduğundan, aygıt sürücüsünü hemen başka bir şey kaldırabilir mi olur!</span><span class="sxs-lookup"><span data-stu-id="17a4b-140">At this time, the work for the device driver will either be scheduled, in-progress, or already finished (the request is already out "over the wire") - but because this is all happening asynchronously, the device driver is able to immediately handle something else!</span></span>

<span data-ttu-id="17a4b-141">Örneğin, Windows işletim Sisteminin iş parçacığı ağ aygıt sürücüsü için bir çağrı yapar ve ağ üzerinden bir kesme istek Paketi'ni (IRP) işlemi gerçekleştirmek için bu işlemi temsil eden ister.</span><span class="sxs-lookup"><span data-stu-id="17a4b-141">For example, in Windows an OS thread makes a call to the network device driver and asks it to perform the networking operation via an Interrupt Request Packet (IRP) which represents the operation.</span></span>  <span data-ttu-id="17a4b-142">Aygıt sürücüsü IRP alır, ağa çağrı yapar, IRP "bekliyor" olarak işaretler ve işletim sistemi geri döndürür.</span><span class="sxs-lookup"><span data-stu-id="17a4b-142">The device driver receives the IRP, makes the call to the network, marks the IRP as "pending", and returns back to the OS.</span></span>  <span data-ttu-id="17a4b-143">IRP "bekliyor" işletim sistemi iş parçacığı şimdi bildiği için bu proje için yapmak için daha fazla iş yok ve "geri diğer işlemleri gerçekleştirmesi için kullanılabilmesi için böylece döndürür".</span><span class="sxs-lookup"><span data-stu-id="17a4b-143">Because the OS thread now knows that the IRP is "pending", it doesn't have any more work to do for this job and "returns" back so that it can be used to perform other work.</span></span>

<span data-ttu-id="17a4b-144">İstek yerine getirilir ve veriler geri aygıt sürücüsü aracılığıyla gelir, bir kesme alınan yeni verileri CPU size bildirir.</span><span class="sxs-lookup"><span data-stu-id="17a4b-144">When the request is fulfilled and data comes back through the device driver, it notifies the CPU of new data received via an interrupt.</span></span>  <span data-ttu-id="17a4b-145">Bu kesme nasıl ele, işletim sistemi bağlı olarak farklılık gösterir, ancak sistem birlikte çalışabilirlik çağrısı ulaşana kadar sonunda veri işletim sistemi geçirilecektir (örneğin, Linux bir kesme işleyicisi altındaki işletim sistemi veri iletmek için IRQ yarısı zamanlar  zaman uyumsuz olarak).</span><span class="sxs-lookup"><span data-stu-id="17a4b-145">How this interrupt gets handled will vary depending on the OS, but eventually the data will be passed through the OS until it reaches a system interop call (for example, in Linux an interrupt handler will schedule the bottom half of the IRQ to pass the data up through the OS asynchronously).</span></span>  <span data-ttu-id="17a4b-146">Not Bu *de* zaman uyumsuz olarak olur!</span><span class="sxs-lookup"><span data-stu-id="17a4b-146">Note that this *also* happens asynchronously!</span></span>  <span data-ttu-id="17a4b-147">Sonuç sonraki kullanılabilir iş parçacığının mümkün olduğu kadar sıraya async yöntemi yürütebilir ve "Tamamlanan görevin sonucu kaydırma".</span><span class="sxs-lookup"><span data-stu-id="17a4b-147">The result is queued up until the next available thread is able execute the async method and "unwrap" the result of the completed task.</span></span>

<span data-ttu-id="17a4b-148">Tüm bu işlem boyunca, bir anahtar takeaway olan **hiçbir iş parçacığı görevi çalıştırmak için adanmış**.</span><span class="sxs-lookup"><span data-stu-id="17a4b-148">Throughout this entire process, a key takeaway is that **no thread is dedicated to running the task**.</span></span>  <span data-ttu-id="17a4b-149">İş bazı içerik içinde yürütülmesi rağmen (diğer bir deyişle, işletim sistemi bir aygıt sürücüsü veri iletmek için bir kesme yanıt mevcut ve), için adanmış iş parçacığı yok *bekleyen* geri dönmeniz istekten alınan veriler için.</span><span class="sxs-lookup"><span data-stu-id="17a4b-149">Although work is executed in some context (that is, the OS does have to pass data to a device driver and respond to an interrupt), there is no thread dedicated to *waiting* for data from the request to come back.</span></span>  <span data-ttu-id="17a4b-150">Bu sistemin bazı g/ç arama tamamlanması bekleniyor yerine iş çok daha büyük bir birim işlemesini sağlar.</span><span class="sxs-lookup"><span data-stu-id="17a4b-150">This allows the system to handle a much larger volume of work rather than waiting for some I/O call to finish.</span></span>

<span data-ttu-id="17a4b-151">Yukarıdaki çok uzun duvar saati süresi cinsinden ölçülen yapılması çalışmanın gibi görünse de, bu, gerçek g/ç işlerini gerçekleştirmek için gereken süreyi karşılaştırıldığında miniscule olur.</span><span class="sxs-lookup"><span data-stu-id="17a4b-151">Although the above may seem like a lot of work to be done, when measured in terms of wall clock time, it’s miniscule compared to the time it takes to do the actual I/O work.</span></span> <span data-ttu-id="17a4b-152">Ancak hiç kesin böyle bir çağrı için olası bir zaman çizelgesi şuna benzer:</span><span class="sxs-lookup"><span data-stu-id="17a4b-152">Although not at all precise, a potential timeline for such a call would look like this:</span></span>

<span data-ttu-id="17a4b-153">0-1————————————————————————————————————————————————–2-3</span><span class="sxs-lookup"><span data-stu-id="17a4b-153">0-1————————————————————————————————————————————————–2-3</span></span>

*   <span data-ttu-id="17a4b-154">Harcanan zaman noktalarından `0` için `1` bir zaman uyumsuz yöntem çağırıcısına denetim verir kadar gereken her şey vardır.</span><span class="sxs-lookup"><span data-stu-id="17a4b-154">Time spent from points `0` to `1` is everything up until an async method yields control to its caller.</span></span>
*   <span data-ttu-id="17a4b-155">Harcanan zaman noktalarından `1` için `2` maliyet hiçbir CPU ile g/ç üzerinde harcanan zamanı.</span><span class="sxs-lookup"><span data-stu-id="17a4b-155">Time spent from points `1` to `2` is the time spent on I/O, with no CPU cost.</span></span>
*   <span data-ttu-id="17a4b-156">Son olarak, noktalarından harcanan zamanı `2` için `3` Denetim Arka (ve büyük olasılıkla bir değer), bu noktada, Yürütülüyor yeniden async yöntemi için geçirme.</span><span class="sxs-lookup"><span data-stu-id="17a4b-156">Finally, time spent from points `2` to `3` is passing control back (and potentially a value) to the async method, at which point it is executing again.</span></span>

### <a name="what-does-this-mean-for-a-server-scenario"></a><span data-ttu-id="17a4b-157">Bunun için sunucu senaryosu anlamı nedir?</span><span class="sxs-lookup"><span data-stu-id="17a4b-157">What does this mean for a server scenario?</span></span>

<span data-ttu-id="17a4b-158">Bu model, iyi bir tipik sunucu senaryosu iş yükü ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="17a4b-158">This model works well with a typical server scenario workload.</span></span>  <span data-ttu-id="17a4b-159">Tamamlanmamış görevler üzerinde engellemek üzere adanmış iş parçacığı olduğundan sunucu threadpool'u bir çok daha yüksek hacmi web istekleri servis edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="17a4b-159">Because there are no threads dedicated to blocking on unfinished tasks, the server threadpool can service a much higher volume of web requests.</span></span>

<span data-ttu-id="17a4b-160">İki sunucu göz önünde bulundurun: zaman uyumsuz kodu çalıştırır ve desteklemez.</span><span class="sxs-lookup"><span data-stu-id="17a4b-160">Consider two servers: one that runs async code, and one that does not.</span></span>  <span data-ttu-id="17a4b-161">Bu örneğin amacı doğrultusunda, her sunucu yalnızca hizmet istekleri için kullanılabilir 5 iş parçacığı yok.</span><span class="sxs-lookup"><span data-stu-id="17a4b-161">For the purpose of this example, each server only has 5 threads available to service requests.</span></span>  <span data-ttu-id="17a4b-162">Bu sayı imaginarily küçük ve yalnızca demonstrative bağlamında hizmet unutmayın.</span><span class="sxs-lookup"><span data-stu-id="17a4b-162">Note that these numbers are imaginarily small and serve only in a demonstrative context.</span></span>

<span data-ttu-id="17a4b-163">Her iki sunucuyu 6 eş zamanlı istekleri almak varsayalım.</span><span class="sxs-lookup"><span data-stu-id="17a4b-163">Assume both servers receive 6 concurrent requests.</span></span> <span data-ttu-id="17a4b-164">Her istek bir g/ç işlemi gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="17a4b-164">Each request performs an I/O operation.</span></span>  <span data-ttu-id="17a4b-165">Sunucu *olmadan* zaman uyumsuz koduna sahip 5 iş parçacığı bir g/Ç-bağlı iş tamamlandı ve yanıt yazılmış kadar 6 isteğini Sıraya alınacak.</span><span class="sxs-lookup"><span data-stu-id="17a4b-165">The server *without* async code has to queue up the 6th request until one of the 5 threads have finished the I/O-bound work and written a response.</span></span> <span data-ttu-id="17a4b-166">Sıranın uzun elde etmektir çünkü 20 istek geldiğinde noktada, aşağı, yavaş sunucu başlayabilir.</span><span class="sxs-lookup"><span data-stu-id="17a4b-166">At the point that the 20th request comes in, the server might start to slow down, because the queue is getting too long.</span></span>

<span data-ttu-id="17a4b-167">Sunucu *ile* üzerinde çalışan zaman uyumsuz kodu hala 6 isteği sıralarını ancak kullandığından `async` ve `await`, her iş parçacıklarını serbest yukarı g/Ç-bağlı iş başlatıldığında yerine bittiğinde.</span><span class="sxs-lookup"><span data-stu-id="17a4b-167">The server *with* async code running on it still queues up the 6th request, but because it uses `async` and `await`, each of its threads are freed up when the I/O-bound work starts, rather than when it finishes.</span></span>  <span data-ttu-id="17a4b-168">Gelen istekleri kadar küçük olacaktır zamanına göre 20 isteği sırada birlikte gelir. (Bu her şeyi hiç olup olmadığını), ve sunucu yavaşlaması olmaz.</span><span class="sxs-lookup"><span data-stu-id="17a4b-168">By the time the 20th request comes in, the queue for incoming requests will be far smaller (if it has anything in it at all), and the server won't slow down.</span></span>

<span data-ttu-id="17a4b-169">Bu contrived örnek olsa da, gerçek dünyadaki çok benzer bir şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="17a4b-169">Although this is a contrived example, it works in a very similar fashion in the real world.</span></span>  <span data-ttu-id="17a4b-170">Aslında, büyüklük kertesinde kullanarak daha fazla isteklerini işlemek için bir sunucu bekleyebilirsiniz `async` ve `await` her istek için bir iş parçacığı ayrılması, alan daha.</span><span class="sxs-lookup"><span data-stu-id="17a4b-170">In fact, you can expect a server to be able to handle an order of magnitude more requests using `async` and `await` than if it were dedicating a thread for each request it receives.</span></span>

### <a name="what-does-this-mean-for-client-scenario"></a><span data-ttu-id="17a4b-171">Bu ne istemci senaryo için anlama geliyor?</span><span class="sxs-lookup"><span data-stu-id="17a4b-171">What does this mean for client scenario?</span></span>

<span data-ttu-id="17a4b-172">Kullanmak için en büyük kazanç `async` ve `await` bir istemci için uygulama yanıt hızını artış olur.</span><span class="sxs-lookup"><span data-stu-id="17a4b-172">The biggest gain for using `async` and `await` for a client app is an increase in responsiveness.</span></span>  <span data-ttu-id="17a4b-173">Bir uygulama yanıt iş parçacığı oluşturma tarafından el ile yapabileceğiniz bir iş parçacığını oluşturma işlemi yalnızca kullanarak göre pahalı bir işlem olsa da `async` ve `await`.</span><span class="sxs-lookup"><span data-stu-id="17a4b-173">Although you can make an app responsive by spawning threads manually, the act of spawning a thread is an expensive operation relative to just using `async` and `await`.</span></span>  <span data-ttu-id="17a4b-174">Özellikle bir şey için taşınabilir oyun gibi burada g/ç kaygı kullanıcı Arabirimi iş parçacığı mümkün olduğunca az etkileyen çok önemlidir.</span><span class="sxs-lookup"><span data-stu-id="17a4b-174">Especially for something like a mobile game, impacting the UI thread as little as possible where I/O is concerned is crucial.</span></span>

<span data-ttu-id="17a4b-175">G/Ç-bağlı iş neredeyse hiçbir zaman CPU üzerinde harcadığı olduğundan daha da önemlisi, neredeyse hiç herhangi bir yararlı çalışmayı gerçekleştirmek için bir tüm CPU iş parçacığı ayrılması kötü bir kaynak kullanımını olacaktır.</span><span class="sxs-lookup"><span data-stu-id="17a4b-175">More importantly, because I/O-bound work spends virtually no time on the CPU, dedicating an entire CPU thread to perform barely any useful work would be a poor use of resources.</span></span>

<span data-ttu-id="17a4b-176">Ayrıca, (örneğin, bir kullanıcı Arabirimi güncelleştirme) kullanıcı Arabirimi iş parçacığı için iş gönderme ile çok basit olup `async` yöntemleri ve (örneğin, bir iş parçacığı temsilci çağırma) ek iş gerektirmez.</span><span class="sxs-lookup"><span data-stu-id="17a4b-176">Additionally, dispatching work to the UI thread (such as updating a UI) is very simple with `async` methods, and does not require extra work (such as calling a thread-safe delegate).</span></span>

## <a name="deeper-dive-into-task-and-taskt-for-a-cpu-bound-operation"></a><span data-ttu-id="17a4b-177">Derin Dalış görev ve görev<T> CPU bağımlı işlemi</span><span class="sxs-lookup"><span data-stu-id="17a4b-177">Deeper Dive into Task and Task<T> for a CPU-Bound Operation</span></span>

<span data-ttu-id="17a4b-178">CPU bağımlı `async` kodu g/Ç-sınırdan biraz farklıdır `async` kodu.</span><span class="sxs-lookup"><span data-stu-id="17a4b-178">CPU-bound `async` code is a bit different than I/O-bound `async` code.</span></span>  <span data-ttu-id="17a4b-179">İş CPU'da yapıldığından, hesaplama için bir iş parçacığı ayrılması geçici almak için yolu yoktur.</span><span class="sxs-lookup"><span data-stu-id="17a4b-179">Because the work is done on the CPU, there's no way to get around dedicating a thread to the computation.</span></span>  <span data-ttu-id="17a4b-180">Kullanımını `async` ve `await` bir arka plan ile etkileşim kurmak için temiz bir şekilde sizinle iş parçacığı ve zaman uyumsuz yöntem arayan yanıt verebilir durumda tutun sağlar.</span><span class="sxs-lookup"><span data-stu-id="17a4b-180">The use of `async` and `await` provides you with a clean way to interact with a background thread and keep the caller of the async method responsive.</span></span>  <span data-ttu-id="17a4b-181">Bu paylaşılan veriler için herhangi bir koruma sağlamaz unutmayın.</span><span class="sxs-lookup"><span data-stu-id="17a4b-181">Note that this does not provide any protection for shared data.</span></span>  <span data-ttu-id="17a4b-182">Paylaşılan veri kullanıyorsanız, uygun eşitleme stratejisi uygulamak gerekecektir.</span><span class="sxs-lookup"><span data-stu-id="17a4b-182">If you are using shared data, you will still need to apply an appropriate synchronization strategy.</span></span>

<span data-ttu-id="17a4b-183">CPU bağımlı zaman uyumsuz çağrı 10.000 kaplama alanı görünümünü şöyledir:</span><span class="sxs-lookup"><span data-stu-id="17a4b-183">Here's a 10,000 foot view of a CPU-bound async call:</span></span>

```csharp
public async Task<int> CalculateResult(InputData data)
{
    // This queues up the work on the threadpool.
    var expensiveResultTask = Task.Run(() => DoExpensiveCalculation(data));
    
    // Note that at this point, you can do some other work concurrently,
    // as CalculateResult() is still executing!
    
    // Execution of CalculateResult is yielded here!
    var result = await expensiveResultTask;
    
    return result;
}
```

<span data-ttu-id="17a4b-184">`CalculateResult()`çağrıldı iş parçacığı üzerinde yürütür.</span><span class="sxs-lookup"><span data-stu-id="17a4b-184">`CalculateResult()` executes on the thread it was called on.</span></span>  <span data-ttu-id="17a4b-185">Bunu çağırdığında `Task.Run`, pahalı CPU bağımlı işlemi kuyruklar `DoExpensiveCalculation()`, iş parçacığı havuzu üzerinde ve alan bir `Task<int>` işlemek.</span><span class="sxs-lookup"><span data-stu-id="17a4b-185">When it calls `Task.Run`, it queues the expensive CPU-bound operation, `DoExpensiveCalculation()`, on the thread pool and receives a `Task<int>` handle.</span></span>  <span data-ttu-id="17a4b-186">`DoExpensiveCalculation()`sonunda eşzamanlı olarak sonraki kullanılabilir iş parçacığı üzerinde başka bir CPU çekirdeği üzerinde büyük olasılıkla çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="17a4b-186">`DoExpensiveCalculation()` is eventually run concurrently on the next available thread, likely on another CPU core.</span></span>  <span data-ttu-id="17a4b-187">Eşzamanlı iş çalışırken yapmak mümkündür `DoExpensiveCalculation()` başka bir iş parçacığı üzerinde meşgul olduğundan çağrılan iş parçacığı `CalculateResult()` yürütülmeye devam.</span><span class="sxs-lookup"><span data-stu-id="17a4b-187">It's possible to do concurrent work while `DoExpensiveCalculation()` is busy on another thread, because the thread which called `CalculateResult()` is still executing.</span></span>

<span data-ttu-id="17a4b-188">Bir kez `await` karşılaşılırsa, yürütülmesi `CalculateResult()` sırasında geçerli iş parçacığı ile yapılacak diğer işleri izin vererek, arayana verdiğini `DoExpensiveCalculation()` bir sonuç fakat.</span><span class="sxs-lookup"><span data-stu-id="17a4b-188">Once `await` is encountered, the execution of `CalculateResult()` is yielded to its caller, allowing other work to be done with the current thread while `DoExpensiveCalculation()` is churning out a result.</span></span>  <span data-ttu-id="17a4b-189">Tamamlandıktan sonra sonuç ana iş parçacığında çalıştırmak için sıraya alındı.</span><span class="sxs-lookup"><span data-stu-id="17a4b-189">Once it has finished, the result is queued up to run on the main thread.</span></span>  <span data-ttu-id="17a4b-190">Sonuç olarak, ana iş parçacığı yürütülen döndürülecek `CalculateResult()`, bu noktada sonucu olacaktır `DoExpensiveCalculation()`.</span><span class="sxs-lookup"><span data-stu-id="17a4b-190">Eventually, the main thread will return to executing `CalculateResult()`, at which point it will have the result of `DoExpensiveCalculation()`.</span></span>

### <a name="why-does-async-help-here"></a><span data-ttu-id="17a4b-191">Neden zaman uyumsuz burada yardımcı olur?</span><span class="sxs-lookup"><span data-stu-id="17a4b-191">Why does async help here?</span></span>

<span data-ttu-id="17a4b-192">`async`ve `await` en iyi uygulamadır yönetme CPU bağımlı iş yanıtlama gerektiğinde şunlardır.</span><span class="sxs-lookup"><span data-stu-id="17a4b-192">`async` and `await` are the best practice managing CPU-bound work when you need responsiveness.</span></span> <span data-ttu-id="17a4b-193">Zaman uyumsuz CPU bağımlı iş ile kullanmak için birden çok desenleri vardır.</span><span class="sxs-lookup"><span data-stu-id="17a4b-193">There are multiple patterns for using async with CPU-bound work.</span></span> <span data-ttu-id="17a4b-194">Async kullanma için küçük bir maliyeti yoktur ve sıkı döngüler için önerilmez dikkate almak önemlidir.</span><span class="sxs-lookup"><span data-stu-id="17a4b-194">It's important to note that there is a small cost to using async and it's not recommended for tight loops.</span></span>  <span data-ttu-id="17a4b-195">Bu size kodunuzu bu yeni özellik geçici yazma biçimini belirlemek için hazır.</span><span class="sxs-lookup"><span data-stu-id="17a4b-195">It's up to you to determine how you write your code around this new capability.</span></span>

## <a name="see-also"></a><span data-ttu-id="17a4b-196">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="17a4b-196">See also</span></span>

<span data-ttu-id="17a4b-197">[C# zaman uyumsuz programlama](~/docs/csharp/async.md) </span><span class="sxs-lookup"><span data-stu-id="17a4b-197">[Asynchronous programming in C#](~/docs/csharp/async.md) </span></span>  
<span data-ttu-id="17a4b-198">[F # zaman uyumsuz programlama](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md) </span><span class="sxs-lookup"><span data-stu-id="17a4b-198">[Async Programming in F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md) </span></span>  
[<span data-ttu-id="17a4b-199">Zaman uyumsuz programlama ile Async ve Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17a4b-199">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/concepts/async/index.md)