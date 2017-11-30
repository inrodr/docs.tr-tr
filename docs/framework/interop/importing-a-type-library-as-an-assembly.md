---
title: "Tür Kitaplığını Derleme Olarak İçeri Aktarma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing type library
- type metadata
- custom wrappers
- metadata
- exposing COM components to .NET Framework
- Type Library Importer
- interoperation with unmanaged code, importing type library
- interoperation with unmanaged code, exposing COM components
- type libraries
- TypeLibConverter class, importing type library as assembly
- COM interop, importing type library
- COM interop, exposing COM components
ms.assetid: d1898229-cd40-426e-a275-f3eb65fbc79f
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a7657540991099cca29dc911c8e42e5ddcd22802
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="importing-a-type-library-as-an-assembly"></a><span data-ttu-id="8a375-102">Tür Kitaplığını Derleme Olarak İçeri Aktarma</span><span class="sxs-lookup"><span data-stu-id="8a375-102">Importing a Type Library as an Assembly</span></span>
<span data-ttu-id="8a375-103">COM tür tanımları genellikle bir tür kitaplığı'nda bulunur.</span><span class="sxs-lookup"><span data-stu-id="8a375-103">COM type definitions usually reside in a type library.</span></span> <span data-ttu-id="8a375-104">Buna karşılık, CLS uyumlu derleyicileri derlemedeki türü meta veriler üretir.</span><span class="sxs-lookup"><span data-stu-id="8a375-104">In contrast, CLS-compliant compilers produce type metadata in an assembly.</span></span> <span data-ttu-id="8a375-105">İki kaynak türü bilgilerinin oldukça farklıdır.</span><span class="sxs-lookup"><span data-stu-id="8a375-105">The two sources of type information are quite different.</span></span> <span data-ttu-id="8a375-106">Bu konu, bir tür kitaplığından meta veri oluşturma teknikleri açıklar.</span><span class="sxs-lookup"><span data-stu-id="8a375-106">This topic describes techniques for generating metadata from a type library.</span></span> <span data-ttu-id="8a375-107">Elde edilen derlemeyi birlikte çalışma derleme adı verilir ve COM türlerini kullanmak .NET Framework uygulamaları içerdiği türü bilgileri sağlar.</span><span class="sxs-lookup"><span data-stu-id="8a375-107">The resulting assembly is called an interop assembly, and the type information it contains enables .NET Framework applications to use COM types.</span></span>  
  
 <span data-ttu-id="8a375-108">Bu tür bilgiler, uygulamanızın kullanılabilir hale getirmek için iki yolu vardır:</span><span class="sxs-lookup"><span data-stu-id="8a375-108">There are two ways to make this type information available to your application:</span></span>  
  
-   <span data-ttu-id="8a375-109">Tasarım zamanı-yalnızca birlikte çalışma derlemeleri kullanma: itibaren [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], yürütülebilir dosyanın birlikte çalışma derlemeye tür bilgilerini katıştırma görevlendirin.</span><span class="sxs-lookup"><span data-stu-id="8a375-109">Using design-time-only interop assemblies: Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can instruct the compiler to embed type information from the interop assembly into your executable.</span></span> <span data-ttu-id="8a375-110">Derleyici, uygulamanızın kullandığı türü bilgilerini katıştırır.</span><span class="sxs-lookup"><span data-stu-id="8a375-110">The compiler embeds only the type information that your application uses.</span></span> <span data-ttu-id="8a375-111">Uygulamanız ile birlikte çalışma derlemeyi dağıtmanız gerekmez.</span><span class="sxs-lookup"><span data-stu-id="8a375-111">You do not have to deploy the interop assembly with your application.</span></span> <span data-ttu-id="8a375-112">Önerilen yöntem budur.</span><span class="sxs-lookup"><span data-stu-id="8a375-112">This is the recommended technique.</span></span>  
  
