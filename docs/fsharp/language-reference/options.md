---
title: "Seçenekler (F#)"
description: "Bir adlandırılmış değeri veya değişken türleri gerçek bir değer olduğunda var olmayabilir F # seçeneği kullanmayı öğrenin."
keywords: "Visual f #, f # işlevsel programlama"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a15b5cf1-9055-4481-918c-4c8a051b5829
ms.openlocfilehash: 537ba69aecc1ab489de63d67c5f9ff857afb4a28
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="options"></a><span data-ttu-id="06b6d-104">Seçenekler</span><span class="sxs-lookup"><span data-stu-id="06b6d-104">Options</span></span>

<span data-ttu-id="06b6d-105">Bir adlandırılmış değeri veya değişken için bir gerçek değer var olmayabilir F # seçenek türü kullanılır.</span><span class="sxs-lookup"><span data-stu-id="06b6d-105">The option type in F# is used when an actual value might not exist for a named value or variable.</span></span> <span data-ttu-id="06b6d-106">İsteğe bağlı bir temel alınan tür vardır ve bu türde bir değer tutabilir veya bir değere sahip olmayabilir.</span><span class="sxs-lookup"><span data-stu-id="06b6d-106">An option has an underlying type and can hold a value of that type, or it might not have a value.</span></span>

## <a name="remarks"></a><span data-ttu-id="06b6d-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="06b6d-107">Remarks</span></span>
<span data-ttu-id="06b6d-108">Aşağıdaki kod bir seçenek türü oluşturan bir işlev gösterir.</span><span class="sxs-lookup"><span data-stu-id="06b6d-108">The following code illustrates a function which generates an option type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

<span data-ttu-id="06b6d-109">Varsa görebileceğiniz gibi giriş `a` 0'dan büyük `Some(a)` oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="06b6d-109">As you can see, if the input `a` is greater than 0, `Some(a)` is generated.</span></span>  <span data-ttu-id="06b6d-110">Aksi takdirde `None` oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="06b6d-110">Otherwise, `None` is generated.</span></span>

<span data-ttu-id="06b6d-111">Değer `None` bir seçenek bir asıl değere sahip olmadığında kullanılır.</span><span class="sxs-lookup"><span data-stu-id="06b6d-111">The value `None` is used when an option does not have an actual value.</span></span> <span data-ttu-id="06b6d-112">Aksi takdirde, ifade `Some( ... )` bir değer seçeneği sunar.</span><span class="sxs-lookup"><span data-stu-id="06b6d-112">Otherwise, the expression `Some( ... )` gives the option a value.</span></span> <span data-ttu-id="06b6d-113">Değerleri `Some` ve `None` düzeni, olduğu gibi aşağıdaki işlevi eşleştirmelerinde yararlıdır `exists`, döndüren `true` seçeneği bir değeri varsa ve `false` mevcut değilse.</span><span class="sxs-lookup"><span data-stu-id="06b6d-113">The values `Some` and `None` are useful in pattern matching, as in the following function `exists`, which returns `true` if the option has a value and `false` if it does not.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a><span data-ttu-id="06b6d-114">Seçeneklerini kullanma</span><span class="sxs-lookup"><span data-stu-id="06b6d-114">Using Options</span></span>
<span data-ttu-id="06b6d-115">Bir arama eşleşen bir sonuç döndürmüyor olduğunda seçenekleri aşağıdaki kodda gösterildiği gibi yaygın olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="06b6d-115">Options are commonly used when a search does not return a matching result, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

<span data-ttu-id="06b6d-116">Önceki kodda Aranan yinelemeli olarak listesidir.</span><span class="sxs-lookup"><span data-stu-id="06b6d-116">In the previous code, a list is searched recursively.</span></span> <span data-ttu-id="06b6d-117">İşlev `tryFindMatch` koşul bir işlev alır `pred` bir Boole değeri ve aramak için bir liste döndürür.</span><span class="sxs-lookup"><span data-stu-id="06b6d-117">The function `tryFindMatch` takes a predicate function `pred` that returns a Boolean value, and a list to search.</span></span> <span data-ttu-id="06b6d-118">Koşulu karşılayan bir öğe bulunursa, özyineleme sona erer ve işlevi döndürür değer ifadesi bir seçenek olarak `Some(head)`.</span><span class="sxs-lookup"><span data-stu-id="06b6d-118">If an element that satisfies the predicate is found, the recursion ends and the function returns the value as an option in the expression `Some(head)`.</span></span> <span data-ttu-id="06b6d-119">Boş bir liste eşleştiğinde özyineleme sona erer.</span><span class="sxs-lookup"><span data-stu-id="06b6d-119">The recursion ends when the empty list is matched.</span></span> <span data-ttu-id="06b6d-120">Bu noktada değeri `head` bulunamadı, ve `None` döndürülür.</span><span class="sxs-lookup"><span data-stu-id="06b6d-120">At that point the value `head` has not been found, and `None` is returned.</span></span>

