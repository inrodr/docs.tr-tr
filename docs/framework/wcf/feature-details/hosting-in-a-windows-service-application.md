---
title: "Windows Hizmet Uygulamasında Barındırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4199998-27f3-4dd9-aee4-0a4addfa9f24
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 07823da6a920a22e35932f32f9320499d9cc84a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="hosting-in-a-windows-service-application"></a><span data-ttu-id="3d6cb-102">Windows Hizmet Uygulamasında Barındırma</span><span class="sxs-lookup"><span data-stu-id="3d6cb-102">Hosting in a Windows Service Application</span></span>
<span data-ttu-id="3d6cb-103">(Daha önce Windows NT Hizmetleri bilinen) Windows hizmetleri sağlayan bir işlem modeli özellikle uzun süre çalışan yürütülebilir dosya içinde bulunmalıdır ve herhangi bir kullanıcı arabirimi biçimi gösterme uygulamalar için uygundur.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-103">Windows services (formerly known as Windows NT services) provide a process model particularly suited to applications that must live in a long-running executable and do not display any form of user interface.</span></span> <span data-ttu-id="3d6cb-104">Hizmet uygulaması başlangıç olanak tanıyan, hizmet denetimi yöneticisi tarafından (SCM), yönetilen bir Windows işlem ömrü durdurun ve Windows hizmeti uygulamalarını duraklatma.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-104">The process lifetime of a Windows service application is managed by the service control manager (SCM), which allows you to start, stop, and pause Windows service applications.</span></span> <span data-ttu-id="3d6cb-105">Bir Windows hizmet işlemi "her zaman açık" uygulamalar için uygun bir barındırma ortamı kolaylaştırarak bilgisayar başlatıldığında otomatik olarak başlayacak şekilde yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-105">You can configure a Windows service process to start automatically when the computer starts, making it a suitable hosting environment for "always on" applications.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="3d6cb-106">Windows hizmet uygulamaları, bkz: [Windows hizmet uygulamaları](http://go.microsoft.com/fwlink/?LinkId=89450).</span><span class="sxs-lookup"><span data-stu-id="3d6cb-106"> Windows service applications, see [Windows Service Applications](http://go.microsoft.com/fwlink/?LinkId=89450).</span></span>  
  
 <span data-ttu-id="3d6cb-107">Uzun süre çalışan barındıran uygulamalar [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Hizmetleri, Windows Hizmetleri ile birçok özelliği paylaşımı.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-107">Applications that host long-running [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services share many characteristics with Windows services.</span></span> <span data-ttu-id="3d6cb-108">Özellikle, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hizmetlerdir doğrudan kullanıcıyla etkileşim değil ve bu nedenle herhangi bir kullanıcı arabirimi biçimi uygulamak uzun süre çalışan sunucu yürütülebilir.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-108">In particular, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services are long-running server executables that do not interact directly with the user and therefore do not implement any form of user interface.</span></span> <span data-ttu-id="3d6cb-109">Bu nedenle, barındırma [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services Windows hizmeti uygulaması içinde güçlü, uzun süreli oluşturmak için bir seçenek [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uygulamalar.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-109">As such, hosting [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services inside of a Windows service application is one option for building robust, long-running, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
 <span data-ttu-id="3d6cb-110">Genellikle, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] geliştiriciler mi barındırmak karar gerekir kendi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bir Windows hizmet uygulaması içinde veya Internet Information Services (IIS) veya Windows İşlem Etkinleştirme Hizmeti (WAS) bir barındırma ortamı içinde uygulama.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-110">Often, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] developers must decide whether to host their [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application inside of a Windows service application or inside of the Internet Information Services (IIS) or Windows Process Activation Service (WAS) hosting environment.</span></span> <span data-ttu-id="3d6cb-111">Windows hizmet uygulamaları aşağıdaki koşullarda kullanmayı düşünmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="3d6cb-111">You should consider using Windows service applications under the following conditions:</span></span>  
  
-   <span data-ttu-id="3d6cb-112">Uygulamanızın açık etkinleştirme gerektirir.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-112">Your application requires explicit activation.</span></span> <span data-ttu-id="3d6cb-113">Örneğin, dinamik olarak ilk gelen iletisine yanıt olarak başlatılmakta yerine sunucu başlatıldığında yapılacak uygulamanızı otomatik olarak başlamalıdır olduğunda Windows Hizmetleri kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-113">For example, you should use Windows services when your application must start automatically when the server starts instead of being dynamically started in response to the first incoming message.</span></span>  
  
-   <span data-ttu-id="3d6cb-114">Uygulamanızı barındıran işlemin başlatıldığında çalışan kalmalıdır.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-114">The process that hosts your application must remain running once started.</span></span> <span data-ttu-id="3d6cb-115">Başladıktan sonra bir Windows hizmet işlemi sürece çalışmaya devam açıkça Kapatma Hizmet Denetim Yöneticisi'ni kullanarak bir sunucu yöneticisi tarafından.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-115">Once started, a Windows service process remains running unless explicitly shut down by a server administrator using the service control manager.</span></span> <span data-ttu-id="3d6cb-116">IIS ya da WAS içinde barındırılan uygulamalar başlatıldı ve sistem kaynakları en iyi kullanılmasını sağlamak için dinamik olarak durduruldu.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-116">Applications hosted in IIS or WAS may be started and stopped dynamically to make optimal use of system resources.</span></span> <span data-ttu-id="3d6cb-117">Kendi barındırma işlemi ömrü üzerinde açık denetim gerektiren uygulamalar, IIS ya da WAS yerine Windows Hizmetleri kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-117">Applications that require explicit control over the lifetime of their hosting process should use Windows services instead of IIS or WAS.</span></span>  
  
-   <span data-ttu-id="3d6cb-118">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Hizmeti Windows Server 2003'te çalıştırın ve HTTP dışında taşımaları kullanın.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-118">Your [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service must run on Windows Server 2003 and use transports other than HTTP.</span></span> <span data-ttu-id="3d6cb-119">Windows Server 2003'te [!INCLUDE[iis601](../../../../includes/iis601-md.md)] barındırma ortamı yalnızca HTTP iletişimi için kısıtlanmış.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-119">On Windows Server 2003, the [!INCLUDE[iis601](../../../../includes/iis601-md.md)] hosting environment is restricted to HTTP communication only.</span></span> <span data-ttu-id="3d6cb-120">Windows hizmet uygulamaları bu kısıtlama tabi değildir ve herhangi bir aktarım kullanabilirsiniz [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] net.tcp net.pipe ve net.msmq çeşitli destekler.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-120">Windows service applications are not subject to this restriction and can use any transport [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports, including net.tcp, net.pipe, and net.msmq.</span></span>  
  
### <a name="to-host-wcf-inside-of-a-windows-service-application"></a><span data-ttu-id="3d6cb-121">Windows hizmet uygulaması içinde WCF barındırmak için</span><span class="sxs-lookup"><span data-stu-id="3d6cb-121">To host WCF inside of a Windows service application</span></span>  
  
1.  <span data-ttu-id="3d6cb-122">Windows hizmet uygulaması oluşturun.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-122">Create a Windows service application.</span></span> <span data-ttu-id="3d6cb-123">Windows hizmet uygulamaları sınıflarda kullanarak yönetilen kod yazabilirsiniz <xref:System.ServiceProcess> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-123">You can write Windows service applications in managed code using the classes in the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="3d6cb-124">Bu uygulama öğesinden devralınan bir sınıf içermelidir <xref:System.ServiceProcess.ServiceBase>.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-124">This application must include one class that inherits from <xref:System.ServiceProcess.ServiceBase>.</span></span>  
  
2.  <span data-ttu-id="3d6cb-125">Ömrü bağlantı [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Windows ömrü Hizmetleri hizmet uygulaması.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-125">Link the lifetime of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to the lifetime of the Windows service application.</span></span> <span data-ttu-id="3d6cb-126">Genellikle, istediğiniz [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hizmetler bir Windows hizmet uygulamasında barındırma hizmeti başlatıldığında etkinleşir barındırılan, Dur barındırma hizmeti durdurulduğunda iletiler için dinleme ve ne zaman işlem barındırma aşağı bilgisayarı [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Hizmet hatayla karşılaşıyor.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-126">Typically, you want [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services hosted in a Windows service application to become active when the hosting service starts, stop listening for messages when the hosting service is stopped, and shut down the hosting process when the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service encounters an error.</span></span> <span data-ttu-id="3d6cb-127">Bu şekilde gerçekleştirilebilir:</span><span class="sxs-lookup"><span data-stu-id="3d6cb-127">This can be accomplished as follows:</span></span>  
  
    -   <span data-ttu-id="3d6cb-128">Geçersiz kılma <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> bir veya daha fazla örneğini açmayı <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-128">Override <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> to open one or more instances of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="3d6cb-129">Tek bir Windows hizmeti uygulama birden çok barındırabilir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] başlatma ve durdurma grup olarak hizmetler.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-129">A single Windows service application can host multiple [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services that start and stop as a group.</span></span>  
  
    -   <span data-ttu-id="3d6cb-130">Geçersiz kılma <xref:System.ServiceProcess.ServiceBase.OnStop%2A> çağırmak için <xref:System.ServiceModel.Channels.CommunicationObject.Closed> üzerinde <xref:System.ServiceModel.ServiceHost> tüm çalışan [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sırasında başlatılan Hizmetleri <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-130">Override <xref:System.ServiceProcess.ServiceBase.OnStop%2A> to call <xref:System.ServiceModel.Channels.CommunicationObject.Closed> on the <xref:System.ServiceModel.ServiceHost> any running [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services that were started during <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>.</span></span>  
  
    -   <span data-ttu-id="3d6cb-131">Abone <xref:System.ServiceModel.Channels.CommunicationObject.Faulted> olayı <xref:System.ServiceModel.ServiceHost> ve <xref:System.ServiceProcess.ServiceController> hata durumunda Windows hizmet uygulaması kapatmak üzere sınıfı.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-131">Subscribe to the <xref:System.ServiceModel.Channels.CommunicationObject.Faulted> event of <xref:System.ServiceModel.ServiceHost> and use the <xref:System.ServiceProcess.ServiceController> class to shut down the Windows service application in case of error.</span></span>  
  
     <span data-ttu-id="3d6cb-132">Windows hizmet uygulamaları barındıran [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Hizmetleri dağıtılan ve hale Windows hizmet uygulamaları kullanımı gibi aynı şekilde yönetilir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d6cb-132">Windows service applications that host [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services are deployed and managed in the same way as Windows service applications that do not make use of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d6cb-133">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3d6cb-133">See Also</span></span>  
 <xref:System.ServiceProcess>  
 [<span data-ttu-id="3d6cb-134">İzlenecek yol: Bileşen tasarımcısında Windows hizmet uygulaması oluşturma</span><span class="sxs-lookup"><span data-stu-id="3d6cb-134">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](http://go.microsoft.com/fwlink/?LinkId=94875)  
 [<span data-ttu-id="3d6cb-135">Nasıl yapılır: yönetilen bir Windows hizmetinde bir WCF Hizmeti barındırma</span><span class="sxs-lookup"><span data-stu-id="3d6cb-135">How to: Host a WCF Service in a Managed Windows Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)  
 [<span data-ttu-id="3d6cb-136">Windows Hizmet Konağı</span><span class="sxs-lookup"><span data-stu-id="3d6cb-136">Windows Service Host</span></span>](../../../../docs/framework/wcf/samples/windows-service-host.md)  
 [<span data-ttu-id="3d6cb-137">Hizmet uygulaması programlama mimarisi</span><span class="sxs-lookup"><span data-stu-id="3d6cb-137">Service Application Programming Architecture</span></span>](http://go.microsoft.com/fwlink/?LinkId=94876)  
 [<span data-ttu-id="3d6cb-138">Windows Server App Fabric barındırma özellikleri</span><span class="sxs-lookup"><span data-stu-id="3d6cb-138">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)