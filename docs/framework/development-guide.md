---
title: ".NET Framework Geliştirme Kılavuzu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: .NET Framework, development guide
ms.assetid: 26e3d285-24c3-435c-a797-9fe5affb8525
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 429eae61ab311d2a7a68567c97f40e1fdc0a1f3e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="net-framework-development-guide"></a><span data-ttu-id="d4cbb-102">.NET Framework Geliştirme Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="d4cbb-102">.NET Framework Development Guide</span></span>
<span data-ttu-id="d4cbb-103">Bu bölümde, oluşturmak, yapılandırmak, hata ayıklama, güvenli ve .NET Framework uygulamalarınızı dağıtma açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-103">This section explains how to create, configure, debug, secure, and deploy your .NET Framework apps.</span></span> <span data-ttu-id="d4cbb-104">Ayrıca bu bölüm dinamik programlama, birlikte çalışabilirlik, genişletilebilirlik, bellek yönetimi ve iş parçacığı oluşturma gibi teknoloji alanları hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-104">The section also provides information about technology areas such as dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4cbb-105">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="d4cbb-105">In This Section</span></span>  
 [<span data-ttu-id="d4cbb-106">Uygulama temelleri</span><span class="sxs-lookup"><span data-stu-id="d4cbb-106">Application Essentials</span></span>](../../docs/standard/application-essentials.md)  
 <span data-ttu-id="d4cbb-107">Geliştirme görevleri uygulama etki alanları ve derlemeler ile programlama, özniteliklerini kullanarak, biçimlendirme ve temel türleri ayrıştırma, koleksiyonları kullanarak, olayları ve özel durumları işleme, dosya ve veri akışlarını kullanma ve kullanarak gibi temel uygulama hakkında bilgi sağlar genel türler.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-107">Provides information about basic app development tasks, such as programming with app domains and assemblies, using attributes, formatting and parsing base types, using collections, handling events and exceptions, using files and data streams, and using generics.</span></span>  
  
 [<span data-ttu-id="d4cbb-108">Veri ve modelleme</span><span class="sxs-lookup"><span data-stu-id="d4cbb-108">Data and Modeling</span></span>](../../docs/framework/data/index.md)  
 <span data-ttu-id="d4cbb-109">ADO.NET, dil tümleşik sorgu (LINQ), WCF Veri Hizmetleri ve XML kullanarak veri erişim hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-109">Provides information about how to access data using ADO.NET, Language Integrated Query (LINQ), WCF Data Services, and XML.</span></span>  
  
 [<span data-ttu-id="d4cbb-110">İstemci uygulamaları</span><span class="sxs-lookup"><span data-stu-id="d4cbb-110">Client Applications</span></span>](../../docs/framework/develop-client-apps.md)  
 <span data-ttu-id="d4cbb-111">Windows Presentation Foundation (WPF) veya Windows Forms kullanarak Windows tabanlı uygulamalar oluşturma açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-111">Explains how to create Windows-based apps by using Windows Presentation Foundation (WPF) or Windows Forms.</span></span>  
  
 [<span data-ttu-id="d4cbb-112">ASP.NET ile Web uygulamaları</span><span class="sxs-lookup"><span data-stu-id="d4cbb-112">Web Applications with ASP.NET</span></span>](../../docs/framework/develop-web-apps-with-aspnet.md)  
 <span data-ttu-id="d4cbb-113">Kurumsal sınıf kodlama en az ile web uygulamaları oluşturmak için ASP.NET kullanma hakkında bilgi için bağlantılar sağlar.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-113">Provides links to information about using ASP.NET to build enterprise-class web apps with a minimum of coding.</span></span>  
  
 [<span data-ttu-id="d4cbb-114">WCF ile hizmet odaklı uygulamalar</span><span class="sxs-lookup"><span data-stu-id="d4cbb-114">Service-Oriented Applications with WCF</span></span>](../../docs/framework/wcf/index.md)  
 <span data-ttu-id="d4cbb-115">Windows Communication Foundation (WCF) güvenli ve güvenilir hizmet odaklı uygulamalar oluşturmak için nasıl kullanılacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-115">Describes how to use Windows Communication Foundation (WCF) to build service-oriented apps that are secure and reliable.</span></span>  
  
 <span data-ttu-id="d4cbb-116">[Windows Workflow Foundation iş akışlarıyla oluşturma](windows-workflow-foundation/index.md)   </span><span class="sxs-lookup"><span data-stu-id="d4cbb-116">[Building workflows with Windows Workflow Foundation](windows-workflow-foundation/index.md)   </span></span>  
 <span data-ttu-id="d4cbb-117">Windows Workflow Foundation (WF) kullanmak için programlama modelini, örnekleri ve araçlar hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-117">Provides information about the programming model, samples, and tools for using Windows Workflow Foundation (WF).</span></span>  

 [<span data-ttu-id="d4cbb-118">Windows hizmet uygulamaları</span><span class="sxs-lookup"><span data-stu-id="d4cbb-118">Windows Service Applications</span></span>](../../docs/framework/windows-services/index.md)  
 <span data-ttu-id="d4cbb-119">Bir hizmet ve başlangıç, durdurmak ve aksi takdirde davranışını denetlemek yüklediğiniz bir uygulama oluşturmak için Visual Studio ve .NET Framework nasıl kullanabileceğini açıklar.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-119">Explains how you can use Visual Studio and the .NET Framework to create an app that is installed as a service, and start, stop, and otherwise control its behavior.</span></span>  
  
 [<span data-ttu-id="d4cbb-120">Paralel işleme ve eşzamanlılık</span><span class="sxs-lookup"><span data-stu-id="d4cbb-120">Parallel Processing and Concurrency</span></span>](../../docs/standard/parallel-processing-and-concurrency.md)  
 <span data-ttu-id="d4cbb-121">Yönetilen iş parçacığı oluşturma, paralel programlama ve zaman uyumsuz programlama tasarım desenleri hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-121">Provides information about managed threading, parallel programming, and asynchronous programming design patterns.</span></span>  
  
 [<span data-ttu-id="d4cbb-122">.NET Framework'te ağ programlaması</span><span class="sxs-lookup"><span data-stu-id="d4cbb-122">Network Programming in the .NET Framework</span></span>](../../docs/framework/network-programming/index.md)  
 <span data-ttu-id="d4cbb-123">Katmanlı, genişletilebilir ve yönetilen uygulamayı hızla ve kolayca, uygulamalarla tümleştirin Internet Hizmetleri açıklar.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-123">Describes the layered, extensible, and managed implementation of Internet services that you can quickly and easily integrate into your apps.</span></span>  
  
 <span data-ttu-id="d4cbb-124">[.NET Framework uygulamaları yapılandırma](configure-apps/index.md)  </span><span class="sxs-lookup"><span data-stu-id="d4cbb-124">[Configuring .NET Framework Apps](configure-apps/index.md)  </span></span>  
 <span data-ttu-id="d4cbb-125">.NET Framework uygulamalarınızı yeniden derlemenize gerek kalmadan ayarlarını değiştirmek için yapılandırma dosyalarını nasıl kullanabileceğiniz açıklanır.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-125">Explains how you can use configuration files to change settings without having to recompile your .NET Framework apps.</span></span>  
  
 [<span data-ttu-id="d4cbb-126">.NET yerel ile uygulama derleme</span><span class="sxs-lookup"><span data-stu-id="d4cbb-126">Compiling Apps with .NET Native</span></span>](../../docs/framework/net-native/index.md)  
 <span data-ttu-id="d4cbb-127">Nasıl kullanabileceğinizi açıklar [!INCLUDE[net_native](../../includes/net-native-md.md)] geliştirmek ve Windows mağazası uygulamaları dağıtmak için ön derleme teknolojisi.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-127">Explains how you can use the [!INCLUDE[net_native](../../includes/net-native-md.md)] precompilation technology to build and deploy Windows Store apps.</span></span> [!INCLUDE[net_native](../../includes/net-native-md.md)]<span data-ttu-id="d4cbb-128">Yönetilen kodda (C#) yazılmıştır ve .NET Framework yerel koda hedef uygulamaları derler.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-128"> compiles apps that are written in managed code (C#) and that target the .NET Framework to native code.</span></span>  
  
 [<span data-ttu-id="d4cbb-129">Güvenlik</span><span class="sxs-lookup"><span data-stu-id="d4cbb-129">Security</span></span>](../../docs/standard/security/index.md)  
 <span data-ttu-id="d4cbb-130">Sınıfları ve .NET Framework'teki güvenli uygulama geliştirmeyi kolaylaştıran hizmetler hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-130">Provides information about the classes and services in the .NET Framework that facilitate secure app development.</span></span>  
  
 [<span data-ttu-id="d4cbb-131">Hata ayıklama, izleme ve profil oluşturma</span><span class="sxs-lookup"><span data-stu-id="d4cbb-131">Debugging, Tracing, and Profiling</span></span>](../../docs/framework/debug-trace-profile/index.md)  
 <span data-ttu-id="d4cbb-132">Sınamak için en iyi duruma getirme ve .NET Framework uygulamaları ve uygulama ortamı profili açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-132">Explains how to test, optimize, and profile .NET Framework apps and the app environment.</span></span> <span data-ttu-id="d4cbb-133">Bu bölümde, Yöneticiler ve bunun yanı sıra geliştiriciler için bilgileri içerir.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-133">This section includes information for administrators as well as developers.</span></span>  
  
 [<span data-ttu-id="d4cbb-134">Birden çok platform için geliştirme</span><span class="sxs-lookup"><span data-stu-id="d4cbb-134">Developing for Multiple Platforms</span></span>](../../docs/standard/cross-platform/index.md)  
 <span data-ttu-id="d4cbb-135">Birden çok platform ve telefonlar, masaüstü ve web gibi birden çok aygıt arasında paylaşılan derlemeler oluşturmak için .NET Framework nasıl kullanabileceğiniz hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-135">Provides information about how you can use the .NET Framework to build assemblies that can be shared across multiple platforms and multiple devices such as phones, desktop, and web.</span></span>  
  
 [<span data-ttu-id="d4cbb-136">Dağıtım</span><span class="sxs-lookup"><span data-stu-id="d4cbb-136">Deployment</span></span>](../../docs/framework/deployment/index.md)  
 <span data-ttu-id="d4cbb-137">Paket ve .NET Framework uygulamanızı dağıtmak açıklar ve geliştiriciler ve Yöneticiler için dağıtım kılavuzları içerir.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-137">Explains how to package and distribute your .NET Framework app, and includes deployment guides for both developers and administrators.</span></span>  
  
 [<span data-ttu-id="d4cbb-138">Performans</span><span class="sxs-lookup"><span data-stu-id="d4cbb-138">Performance</span></span>](../../docs/framework/performance/index.md)  
 <span data-ttu-id="d4cbb-139">Önbelleğe alma, geç başlatma, güvenilirlik ve ETW olayları hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-139">Provides information about caching, lazy initialization, reliability, and ETW events.</span></span>  
  
 <!--zz [Advanced Reading for the .NET Framework](http://msdn.microsoft.com/en-us/faae8083-fecb-4514-b133-b0a5a32a7c3c)  
 Provides information about advanced development tasks and techniques in the .NET Framework, including extensibility, interoperability, and reflection. Also includes the reference topics for unmanaged APIs that can be used by managed apps, such as runtime hosts, compilers, disassemblers, debuggers, and profilers.  --> 
  
## <a name="reference"></a><span data-ttu-id="d4cbb-140">Başvuru</span><span class="sxs-lookup"><span data-stu-id="d4cbb-140">Reference</span></span>  
 [<span data-ttu-id="d4cbb-141">.NET framework sınıf kitaplığı</span><span class="sxs-lookup"><span data-stu-id="d4cbb-141">.NET Framework Class Library</span></span>](/dotnet/api/?view=netframework-4.7)  
 <span data-ttu-id="d4cbb-142">Sözdizimi, kod örnekleri ve içerdiği her sınıf için kullanım bilgileri sağlayan [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] ad alanları.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-142">Supplies syntax, code examples, and usage information for each class that is contained in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d4cbb-143">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="d4cbb-143">Related Sections</span></span>  
 [<span data-ttu-id="d4cbb-144">Başlarken</span><span class="sxs-lookup"><span data-stu-id="d4cbb-144">Getting Started</span></span>](../../docs/framework/get-started/index.md)  
 <span data-ttu-id="d4cbb-145">.NET Framework'e kapsamlı bir genel bakış ve ek kaynaklara bağlantılar sağlar.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-145">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>  
  
 [<span data-ttu-id="d4cbb-146">Yenilikler</span><span class="sxs-lookup"><span data-stu-id="d4cbb-146">What's New</span></span>](../../docs/framework/whats-new/index.md)  
 <span data-ttu-id="d4cbb-147">Yeni anahtar özellikler ve .NET Framework'ün en son sürümündeki değişiklikleri açıklar.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-147">Describes key new features and changes in the latest version of the .NET Framework.</span></span> <span data-ttu-id="d4cbb-148">.NET Framework'ün önceki sürümden uygulamalarınızı geçirmek için bir kılavuz sağlar ve yeni ve eski tür ve üyelerin listesini içerir.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-148">Includes lists of new and obsolete types and members, and provides a guide for migrating your apps from the previous version of the .NET Framework.</span></span>  
  
 [<span data-ttu-id="d4cbb-149">Araçları</span><span class="sxs-lookup"><span data-stu-id="d4cbb-149">Tools</span></span>](../../docs/framework/tools/index.md)  
 <span data-ttu-id="d4cbb-150">Açıklar yardımcı olan araçlar geliştirmek, yapılandırmak ve .NET Framework teknolojileri kullanarak uygulamaları dağıtın.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-150">Describes the tools that help you develop, configure, and deploy apps by using .NET Framework technologies.</span></span>  
  
 [<span data-ttu-id="d4cbb-151">.NET framework örnekleri</span><span class="sxs-lookup"><span data-stu-id="d4cbb-151">.NET Framework Samples</span></span>](http://msdn.microsoft.com/en-us/177055f8-4a1f-43e7-aee6-995c196079b1)  
 <span data-ttu-id="d4cbb-152">Bağlantılar için .NET Framework teknolojileri gösteren örnek uygulamaları MSDN kod örnekleri Galerisine sağlar.</span><span class="sxs-lookup"><span data-stu-id="d4cbb-152">Provides links to the MSDN Code Samples Gallery for sample apps that demonstrate .NET Framework technologies.</span></span>