<span data-ttu-id="06b6d-121">Bir koleksiyonu olabilir veya return olmayabilir bir değer için arama birçok F # kitaplığı işlevleri `option` türü.</span><span class="sxs-lookup"><span data-stu-id="06b6d-121">Many F# library functions that search a collection for a value that may or may not exist return the `option` type.</span></span> <span data-ttu-id="06b6d-122">Bu işlevler kurala göre başlayın `try` önek, örneğin, [ `Seq.tryFindIndex` ](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a).</span><span class="sxs-lookup"><span data-stu-id="06b6d-122">By convention, these functions begin with the `try` prefix, for example, [`Seq.tryFindIndex`](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a).</span></span>

<span data-ttu-id="06b6d-123">Ayrıca bir değer, mümkünse bir değer oluşturmaya çalışırken bir özel durum, örneğin mevcut olmayabilir seçenekleri kullanışlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="06b6d-123">Options can also be useful when a value might not exist, for example if it is possible that an exception will be thrown when you try to construct a value.</span></span> <span data-ttu-id="06b6d-124">Aşağıdaki kod örneği bunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="06b6d-124">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

<span data-ttu-id="06b6d-125">`openFile` Önceki örnekte işlevi türüne sahip `string -> File option` onu döndürdüğünden bir `File` dosya başarıyla açılır, nesne ve `None` bir özel durum oluşursa.</span><span class="sxs-lookup"><span data-stu-id="06b6d-125">The `openFile` function in the previous example has type `string -> File option` because it returns a `File` object if the file opens successfully and `None` if an exception occurs.</span></span> <span data-ttu-id="06b6d-126">Durum bağlı olarak, bu yayılmasına izin vererek yerine bir özel durum yakalamak için bir uygun tasarım seçiminin olmayabilir.</span><span class="sxs-lookup"><span data-stu-id="06b6d-126">Depending on the situation, it may not be an appropriate design choice to catch an exception rather than allowing it to propagate.</span></span>


## <a name="option-properties-and-methods"></a><span data-ttu-id="06b6d-127">Seçenek özellikleri ve yöntemleri</span><span class="sxs-lookup"><span data-stu-id="06b6d-127">Option Properties and Methods</span></span>
<span data-ttu-id="06b6d-128">Seçenek türü aşağıdaki özellikleri ve yöntemleri destekler.</span><span class="sxs-lookup"><span data-stu-id="06b6d-128">The option type supports the following properties and methods.</span></span>



