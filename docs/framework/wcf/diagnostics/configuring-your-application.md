---
title: "Uygulamanızı Yapılandırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f22fac02616070ecd6498ad0e158782001681ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="configuring-your-application"></a><span data-ttu-id="aa3c1-102">Uygulamanızı Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="aa3c1-102">Configuring Your Application</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="aa3c1-103">.NET yapılandırma sistemini kullanır ve her iki makine ve uygulama kapsamda hizmetlerini yapılandırmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-103"> uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="aa3c1-104">Yapılandırma ayarları tarafından tanımlanan [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bulunan `<system.serviceModel>` bölüm grubu.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-104">Configuration settings defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are located in the `<system.serviceModel>` section group.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="aa3c1-105">nasıl yapılandırılacağı bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hizmet, aşağıdaki konulara bakın:</span><span class="sxs-lookup"><span data-stu-id="aa3c1-105"> how to configure a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, see the following topics:</span></span>  
  
-   [<span data-ttu-id="aa3c1-106">Hizmetleri Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="aa3c1-106">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [<span data-ttu-id="aa3c1-107">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="aa3c1-107">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="aa3c1-108">Uygulama tanımlı yapılandırma ayarları tanımlanmış `<appSettings>` bölüm grubu.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-108">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="aa3c1-109">Uygulama ayarları .NET yapılandırma dosyalarında bkz [ \<appSettings >](http://go.microsoft.com/fwlink/?LinkId=95159).</span><span class="sxs-lookup"><span data-stu-id="aa3c1-109"> application settings in .NET configuration files, see [\<appSettings>](http://go.microsoft.com/fwlink/?LinkId=95159).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="aa3c1-110">Yapılandırma Düzenleyicisi'ni kullanarak</span><span class="sxs-lookup"><span data-stu-id="aa3c1-110">Using the Configuration Editor</span></span>  
 <span data-ttu-id="aa3c1-111">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [Yapılandırma Aracı (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) Yöneticiler ve geliştiriciler oluşturmak ve yapılandırma ayarlarını değiştirmek izin veren [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bir grafik kullanıcı arabirimini kullanarak hizmetleri.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-111">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)][Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services using a graphical user interface.</span></span> <span data-ttu-id="aa3c1-112">Bu araçla ayarlarını yönetebilirsiniz [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bağlamaları, davranışları, hizmetleri ve XML yapılandırma dosyalarını doğrudan düzenleyerek olmadan tanılama.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-112">With this tool, you can manage settings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="aa3c1-113">Visual Studio'da yapılandırma dosyalarını düzenleme</span><span class="sxs-lookup"><span data-stu-id="aa3c1-113">Editing Configuration Files in Visual Studio</span></span>  
 <span data-ttu-id="aa3c1-114">Yapılandırma dosyasını düzenlemek için bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hizmet projesinde [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], sağ tıklayın, **Çözüm Gezgini** ve **Düzenle WCF yapılandırma** bağlam menüsü öğesini.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-114">To edit the configuration file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service project in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="aa3c1-115">Bu başlatır [Yapılandırma Aracı (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="aa3c1-115">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa3c1-116">Yapılandırma dosyası düzenlerseniz bir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web hizmeti projesinde [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] içinde tıklanarak **Çözüm Gezgini**, dikkat **Düzenle WCF yapılandırma** bağlam menüsü öğesini eksik .</span><span class="sxs-lookup"><span data-stu-id="aa3c1-116">If you edit the configuration file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web Service project in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="aa3c1-117">Geçici çözüm bu sorunu tıklatın **Araçları** menüsünde ve seçin **WCF Hizmeti Yapılandırma Düzenleyicisi**.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-117">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="aa3c1-118">Bundan sonra bir yapılandırma dosyasına sağ tıklayın ve kullanmak **Düzenle WCF yapılandırma** bağlam menüsü öğesini.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-118">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa3c1-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="aa3c1-119">See Also</span></span>  
 [<span data-ttu-id="aa3c1-120">Yapılandırma Aracı (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="aa3c1-120">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [<span data-ttu-id="aa3c1-121">Hizmetleri Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="aa3c1-121">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
 [<span data-ttu-id="aa3c1-122">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="aa3c1-122">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)