---
title: ".NET Framework Uygulamalarını Genelleştirme ve Yerelleştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- international applications [.NET Framework]
- globalization [.NET Framework], encoding
- global applications
- internationalization
- world-ready applications
- application development [.NET Framework], globalization
- multilingual application development
ms.assetid: 9a59696b-d89b-45bd-946d-c75da4732d02
caps.latest.revision: "42"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f6beb720819a1be4e45bf4cefac3d805d7ee5e7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="globalizing-and-localizing-net-framework-applications"></a><span data-ttu-id="418c6-102">.NET Framework Uygulamalarını Genelleştirme ve Yerelleştirme</span><span class="sxs-lookup"><span data-stu-id="418c6-102">Globalizing and Localizing .NET Framework Applications</span></span>
<span data-ttu-id="418c6-103">Geliştirme bir [dünya çapında kullanılmaya hazır uygulama](http://msdn.microsoft.com/goglobal/bb978433.aspx), bir veya daha fazla dillere yerelleştirilmiş bir uygulama da dahil olmak üzere, üç adımdan oluşur: yerelleştirilebilirlik gözden geçirin Genelleştirme ve Yerelleştirme.</span><span class="sxs-lookup"><span data-stu-id="418c6-103">Developing a [world-ready application](http://msdn.microsoft.com/goglobal/bb978433.aspx), including an application that can be localized into one or more languages, involves three steps: globalization, localizability review, and localization.</span></span>  
  
 [<span data-ttu-id="418c6-104">Genelleştirme</span><span class="sxs-lookup"><span data-stu-id="418c6-104">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 <span data-ttu-id="418c6-105">Bu adım kültür ve dil açısından nötr olan ve tüm kullanıcılar için yerelleştirilmiş kullanıcı arabirimleri ve bölgesel verileri destekleyen bir uygulamanın tasarlanması ve kodlanmasını içerir.</span><span class="sxs-lookup"><span data-stu-id="418c6-105">This step involves designing and coding an application that is culture-neutral and language-neutral, and that supports localized user interfaces and regional data for all users.</span></span> <span data-ttu-id="418c6-106">Tasarım yapma ve kültüre özgü varsayımlara dayalı olmayan kararları programlama ile ilgilidir.</span><span class="sxs-lookup"><span data-stu-id="418c6-106">It involves making design and programming decisions that are not based on culture-specific assumptions.</span></span> <span data-ttu-id="418c6-107">Global uygulamalar yerelleştirilmez, ancak daha sonra bir veya birden çok dile görece kolay yerelleştirilebilecek şekilde tasarlanır ve yazılırlar.</span><span class="sxs-lookup"><span data-stu-id="418c6-107">While a globalized application is not localized, it nevertheless is designed and written so that it can be subsequently localized into one or more languages with relative ease.</span></span>  
  
 [<span data-ttu-id="418c6-108">Yerelleştirilebilirlik gözden geçirme</span><span class="sxs-lookup"><span data-stu-id="418c6-108">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 <span data-ttu-id="418c6-109">Bu adım, bir uygulamanın kod ve tasarımının, kolayca yerelleştirilebilir olmasını sağlamak ve yerelleştirme için olası engelleri tanımlamak üzere gözden geçirilmesi ve uygulamanın yürütülebilir kodunun kaynaklarından ayrı olduğunun doğrulanması ile ilgilidir.</span><span class="sxs-lookup"><span data-stu-id="418c6-109">This step involves reviewing an application's code and design to ensure that it can be localized easily and to identify potential roadblocks for localization, and verifying that the application's executable code is separated from its resources.</span></span> <span data-ttu-id="418c6-110">Genelleştirme aşaması etkili olduysa, yerelleştirme incelemesi, genelleştirme sırasında yapılan tasarım ve kodlama seçimlerini onaylar.</span><span class="sxs-lookup"><span data-stu-id="418c6-110">If the globalization stage was effective, the localizability review will confirm the design and coding choices made during globalization.</span></span> <span data-ttu-id="418c6-111">Yerelleştirilebilirlik aşaması, bir uygulamanın kaynak kodunu yerelleştirme aşamasında değiştirmek zorunda kalmamanızı sağlayacak şekilde geri kalan sorunları tanımlayabilir.</span><span class="sxs-lookup"><span data-stu-id="418c6-111">The localizability stage may also identify any remaining issues so that an application's source code doesn't have to be modified during the localization stage.</span></span>  
  
 [<span data-ttu-id="418c6-112">Yerelleştirme</span><span class="sxs-lookup"><span data-stu-id="418c6-112">Localization</span></span>](../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="418c6-113">Bu adım özel kültürler veya bölgeler için bir uygulamanın özelleştirilmesini içerir.</span><span class="sxs-lookup"><span data-stu-id="418c6-113">This step involves customizing an application for specific cultures or regions.</span></span> <span data-ttu-id="418c6-114">Genelleştirme ve yerelleştirme adımları doğru olarak gerçekleştirilmişse, yerelleştirme, öncelikli olarak kullanıcı arabirimini çevirmeyi içerir.</span><span class="sxs-lookup"><span data-stu-id="418c6-114">If the globalization and localizability steps have been performed correctly, localization consists primarily of translating the user interface.</span></span>  
  
 <span data-ttu-id="418c6-115">Aşağıdaki üç adımı izlemenin iki avantajı vardır:</span><span class="sxs-lookup"><span data-stu-id="418c6-115">Following these three steps provides two advantages:</span></span>  
  
-   <span data-ttu-id="418c6-116">ABD gibi tek bir kültür desteklemek üzere tasarlanmış bir uygulama yükseltmek zorunda kalmaktan serbest bırakma İngilizce, ek kültürler desteklemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="418c6-116">It frees you from having to retrofit an application that is designed to support a single culture, such as U.S. English, to support additional cultures.</span></span>  
  
-   <span data-ttu-id="418c6-117">Daha kararlı ve daha az hatası olan yerelleştirilmiş uygulamalar olarak sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="418c6-117">It results in localized applications that are more stable and have fewer bugs.</span></span>  
  
 <span data-ttu-id="418c6-118">.NET Framework, dünya çapında kullanılmaya hazır ve yerelleştirilmiş uygulamalar geliştirme için kapsamlı destek sağlar.</span><span class="sxs-lookup"><span data-stu-id="418c6-118">The .NET Framework provides extensive support for the development of world-ready and localized applications.</span></span> <span data-ttu-id="418c6-119">Özellikle, .NET Framework sınıf kitaplığındaki birçok üye türü, geçerli kullanıcının kültür veya belirli bir kültürü yansıtan değerlerini döndürerek genelleştirmeye yardım eder.</span><span class="sxs-lookup"><span data-stu-id="418c6-119">In particular, many type members in the .NET Framework class library aid globalization by returning values that reflect the conventions of either the current user's culture or a specified culture.</span></span> <span data-ttu-id="418c6-120">Ayrıca, .NET Framework, bir uygulamayı yerelleştirme işlemini kolaylaştıran uydu derlemelerini destekler.</span><span class="sxs-lookup"><span data-stu-id="418c6-120">Also, the .NET Framework supports satellite assemblies, which facilitate the process of localizing an application.</span></span>  
  
 <span data-ttu-id="418c6-121">Ek bilgi için bkz: [Git genel Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkId=235015).</span><span class="sxs-lookup"><span data-stu-id="418c6-121">For additional information, see the [Go Global Developer Center](http://go.microsoft.com/fwlink/?LinkId=235015).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="418c6-122">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="418c6-122">In This Section</span></span>  
 [<span data-ttu-id="418c6-123">Genelleştirme</span><span class="sxs-lookup"><span data-stu-id="418c6-123">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 <span data-ttu-id="418c6-124">Nötr kültüre ve nötr dile sahip bir uygulama tasarlamayı ve kodlamayı da içeren, dünya çapında kullanılmaya hazır uygulama bir oluşturmanın ilk aşamasını açıklar.</span><span class="sxs-lookup"><span data-stu-id="418c6-124">Discusses the first stage of creating a world-ready application, which involves designing and coding an application that is culture-neutral and language-neutral.</span></span>  
  
 [<span data-ttu-id="418c6-125">Yerelleştirilebilirlik gözden geçirme</span><span class="sxs-lookup"><span data-stu-id="418c6-125">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 <span data-ttu-id="418c6-126">Yerelleştirmede potansiyel bariyerler tanımlamayı da içeren yerelleştirilmiş uygulama oluşturmanın ikinci aşamasını açıklar.</span><span class="sxs-lookup"><span data-stu-id="418c6-126">Discusses the second stage of creating a localized application, which involves identifying potential roadblocks to localization.</span></span>  
  
 [<span data-ttu-id="418c6-127">Yerelleştirme</span><span class="sxs-lookup"><span data-stu-id="418c6-127">Localization</span></span>](../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="418c6-128">Özel bölgeler ve kültürler için bir uygulamanın kullanıcı arabirimini özelleştirmeyi içeren yerelleştirilmiş bir uygulama oluşturmanın son adımını açıklar.</span><span class="sxs-lookup"><span data-stu-id="418c6-128">Discusses the final stage of creating a localized application, which involves customizing an application's user interface for specific regions or cultures.</span></span>  
  
 [<span data-ttu-id="418c6-129">Kültüre duyarsız dize işlemleri</span><span class="sxs-lookup"><span data-stu-id="418c6-129">Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 <span data-ttu-id="418c6-130">Kültür duyarlı olmayan sonuçlar elde etmek için varsayılan olarak kültüre duyarlı olan .NET Framework yöntemlerinin ve sınıflarının nasıl kullanılacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="418c6-130">Describes how to use .NET Framework methods and classes that are culture-sensitive by default to obtain culture-insensitive results.</span></span>  
  
 [<span data-ttu-id="418c6-131">Dünya çapında kullanılmaya hazır uygulamalar geliştirmek için en iyi uygulamalar</span><span class="sxs-lookup"><span data-stu-id="418c6-131">Best Practices for Developing World-Ready Applications</span></span>](../../../docs/standard/globalization-localization/best-practices-for-developing-world-ready-apps.md)  
 <span data-ttu-id="418c6-132">Genelleştirme, yerelleştirme ve dünya çapında kullanılmaya hazır ASP.NET uygulamaları geliştirmek için izlenebilecek en iyi uygulamaları açıklar.</span><span class="sxs-lookup"><span data-stu-id="418c6-132">Describes the best practices to follow for globalization, localization, and developing world-ready ASP.NET applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="418c6-133">Başvuru</span><span class="sxs-lookup"><span data-stu-id="418c6-133">Reference</span></span>  
 <span data-ttu-id="418c6-134"><xref:System.Globalization?displayProperty=nameWithType>ad alanı</span><span class="sxs-lookup"><span data-stu-id="418c6-134"><xref:System.Globalization?displayProperty=nameWithType> namespace</span></span>  
 <span data-ttu-id="418c6-135">Bu ad alanındaki, dil, ülke/bölge, kullanılan takvimler, tarihler için biçim desenleri, para birimi, sayılar ve dizeler için sıralama düzeni gibi kültürle ilişkili bilgileri tanımlayan sınıflar içerir</span><span class="sxs-lookup"><span data-stu-id="418c6-135">Contains classes that define culture-related information, including the language, the country/region, the calendars in use, the format patterns for dates, currency, and numbers, and the sort order for strings.</span></span>  
  
 <span data-ttu-id="418c6-136"><xref:System.Resources>ad alanı</span><span class="sxs-lookup"><span data-stu-id="418c6-136"><xref:System.Resources> namespace</span></span>  
 <span data-ttu-id="418c6-137">Kaynaklar oluşturmak, düzenlemek ve kullanmak için sınıflar sağlar.</span><span class="sxs-lookup"><span data-stu-id="418c6-137">Provides classes for creating, manipulating, and using resources.</span></span>  
  
 <span data-ttu-id="418c6-138"><xref:System.Text>ad alanı</span><span class="sxs-lookup"><span data-stu-id="418c6-138"><xref:System.Text> namespace</span></span>  
 <span data-ttu-id="418c6-139">ASCII, ANSI, Unicode ve diğer karakter kodlamalarını temsil eden sınıfları içerir.</span><span class="sxs-lookup"><span data-stu-id="418c6-139">Contains classes representing ASCII, ANSI, Unicode, and other character encodings.</span></span>  
  
 [<span data-ttu-id="418c6-140">Resgen.exe (kaynak dosya oluşturucu)</span><span class="sxs-lookup"><span data-stu-id="418c6-140">Resgen.exe (Resource File Generator)</span></span>](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)  
 <span data-ttu-id="418c6-141">.txt dosyalarını ve XML tabanlı kaynak biçimi (.resx) dosyalarını ortak dil çalışma zamanı ikili .resources dosyalarına dönüştürmek için Resgen.exe öğesinin nasıl kullanılacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="418c6-141">Describes how to use Resgen.exe to convert .txt files and XML-based resource format (.resx) files to common language runtime binary .resources files.</span></span>  
  
 [<span data-ttu-id="418c6-142">Winres.exe (Windows Forms Kaynak Düzenleyici)</span><span class="sxs-lookup"><span data-stu-id="418c6-142">Winres.exe (Windows Forms Resource Editor)</span></span>](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)  
 <span data-ttu-id="418c6-143">Windows Forms formlarını yerelleştirmek için Winres.exe yürütme dosyasının nasıl kullanılacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="418c6-143">Describes how to use Winres.exe to localize Windows Forms forms.</span></span>