-   <span data-ttu-id="8a375-113">Birlikte çalışma derlemeleri dağıtma: birlikte çalışma derlemesi için standart bir başvuru oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8a375-113">Deploying interop assemblies: You can create a standard reference to the interop assembly.</span></span> <span data-ttu-id="8a375-114">Bu durumda, uygulamanız ile birlikte çalışma derlemesi dağıtılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="8a375-114">In this case, the interop assembly must be deployed with your application.</span></span> <span data-ttu-id="8a375-115">Bu yöntem uygulamadığınız ve özel bir COM bileşeni kullanmıyorsanız, her zaman yönetilen kodunuzda birleştirmek istiyorsanız COM bileşeni yazarı tarafından yayımlanan birincil birlikte çalışma derlemesi (PIA) başvuru.</span><span class="sxs-lookup"><span data-stu-id="8a375-115">If you employ this technique, and you are not using a private COM component, always reference the primary interop assembly (PIA) published by the author of the COM component you intend to incorporate in your managed code.</span></span> <span data-ttu-id="8a375-116">Oluşturan ve birincil birlikte çalışma derlemeleri kullanma hakkında daha fazla bilgi için bkz: [birincil birlikte çalışma derlemeleri](http://msdn.microsoft.com/en-us/b977a8be-59a0-40a0-a806-b11ffba5c080).</span><span class="sxs-lookup"><span data-stu-id="8a375-116">For more information about producing and using primary interop assemblies, see [Primary Interop Assemblies](http://msdn.microsoft.com/en-us/b977a8be-59a0-40a0-a806-b11ffba5c080).</span></span>  
  
 <span data-ttu-id="8a375-117">Tasarım zamanı-yalnızca birlikte çalışma derlemeleri kullandığınızda, COM bileşeninin yazar tarafından yayımlanan birincil birlikte çalışma derlemesi tür bilgilerini katıştırma.</span><span class="sxs-lookup"><span data-stu-id="8a375-117">When you use design-time-only interop assemblies, you can embed type information from the primary interop assembly published by the author of the COM component.</span></span> <span data-ttu-id="8a375-118">Ancak, uygulamanız ile birincil birlikte çalışma derlemesi dağıtmak gerekmez.</span><span class="sxs-lookup"><span data-stu-id="8a375-118">However, you do not have to deploy the primary interop assembly with your application.</span></span>  
  
 <span data-ttu-id="8a375-119">Çoğu uygulamayı bir COM bileşeni'nin tüm özelliklerini kullanmadığından tasarım-zamanı-yalnızca birlikte çalışma derlemeleri kullanarak, uygulamanızın boyutunu azaltır.</span><span class="sxs-lookup"><span data-stu-id="8a375-119">Using design-time-only interop assemblies reduces the size of your application, because most applications do not use all the features of a COM component.</span></span> <span data-ttu-id="8a375-120">Tür bilgilerini katıştırır yüklediğinizde derleyici çok verimli olur; Uygulamanız yalnızca bazı yöntemlere bir COM arabirimi kullanıyorsa derleyici kullanılmayan yöntemleri katıştırmak değil.</span><span class="sxs-lookup"><span data-stu-id="8a375-120">The compiler is very efficient when it embeds type information; if your application uses only some of the methods on a COM interface, the compiler does not embed the unused methods.</span></span> <span data-ttu-id="8a375-121">Katıştırılmış türde bilgi içeren bir uygulama gibi başka bir uygulama ile etkileşim veya birincil birlikte çalışma derlemesi kullanan bir uygulama ile etkileşime giren, ortak dil çalışma zamanı kullandığı iki ile türleri olup olmadığını belirlemek için eşdeğer kuralları yazın. aynı adı aynı COM türünü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="8a375-121">When an application that has embedded type information interacts with another such application, or interacts with an application that uses a primary interop assembly, the common language runtime uses type equivalence rules to determine whether two types with the same name represent the same COM type.</span></span> <span data-ttu-id="8a375-122">COM nesneleri kullanmak için bu kurallar bilmek zorunda değildir.</span><span class="sxs-lookup"><span data-stu-id="8a375-122">You do not have to know these rules to use COM objects.</span></span> <span data-ttu-id="8a375-123">Ancak, kurallarda ilgileniyorsanız, bkz [tür Eşdeğerliği ve katıştırılmış birlikte çalışma türlerini](../../../docs/framework/interop/type-equivalence-and-embedded-interop-types.md).</span><span class="sxs-lookup"><span data-stu-id="8a375-123">However, if you are interested in the rules, see [Type Equivalence and Embedded Interop Types](../../../docs/framework/interop/type-equivalence-and-embedded-interop-types.md).</span></span>  
  