|<span data-ttu-id="06b6d-129">Özelliği veya yöntemi</span><span class="sxs-lookup"><span data-stu-id="06b6d-129">Property or method</span></span>|<span data-ttu-id="06b6d-130">Tür</span><span class="sxs-lookup"><span data-stu-id="06b6d-130">Type</span></span>|<span data-ttu-id="06b6d-131">Açıklama</span><span class="sxs-lookup"><span data-stu-id="06b6d-131">Description</span></span>|
|------------------|----|-----------|
|[<span data-ttu-id="06b6d-132">Yok</span><span class="sxs-lookup"><span data-stu-id="06b6d-132">None</span></span>](https://msdn.microsoft.com/library/83ef260a-aa33-4e6f-aee6-b9bf0a461476)|`'T option`|<span data-ttu-id="06b6d-133">Sahip bir seçenek değeri oluşturmanızı sağlayan bir statik özellik `None` değeri.</span><span class="sxs-lookup"><span data-stu-id="06b6d-133">A static property that enables you to create an option value that has the `None` value.</span></span>|
|[<span data-ttu-id="06b6d-134">IsNone</span><span class="sxs-lookup"><span data-stu-id="06b6d-134">IsNone</span></span>](https://msdn.microsoft.com/library/f08532ca-1716-4f60-ae59-8ef6256df234)|`bool`|<span data-ttu-id="06b6d-135">Döndürür `true` seçeneği varsa `None` değeri.</span><span class="sxs-lookup"><span data-stu-id="06b6d-135">Returns `true` if the option has the `None` value.</span></span>|
|[<span data-ttu-id="06b6d-136">IsSome</span><span class="sxs-lookup"><span data-stu-id="06b6d-136">IsSome</span></span>](https://msdn.microsoft.com/library/c5088d51-c5d7-425f-a77f-12c379bb356f)|`bool`|<span data-ttu-id="06b6d-137">Döndürür `true` seçeneği olmayan bir değer varsa `None`.</span><span class="sxs-lookup"><span data-stu-id="06b6d-137">Returns `true` if the option has a value that is not `None`.</span></span>|
|[<span data-ttu-id="06b6d-138">Bazı</span><span class="sxs-lookup"><span data-stu-id="06b6d-138">Some</span></span>](https://msdn.microsoft.com/library/12f048d2-e293-4596-accb-de036ecd63fc)|`'T option`|<span data-ttu-id="06b6d-139">Bir seçenek oluşturan statik bir üyenin olmayan bir değere sahip `None`.</span><span class="sxs-lookup"><span data-stu-id="06b6d-139">A static member that creates an option that has a value that is not `None`.</span></span>|
|[<span data-ttu-id="06b6d-140">Değer</span><span class="sxs-lookup"><span data-stu-id="06b6d-140">Value</span></span>](https://msdn.microsoft.com/library/c79f68e8-11fd-45b1-a053-e8fc38b56df7)|`'T`|<span data-ttu-id="06b6d-141">Temel alınan değeri döndürür veya oluşturur bir `System.NullReferenceException` değer ise `None`.</span><span class="sxs-lookup"><span data-stu-id="06b6d-141">Returns the underlying value, or throws a `System.NullReferenceException` if the value is `None`.</span></span>|

## <a name="option-module"></a><span data-ttu-id="06b6d-142">Option Modülü</span><span class="sxs-lookup"><span data-stu-id="06b6d-142">Option Module</span></span>
<span data-ttu-id="06b6d-143">Bir modül yok [seçeneği](https://msdn.microsoft.com/library/e615e4d3-bbbb-49ba-addc-6061ea2e2f4c), seçenekleri işlemleri yararlı işlevler içerir.</span><span class="sxs-lookup"><span data-stu-id="06b6d-143">There is a module, [Option](https://msdn.microsoft.com/library/e615e4d3-bbbb-49ba-addc-6061ea2e2f4c), that contains useful functions that perform operations on options.</span></span> <span data-ttu-id="06b6d-144">Bazı işlevler özellikleri işlevselliğini yineleyin ancak burada bir işlev gerekli bağlamlarda yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="06b6d-144">Some functions repeat the functionality of the properties but are useful in contexts where a function is needed.</span></span> <span data-ttu-id="06b6d-145">[Option.IsSome](https://msdn.microsoft.com/library/41ad0857-5672-4326-84b5-c33dc43dcf79) ve [Option.IsNone](https://msdn.microsoft.com/library/73db6a53-15e7-40a6-94f9-a0049e5f4819) bir seçenek değeri tutan olup olmadığını test hem modülü işlevlerdir.</span><span class="sxs-lookup"><span data-stu-id="06b6d-145">[Option.isSome](https://msdn.microsoft.com/library/41ad0857-5672-4326-84b5-c33dc43dcf79) and [Option.isNone](https://msdn.microsoft.com/library/73db6a53-15e7-40a6-94f9-a0049e5f4819) are both module functions that test whether an option holds a value.</span></span> <span data-ttu-id="06b6d-146">[Option.get](https://msdn.microsoft.com/library/803e9fcb-6edd-4910-808c-25f08cbc55ea) varsa değerini alır.</span><span class="sxs-lookup"><span data-stu-id="06b6d-146">[Option.get](https://msdn.microsoft.com/library/803e9fcb-6edd-4910-808c-25f08cbc55ea) obtains the value, if there is one.</span></span> <span data-ttu-id="06b6d-147">Değer yoksa oluşturur `System.ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="06b6d-147">If there is no value, it throws `System.ArgumentException`.</span></span>

<span data-ttu-id="06b6d-148">[Option.bind](https://msdn.microsoft.com/library/c3406192-24ac-49b5-bc3b-8f805187f1c0) işlevi bir değer ise bu işlev değerine göre yürütür.</span><span class="sxs-lookup"><span data-stu-id="06b6d-148">The [Option.bind](https://msdn.microsoft.com/library/c3406192-24ac-49b5-bc3b-8f805187f1c0) function executes a function on the value, if there is a value.</span></span> <span data-ttu-id="06b6d-149">İşlev tam olarak bir bağımsız değişken almanız gerekir ve parametre türü seçenek türü olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="06b6d-149">The function must take exactly one argument, and its parameter type must be the option type.</span></span> <span data-ttu-id="06b6d-150">İşlevinin dönüş değeri, yalnızca başka bir seçenek türüdür.</span><span class="sxs-lookup"><span data-stu-id="06b6d-150">The return value of the function is another option type.</span></span>

<span data-ttu-id="06b6d-151">Option modülü listeler, dizileri, dizileri ve diğer koleksiyon türleri için kullanılabilen işlevlerin karşılık işlevleri de içerir.</span><span class="sxs-lookup"><span data-stu-id="06b6d-151">The option module also includes functions that correspond to the functions that are available for lists, arrays, sequences, and other collection types.</span></span> <span data-ttu-id="06b6d-152">Bu işlevler [ `Option.map` ](https://msdn.microsoft.com/library/91a20385-7e73-40c2-9adc-635e86d6a622), [ `Option.iter` ](https://msdn.microsoft.com/library/83389eef-3dff-4074-b4cc-f69581c25191), [ `Option.forall` ](https://msdn.microsoft.com/library/ba884586-5eae-49c5-9e36-05481c1c3428), [ `Option.exists` ](https://msdn.microsoft.com/library/a606d2d4-fddc-4eab-ab37-c6138fb7ad99), [ `Option.foldBack` ](https://msdn.microsoft.com/library/a882fbaf-c019-46f0-b4f5-b8c2b8b90ffb), [ `Option.fold` ](https://msdn.microsoft.com/library/af896794-3d53-406c-9411-316cd5c33ad8), ve [ `Option.count` ](https://msdn.microsoft.com/library/2dac83a9-684e-4d0f-b50e-ff722a8bb876).</span><span class="sxs-lookup"><span data-stu-id="06b6d-152">These functions include [`Option.map`](https://msdn.microsoft.com/library/91a20385-7e73-40c2-9adc-635e86d6a622), [`Option.iter`](https://msdn.microsoft.com/library/83389eef-3dff-4074-b4cc-f69581c25191), [`Option.forall`](https://msdn.microsoft.com/library/ba884586-5eae-49c5-9e36-05481c1c3428), [`Option.exists`](https://msdn.microsoft.com/library/a606d2d4-fddc-4eab-ab37-c6138fb7ad99), [`Option.foldBack`](https://msdn.microsoft.com/library/a882fbaf-c019-46f0-b4f5-b8c2b8b90ffb), [`Option.fold`](https://msdn.microsoft.com/library/af896794-3d53-406c-9411-316cd5c33ad8), and [`Option.count`](https://msdn.microsoft.com/library/2dac83a9-684e-4d0f-b50e-ff722a8bb876).</span></span> <span data-ttu-id="06b6d-153">Bu işlevler sıfır veya bir öğe koleksiyonunu gibi kullanılması için seçenekler sağlar.</span><span class="sxs-lookup"><span data-stu-id="06b6d-153">These functions enable options to be used like a collection of zero or one elements.</span></span> <span data-ttu-id="06b6d-154">Daha fazla bilgi ve örnekler için toplama işlevlerinde tartışma bkz [listeler](lists.md).</span><span class="sxs-lookup"><span data-stu-id="06b6d-154">For more information and examples, see the discussion of collection functions in [Lists](lists.md).</span></span>


## <a name="converting-to-other-types"></a><span data-ttu-id="06b6d-155">Diğer türleri dönüştürme</span><span class="sxs-lookup"><span data-stu-id="06b6d-155">Converting to Other Types</span></span>
<span data-ttu-id="06b6d-156">Seçenekler, listeleri ya da diziler dönüştürülebilir.</span><span class="sxs-lookup"><span data-stu-id="06b6d-156">Options can be converted to lists or arrays.</span></span> <span data-ttu-id="06b6d-157">Bir seçenek bu veri yapıları birini dönüştürüldüğünde ortaya çıkan veri yapısı sıfır veya bir öğeye sahip.</span><span class="sxs-lookup"><span data-stu-id="06b6d-157">When an option is converted into either of these data structures, the resulting data structure has zero or one element.</span></span> <span data-ttu-id="06b6d-158">Dizi için bir seçenek dönüştürmek için [ `Option.toArray` ](https://msdn.microsoft.com/library/c8044873-ba17-4b52-8231-eb1a28318c64).</span><span class="sxs-lookup"><span data-stu-id="06b6d-158">To convert an option to an array, use [`Option.toArray`](https://msdn.microsoft.com/library/c8044873-ba17-4b52-8231-eb1a28318c64).</span></span> <span data-ttu-id="06b6d-159">Bir liste için bir seçenek dönüştürmek için [ `Option.toList` ](https://msdn.microsoft.com/library/5f1af295-9fa9-40ad-b4a1-3578d94d44e1).</span><span class="sxs-lookup"><span data-stu-id="06b6d-159">To convert an option to a list, use [`Option.toList`](https://msdn.microsoft.com/library/5f1af295-9fa9-40ad-b4a1-3578d94d44e1).</span></span>


## <a name="see-also"></a><span data-ttu-id="06b6d-160">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="06b6d-160">See Also</span></span>
[<span data-ttu-id="06b6d-161">F # dili başvurusu</span><span class="sxs-lookup"><span data-stu-id="06b6d-161">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="06b6d-162">F # türleri</span><span class="sxs-lookup"><span data-stu-id="06b6d-162">F# Types</span></span>](fsharp-types.md)