## <a name="generating-metadata"></a><span data-ttu-id="8a375-124">Meta veri oluşturma</span><span class="sxs-lookup"><span data-stu-id="8a375-124">Generating Metadata</span></span>  
 <span data-ttu-id="8a375-125">COM tür kitaplıklarının Loanlib.tlb gibi bir .tlb uzantısına sahip tek başına dosya olabilir.</span><span class="sxs-lookup"><span data-stu-id="8a375-125">COM type libraries can be stand-alone files that have a .tlb extension, such as Loanlib.tlb.</span></span> <span data-ttu-id="8a375-126">Bazı tür kitaplıklarının bir .dll veya .exe dosyasının kaynak bölümüne katıştırılır.</span><span class="sxs-lookup"><span data-stu-id="8a375-126">Some type libraries are embedded in the resource section of a .dll or .exe file.</span></span> <span data-ttu-id="8a375-127">Diğer bilgi kaynaklarıyla ilgili tür kitaplığı .olb ve .ocx dosyalarıdır.</span><span class="sxs-lookup"><span data-stu-id="8a375-127">Other sources of type library information are .olb and .ocx files.</span></span>  
  
 <span data-ttu-id="8a375-128">COM türü hedef uygulaması içeren tür kitaplığı bulduktan sonra türü meta verileri içeren bir birlikte çalışma derleme oluşturmak için aşağıdaki seçenekleriniz vardır:</span><span class="sxs-lookup"><span data-stu-id="8a375-128">After you locate the type library that contains the implementation of your target COM type, you have the following options for generating an interop assembly containing type metadata:</span></span>  
  
-   <span data-ttu-id="8a375-129">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8a375-129">Visual Studio</span></span>  
  
     <span data-ttu-id="8a375-130">Visual Studio derleme meta verilerini otomatik olarak bir tür kitaplığı COM türlerinde dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="8a375-130">Visual Studio automatically converts COM types in a type library to metadata in an assembly.</span></span> <span data-ttu-id="8a375-131">Yönergeler için bkz: [nasıl yapılır: tür kitaplıklarına Başvuru Ekle](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md) ve [izlenecek yol: Microsoft Office derlemelerinden tür bilgilerini katıştırma](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3).</span><span class="sxs-lookup"><span data-stu-id="8a375-131">For instructions, see [How to: Add References to Type Libraries](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md) and [Walkthrough: Embedding Type Information from Microsoft Office Assemblies](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3).</span></span>  
  
-   [<span data-ttu-id="8a375-132">Tür kitaplığı içeri Aktarıcı (Tlbimp.exe)</span><span class="sxs-lookup"><span data-stu-id="8a375-132">Type Library Importer (Tlbimp.exe)</span></span>](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
  
     <span data-ttu-id="8a375-133">Tür kitaplığı içeri Aktarıcı meta verileri elde edilen birlikte çalışma dosyasındaki ayarlamak için komut satırı seçenekleri sağlar, türleri var olan bir tür kitaplığından içeri aktarır ve birlikte çalışabilirlik bütünleştirilmiş kod ve bir ad alanı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="8a375-133">The Type Library Importer provides command-line options to adjust metadata in the resulting interop file, imports types from an existing type library, and generates an interop assembly and a namespace.</span></span> <span data-ttu-id="8a375-134">Yönergeler için bkz: [nasıl yapılır: tür kitaplıklarından birlikte çalışma derlemeleri oluşturmak](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="8a375-134">For instructions, see [How to: Generate Interop Assemblies from Type Libraries](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
-   <span data-ttu-id="8a375-135"><xref:System.Runtime.InteropServices.TypeLibConverter?displayProperty=nameWithType>sınıfı</span><span class="sxs-lookup"><span data-stu-id="8a375-135"><xref:System.Runtime.InteropServices.TypeLibConverter?displayProperty=nameWithType> class</span></span>  
  
     <span data-ttu-id="8a375-136">Bu sınıf coclass'ları ve bir tür kitaplığı arabirimlerde derlemedeki meta verileri dönüştürmek için yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="8a375-136">This class provides methods to convert coclasses and interfaces in a type library to metadata within an assembly.</span></span> <span data-ttu-id="8a375-137">Tlbimp.exe aynı meta veri çıkışı üretir.</span><span class="sxs-lookup"><span data-stu-id="8a375-137">It produces the same metadata output as Tlbimp.exe.</span></span> <span data-ttu-id="8a375-138">Ancak, Tlbimp.exe, aksine <xref:System.Runtime.InteropServices.TypeLibConverter> sınıfı, bir bellek içi tür kitaplığı meta verileri dönüştürebilir.</span><span class="sxs-lookup"><span data-stu-id="8a375-138">However, unlike Tlbimp.exe, the <xref:System.Runtime.InteropServices.TypeLibConverter> class can convert an in-memory type library to metadata.</span></span>  
  
-   <span data-ttu-id="8a375-139">Özel sarmalayıcılar</span><span class="sxs-lookup"><span data-stu-id="8a375-139">Custom wrappers</span></span>  
  
     <span data-ttu-id="8a375-140">Bir tür kitaplığı kullanılamıyor ya da yanlış olduğunda, bir seçenek sınıfı veya arabirimi yinelenen tanımının yönetilen kaynak kodunda oluşturmaktır.</span><span class="sxs-lookup"><span data-stu-id="8a375-140">When a type library is unavailable or incorrect, one option is to create a duplicate definition of the class or interface in managed source code.</span></span> <span data-ttu-id="8a375-141">Ardından, derlemedeki meta verileri üretmek için çalışma zamanı hedefleyen bir derleme kaynak koduyla de derleyin.</span><span class="sxs-lookup"><span data-stu-id="8a375-141">You then compile the source code with a compiler that targets the runtime to produce metadata in an assembly.</span></span>  
  
     <span data-ttu-id="8a375-142">COM türlerini manuel olarak tanımlamak için aşağıdaki öğeleri erişiminiz olmalıdır:</span><span class="sxs-lookup"><span data-stu-id="8a375-142">To define COM types manually, you must have access to the following items:</span></span>  
  
    -   <span data-ttu-id="8a375-143">Kesin açıklamaları tanımlanmakta arabirimleri ve coclass'ları.</span><span class="sxs-lookup"><span data-stu-id="8a375-143">Precise descriptions of the coclasses and interfaces being defined.</span></span>  
  
    -   <span data-ttu-id="8a375-144">Uygun .NET Framework sınıf tanımları oluşturabilen C# Derleyici gibi bir derleyici.</span><span class="sxs-lookup"><span data-stu-id="8a375-144">A compiler, such as the C# compiler, that can generate the appropriate .NET Framework class definitions.</span></span>  
  
    -   <span data-ttu-id="8a375-145">Tür kitaplığını derleme dönüştürme kurallarını bilgi.</span><span class="sxs-lookup"><span data-stu-id="8a375-145">Knowledge of the type library-to-assembly conversion rules.</span></span>  
  
     <span data-ttu-id="8a375-146">Özel bir sarmalayıcı yazma Gelişmiş bir tekniktir.</span><span class="sxs-lookup"><span data-stu-id="8a375-146">Writing a custom wrapper is an advanced technique.</span></span> <span data-ttu-id="8a375-147">Özel bir sarmalayıcı oluşturur hakkında ek bilgi için bkz: [özelleştirme standart sarmalayıcıları](http://msdn.microsoft.com/en-us/c40d089b-6a3c-41b5-a20d-d760c215e49d).</span><span class="sxs-lookup"><span data-stu-id="8a375-147">For additional information about how to generate a custom wrapper, see [Customizing Standard Wrappers](http://msdn.microsoft.com/en-us/c40d089b-6a3c-41b5-a20d-d760c215e49d).</span></span>  
  
 <span data-ttu-id="8a375-148">COM birlikte çalışma alma işlemi hakkında daha fazla bilgi için bkz: [derleme dönüştürme özeti için tür kitaplığı](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958).</span><span class="sxs-lookup"><span data-stu-id="8a375-148">For more information about the COM interop import process, see [Type Library to Assembly Conversion Summary](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a375-149">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8a375-149">See Also</span></span>  
 <xref:System.Runtime.InteropServices.TypeLibConverter>  
 [<span data-ttu-id="8a375-150">COM bileşenlerini .NET Framework'te gösterme</span><span class="sxs-lookup"><span data-stu-id="8a375-150">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 [<span data-ttu-id="8a375-151">Derleme dönüştürme özeti için tür kitaplığı</span><span class="sxs-lookup"><span data-stu-id="8a375-151">Type Library to Assembly Conversion Summary</span></span>](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958)  
 [<span data-ttu-id="8a375-152">Tlbimp.exe (tür kitaplığı içeri Aktarıcı)</span><span class="sxs-lookup"><span data-stu-id="8a375-152">Tlbimp.exe (Type Library Importer)</span></span>](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
 [<span data-ttu-id="8a375-153">Standart sarmalayıcıları özelleştirme</span><span class="sxs-lookup"><span data-stu-id="8a375-153">Customizing Standard Wrappers</span></span>](http://msdn.microsoft.com/en-us/c40d089b-6a3c-41b5-a20d-d760c215e49d)  
 [<span data-ttu-id="8a375-154">Yönetilen kodda COM türlerini kullanma</span><span class="sxs-lookup"><span data-stu-id="8a375-154">Using COM Types in Managed Code</span></span>](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)  
 [<span data-ttu-id="8a375-155">Birlikte çalışma projesi derleme</span><span class="sxs-lookup"><span data-stu-id="8a375-155">Compiling an Interop Project</span></span>](../../../docs/framework/interop/compiling-an-interop-project.md)  
 [<span data-ttu-id="8a375-156">Birlikte çalışma uygulamasını dağıtma</span><span class="sxs-lookup"><span data-stu-id="8a375-156">Deploying an Interop Application</span></span>](../../../docs/framework/interop/deploying-an-interop-application.md)  
 [<span data-ttu-id="8a375-157">Nasıl yapılır: tür kitaplıklarına başvurular ekleme</span><span class="sxs-lookup"><span data-stu-id="8a375-157">How to: Add References to Type Libraries</span></span>](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md)  
 [<span data-ttu-id="8a375-158">Nasıl yapılır: tür kitaplıklarından birlikte çalışma derlemeleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="8a375-158">How to: Generate Interop Assemblies from Type Libraries</span></span>](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md)  
 [<span data-ttu-id="8a375-159">İzlenecek yol: Microsoft Office derlemelerinden tür bilgilerini katıştırma</span><span class="sxs-lookup"><span data-stu-id="8a375-159">Walkthrough: Embedding Type Information from Microsoft Office Assemblies</span></span>](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3)