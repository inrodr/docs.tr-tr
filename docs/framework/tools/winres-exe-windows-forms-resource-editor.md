---
title: "Winres.exe (Windows Forms Kaynak Düzenleyici)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Winres.exe
- Windows Forms Resource Editor
- localization
- Windows Forms, localization
- forms, localizing
- resx files
- .resx files
ms.assetid: cb8bc835-9221-4888-af53-1a4f5fad6c48
caps.latest.revision: "23"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8009f832434d6bbad2ad7bee9cbfd62c81d623c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="winresexe-windows-forms-resource-editor"></a><span data-ttu-id="2cea7-102">Winres.exe (Windows Forms Kaynak Düzenleyici)</span><span class="sxs-lookup"><span data-stu-id="2cea7-102">Winres.exe (Windows Forms Resource Editor)</span></span>
<span data-ttu-id="2cea7-103">Windows Formları Kaynak Düzenleyicisi Winres.exe, yerelleştirme uzmanlarının formlar tarafından kullanılan Windows Formları kullanıcı arabirimi (UI) kaynaklarını yerelleştirmesine yardımcı olan görsel bir düzen aracıdır.</span><span class="sxs-lookup"><span data-stu-id="2cea7-103">The Windows Forms Resource Editor, Winres.exe, is a visual layout tool that helps localization experts localize Windows Forms user interface (UI) resources used by forms.</span></span> <span data-ttu-id="2cea7-104">Winres.exe için girdi olarak kullanılan .resx veya .resources dosyaları Microsoft Visual Studio gibi bir görsel tasarım ortamı kullanarak oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-104">The .resx or .resources files that are used as input to Winres.exe can be created using a visual design environment such as Microsoft Visual Studio.</span></span> <span data-ttu-id="2cea7-105">.NET Framework uygulamalarında kaynakları dağıtma hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakları](../../../docs/framework/resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="2cea7-105">For information on deploying resources in .NET Framework applications, see [Resources in Desktop Apps](../../../docs/framework/resources/index.md).</span></span>  
  
 <span data-ttu-id="2cea7-106">Bu araç, Visual Studio ile birlikte otomatik olarak yüklenir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="2cea7-107">Aracı çalıştırmak için, Geliştirici Komut İstemi (veya Windows 7'de Visual Studio Komut İstemi) kullanın.</span><span class="sxs-lookup"><span data-stu-id="2cea7-107">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="2cea7-108">Daha fazla bilgi için bkz: [komut istemlerini](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="2cea7-108">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="2cea7-109">Komut satırına şunu yazın:</span><span class="sxs-lookup"><span data-stu-id="2cea7-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cea7-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="2cea7-110">Syntax</span></span>  
  
```  
winres resourceFile   
winres /?   
```  
  
## <a name="remarks"></a><span data-ttu-id="2cea7-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2cea7-111">Remarks</span></span>  
  
|<span data-ttu-id="2cea7-112">Bağımsız Değişken</span><span class="sxs-lookup"><span data-stu-id="2cea7-112">Argument</span></span>|<span data-ttu-id="2cea7-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2cea7-113">Description</span></span>|  
|--------------|-----------------|  
|`resourceFile`|<span data-ttu-id="2cea7-114">Yerelleştirilecek kaynak dosyası.</span><span class="sxs-lookup"><span data-stu-id="2cea7-114">The resource file to localize.</span></span> <span data-ttu-id="2cea7-115">Bu dosya, Visual Studio tasarımcısı tarafından oluşturulan Windows Forms formu .resx veya .resources dosyası olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="2cea7-115">This file must be a Windows Forms form .resx or .resources file generated by the Visual Studio designer.</span></span> <span data-ttu-id="2cea7-116">Winres.exe genel .resx veya .resources dosyalarını açamaz.</span><span class="sxs-lookup"><span data-stu-id="2cea7-116">Winres.exe cannot open generic .resx or .resources files.</span></span>|  
  
|<span data-ttu-id="2cea7-117">Seçenek</span><span class="sxs-lookup"><span data-stu-id="2cea7-117">Option</span></span>|<span data-ttu-id="2cea7-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2cea7-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2cea7-119">**/?**</span><span class="sxs-lookup"><span data-stu-id="2cea7-119">**/?**</span></span>|<span data-ttu-id="2cea7-120">Araç için komut sözdizimini ve seçenekleri görüntüler.</span><span class="sxs-lookup"><span data-stu-id="2cea7-120">Displays command syntax and options for the tool.</span></span>|  
  
 <span data-ttu-id="2cea7-121">Bir Windows Forms projesindeki formda bulunan arabirim öğelerinin durumu genellikle kaynak dosyalarında depolanır; bunlar .resx uzantılı XML tabanlı dosyalar veya karşılık gelen derlenmiş, .resources uzantılı ikili sürümlerdir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-121">The state of UI elements from a form in a Windows Forms project are typically stored in resource files, which are either XML-based files with the extension .resx or the corresponding compiled, binary versions with the extension .resources.</span></span> <span data-ttu-id="2cea7-122">Winres.exe, her iki dosya türünün Visual Studio tasarım ortamı dışında sınırlı şekilde düzenlenmesine olanak veren bir araçtır.</span><span class="sxs-lookup"><span data-stu-id="2cea7-122">Winres.exe is a tool that enables limited editing of either type of file outside of the Visual Studio design environment.</span></span> <span data-ttu-id="2cea7-123">Özellikle aşağıdaki türden düzenleme işlemlerine izin verir:</span><span class="sxs-lookup"><span data-stu-id="2cea7-123">Specifically, it allows the following types of editing operations:</span></span>  
  
-   <span data-ttu-id="2cea7-124">Bir nötr veya belirli kültür kaynak dosyası, formun arabirim özelliklerini veya denetimlerini (metin, boyut veya konum gibi) değiştirecek şekilde düzenlenebilir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-124">A neutral or specific culture resource file can be edited to change the UI properties of the form or its controls, such as their text, size, or position.</span></span>  
  
-   <span data-ttu-id="2cea7-125">Nötr veya belirli kültür kaynak dosyaları varsayılan kaynak dosyasından oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-125">Neutral or specific culture resource files can be generated from the default resource file.</span></span>  
  
-   <span data-ttu-id="2cea7-126">Bir kültür kaynak dosyası başka bir kültür kaynak dosyası olarak kaydedilebilir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-126">A culture resource file can be saved as another culture resource file.</span></span> <span data-ttu-id="2cea7-127">Örneğin, İngilizce (ABD) kaynak dosyası Lehçe kaynak dosyası olarak kaydedilebilir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-127">For example, an English (U.S.) resource file could be saved as a Polish resource file.</span></span> <span data-ttu-id="2cea7-128">Genellikle yeni dosya daha sonra yeni kültür ile uyumlu olacak şekilde düzenlenir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-128">Typically the new file would subsequently be edited to be compatible with the new culture.</span></span>  
  
 <span data-ttu-id="2cea7-129">Ayrıca bkz. [yerelleştirme, hiyerarşik kuruluş kaynakları](http://msdn.microsoft.com/library/756hydy4\(v=vs.110\)) veya [yerelleştirme, hiyerarşik kuruluş kaynakları](http://msdn.microsoft.com/library/756hydy4\(v=vs.120\)).</span><span class="sxs-lookup"><span data-stu-id="2cea7-129">Also see [Hierarchical Organization of Resources for Localization](http://msdn.microsoft.com/library/756hydy4\(v=vs.110\)) or [Hierarchical Organization of Resources for Localization](http://msdn.microsoft.com/library/756hydy4\(v=vs.120\)).</span></span>  
  
 <span data-ttu-id="2cea7-130">Winres.exe, bir .resx dosyasını karşılık gelen .resources dosyasına dönüştüremez; bunun yerine Resgen.exe aracını kullanmalısınız.</span><span class="sxs-lookup"><span data-stu-id="2cea7-130">Winres.exe cannot convert a .resx file into its corresponding .resources file; use the Resgen.exe tool instead.</span></span> <span data-ttu-id="2cea7-131">Resgen.exe hakkında daha fazla bilgi için bkz: [Resgen.exe (kaynak dosya oluşturucu)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md).</span><span class="sxs-lookup"><span data-stu-id="2cea7-131">For more information about Resgen.exe, see [Resgen.exe (Resource File Generator)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md).</span></span>  
  
 <span data-ttu-id="2cea7-132">Winres.exe, kaynak koduna erişmeden bir Windows Forms formunun tasarım zamanı sürümünü yalnızca kaynak dosyasından yeniden oluşturan grafiksel bir uygulamadır.</span><span class="sxs-lookup"><span data-stu-id="2cea7-132">Winres.exe is a graphical application that recreates a design-time version of a Windows Forms form from just the resource file, without having access to the source code.</span></span> <span data-ttu-id="2cea7-133">Winres.exe, Visual Studio'nun Windows Forms Form Tasarımcısı ve Özellikler penceresini barındırır.</span><span class="sxs-lookup"><span data-stu-id="2cea7-133">Winres.exe hosts Visual Studio's Windows Forms Form Designer and Properties window.</span></span> <span data-ttu-id="2cea7-134">Bu özellikler, Windows Forms formu içeren bir .resources veya .resx dosyasının görsel olarak düzenlenmesine olanak verir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-134">These features enable visual editing of a .resources or .resx file containing a Windows Forms form.</span></span> <span data-ttu-id="2cea7-135">Yerelleştiriciler genellikle hedef kültüre uygun olacak şekilde denetim etiketlerini düzenlemek ve denetimlerin konumu ile boyutunu ayarlamak için Winres.exe'yi kullanırlar.</span><span class="sxs-lookup"><span data-stu-id="2cea7-135">Typically localizers use Winres.exe to edit control labels and adjust the location and size of controls to accommodate the labels for the target culture.</span></span>  
  
 <span data-ttu-id="2cea7-136">Winres.exe bir denetimin türünü çözümleyemezse, yerelleştirilmiş .resx veya .resources dosyasında bir yer tutucu denetimi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="2cea7-136">If Winres.exe cannot resolve the type of a control, it creates a placeholder control in the localized .resx or .resources file.</span></span> <span data-ttu-id="2cea7-137">Yer tutucu denetimi Windows Forms formunda taranmış bir pencere olarak görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-137">The placeholder control appears on the Windows Forms form as a hatched window.</span></span> <span data-ttu-id="2cea7-138">Taranmış pencerenin boyutu ve konumu gerçek denetiminkilerle aynıdır.</span><span class="sxs-lookup"><span data-stu-id="2cea7-138">The size and position of the hatched window matches that of the actual control.</span></span> <span data-ttu-id="2cea7-139">Yer tutucu denetiminin tüm kullanılabilir, yerelleştirilebilir özellikleri Özellikler penceresinde görünür.</span><span class="sxs-lookup"><span data-stu-id="2cea7-139">All the available localizable properties for the placeholder control appear in the Properties window.</span></span> <span data-ttu-id="2cea7-140">Yer tutucu denetiminde yaptığınız tüm değişiklikler asıl denetim için kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-140">Any changes that you make to the placeholder control are saved for the actual control.</span></span>  
  
## <a name="winresexe-versus-visual-studio"></a><span data-ttu-id="2cea7-141">Winres.exe ve Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2cea7-141">Winres.exe versus Visual Studio</span></span>  
 <span data-ttu-id="2cea7-142">Genel olarak, bir uygulamanın Windows Forms formlarını yerelleştirmeye başlamadan önce, yerelleştirme aracı olarak Visual Studio'yu mu yoksa Winres.exe'yi mi kullanmak istediğinize karar vermelisiniz.</span><span class="sxs-lookup"><span data-stu-id="2cea7-142">In general, before you begin to localize an application's Windows Forms forms, you should decide whether you want to use Visual Studio or Winres.exe as the localization tool.</span></span> <span data-ttu-id="2cea7-143">Sürüm uyumluluğu, daha sonra açıklandığı gibi, bir araçtan diğerine geçiş yapmasını engelleyebilir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-143">Version compatibility, as described later, may prevent you from switching from one tool to the other.</span></span>  
  
 <span data-ttu-id="2cea7-144">Visual Studio'nun avantajı, bir uygulamayı hem geliştirmek hem de yerelleştirmek için kullanabilmenizdedir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-144">The advantage of Visual Studio is that you can use it to both develop and localize an application.</span></span> <span data-ttu-id="2cea7-145">Formun geliştirme tamamlandıktan sonra bir form yerelleştirme ayarlayın <xref:System.ComponentModel.LocalizableAttribute> ( **yerelleştirilebilir** özellikleri Düzenleyicisi'nde özelliği) için `true` değiştirip kendi **dil** özelliği İstenen hedef kültür.</span><span class="sxs-lookup"><span data-stu-id="2cea7-145">To localize a form, after development is complete, set the form's <xref:System.ComponentModel.LocalizableAttribute> (the **Localizable** property in the Properties Editor) to `true` and change its **Language** property to the desired target culture.</span></span> <span data-ttu-id="2cea7-146">Daha sonra, dizeleri düzenleyin ve denetimlerin konumu ile boyutunu hedef kültürün dizelerine uygun olacak şekilde ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="2cea7-146">Then, edit strings and adjust the location and size of controls to accommodate the strings for the target culture.</span></span> <span data-ttu-id="2cea7-147">Yerelleştirilmiş .resx dosyasını kaydettiğinizde, Visual Studio dosyaya yalnızca yerelleştirilebilir özellikleri (hedef kültürde değiştirilen özellikler) yazar.</span><span class="sxs-lookup"><span data-stu-id="2cea7-147">When you save the localized .resx file, Visual Studio writes only the localizable properties (properties that changed in the target culture) to the file.</span></span> <span data-ttu-id="2cea7-148">Visual Studio, yerelleştirilmiş .resx dosyası için bir uydu derlemesini doğru dizin konumunda otomatik olarak oluşturur.</span><span class="sxs-lookup"><span data-stu-id="2cea7-148">Visual Studio automatically creates a satellite assembly for the localized .resx file in the correct directory location.</span></span>  <span data-ttu-id="2cea7-149">Ayrıca bkz. [izlenecek yol: Windows Formları yerelleştirme](http://msdn.microsoft.com/library/y99d1cd3\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="2cea7-149">Also see [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/library/y99d1cd3\(v=vs.110\)).</span></span>  
  
 <span data-ttu-id="2cea7-150">Visual Studio tümleşik bir geliştirme ve yerelleştirme ortamı sağlasa da, yerelleştirme üçüncü taraf yerelleştiriciler tarafından yapılacaksa önerilen araç Winres.exe'dir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-150">Although Visual Studio provides an integrated development and localization environment, Winres.exe is the recommended tool to use if localization will be done by third-party localizers.</span></span> <span data-ttu-id="2cea7-151">Winres.exe yalnızca bir yerelleştirme aracı olduğu için, bir uygulamanın kodu ile yerelleştirilecek formlar arasında daha net bir ayrım sağlar, ki bu da büyük projeleri yönetirken daha büyük bir kolaylık demektir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-151">Because Winres.exe is a localization tool only, it allows for a cleaner separation of an application's code from the forms to be localized, which is more practical for managing large projects.</span></span>  
  
## <a name="using-winresexe"></a><span data-ttu-id="2cea7-152">Winres.exe'yi kullanma</span><span class="sxs-lookup"><span data-stu-id="2cea7-152">Using Winres.exe</span></span>  
 <span data-ttu-id="2cea7-153">Winres.exe kullanarak yerelleştirmek için, önce Visual Studio'da Forms Tasarımcısı gibi görsel bir tasarımcıyı kullanarak bir uygulama geliştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-153">To localize using Winres.exe, you must first develop an application using a visual designer like the Forms Designer in Visual Studio.</span></span> <span data-ttu-id="2cea7-154">Geliştirme tamamlandığında, formun ayarlamak <xref:System.ComponentModel.LocalizableAttribute> ( **yerelleştirilebilir** özelliği özellikleri Düzenleyicisi'nde) için `true`ve ardından varsayılan kültür için .resx dosyası kapalı bir üçüncü taraf yerelleştiriciye el.</span><span class="sxs-lookup"><span data-stu-id="2cea7-154">When development is complete, set the form's <xref:System.ComponentModel.LocalizableAttribute> (the **Localizable** property in the Properties Editor) to `true`, and then hand off the .resx file for the default culture to a third-party localizer.</span></span> <span data-ttu-id="2cea7-155">Bu .resx dosyası özgün formun tasarım zamanı sürümünü yeniden oluşturmak için Winres.exe'nin kullandığı ek bilgileri içerir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-155">This .resx file contains extra information that Winres.exe uses to recreate a design-time version of the original form.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="2cea7-156">Winres.exe varsayılan kaynak dosyayı düzenlemek için kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="2cea7-156">Winres.exe cannot be used to edit the default resource file.</span></span> <span data-ttu-id="2cea7-157">Winres.exe, değişen tüm özellikleri yerelleştirilmiş özellikler olarak yorumlar ve bunları hedef kültür kaynak dosyasına kaydeder.</span><span class="sxs-lookup"><span data-stu-id="2cea7-157">Winres.exe interprets all changed properties as localized properties and saves them to the target culture resource file.</span></span>  
  
 <span data-ttu-id="2cea7-158">Kültür kaynak dosyalarının son sürümleri son olarak uygulamanın yerelleştirilmiş sürümlerini oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-158">The final versions of the culture resource files can finally be used to create localized versions of the application.</span></span> <span data-ttu-id="2cea7-159">Daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakları](../../../docs/framework/resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="2cea7-159">For more information, see [Resources in Desktop Apps](../../../docs/framework/resources/index.md).</span></span>  
  
 <span data-ttu-id="2cea7-160">Winres.exe 2.0 sürümünde aşağıdaki özellikler ve yetenekler vardır:</span><span class="sxs-lookup"><span data-stu-id="2cea7-160">Version 2.0 of Winres.exe has the following features and capabilities:</span></span>  
  
-   <span data-ttu-id="2cea7-161">Winres Tek Dosya Modu'nda (SFM) veya Visual Studio Dosya Modu'nda (VSFM) çalışabilir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-161">Winres can operate in Single File Mode (SFM) or Visual Studio File Mode (VSFM).</span></span> <span data-ttu-id="2cea7-162">SFM, form ve içeriği hakkındaki tüm bilgilerin kaynak dosyada depolandığı eski moddur.</span><span class="sxs-lookup"><span data-stu-id="2cea7-162">SFM is the legacy mode where complete information about the form and its contents is stored to the resource file.</span></span> <span data-ttu-id="2cea7-163">VSFM kültürel değişiklikleri yalnızca kaynak dosyasında depolar.</span><span class="sxs-lookup"><span data-stu-id="2cea7-163">VSFM only stores only the cultural changes in the resource file.</span></span>  
  
-   <span data-ttu-id="2cea7-164">Arabirime ana pencerenin sol alt tarafında bir hata bildirimi penceresi eklenmiştir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-164">An error-reporting window, docked to the bottom-left of the main window, has been added to the interface.</span></span>  
  
-   <span data-ttu-id="2cea7-165">Kısayol tuşları çoğaltmaları kontrol: biçimi menüden **kısayollarıyla denetleyin** komutu.</span><span class="sxs-lookup"><span data-stu-id="2cea7-165">Hotkeys can be checked for duplicates: from the Format menu, click the **Check HotKeys** command.</span></span>  
  
## <a name="version-compatibility"></a><span data-ttu-id="2cea7-166">Sürüm Uyumluluğu</span><span class="sxs-lookup"><span data-stu-id="2cea7-166">Version Compatibility</span></span>  
 <span data-ttu-id="2cea7-167">Kaynak dosyaların biçimi Visual Studio .NET 2002 ve Visual Studio 2005 sürümleri arasında değiştiğinden, Winres.exe de uyumlu olacak şekilde değiştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-167">Because the format of resource files changed between Visual Studio .NET 2002 and Visual Studio 2005, Winres.exe was likewise changed to be compatible.</span></span> <span data-ttu-id="2cea7-168">Bu nedenle genel kural olarak, uygulamayı oluşturmak için kullanmakta olduğunuz .NET Framework ile birlikte yayımlanan Winres.exe sürümünü kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-168">Therefore, as a general rule, you should use the version of Winres.exe that was released with the .NET Framework you are using to create the application.</span></span> <span data-ttu-id="2cea7-169">Aşağıdaki tabloda uyumlu sürümler listelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-169">The following table lists the compatible versions.</span></span>  
  
|<span data-ttu-id="2cea7-170">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2cea7-170">Visual Studio</span></span>|<span data-ttu-id="2cea7-171">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="2cea7-171">.NET Framework</span></span>|<span data-ttu-id="2cea7-172">Winres.exe</span><span class="sxs-lookup"><span data-stu-id="2cea7-172">Winres.exe</span></span>|  
|-------------------|--------------------|----------------|  
|<span data-ttu-id="2cea7-173">Visual Studio .NET 2002</span><span class="sxs-lookup"><span data-stu-id="2cea7-173">Visual Studio .NET 2002</span></span>|<span data-ttu-id="2cea7-174">1.0</span><span class="sxs-lookup"><span data-stu-id="2cea7-174">1.0</span></span>|<span data-ttu-id="2cea7-175">1.0</span><span class="sxs-lookup"><span data-stu-id="2cea7-175">1.0</span></span>|  
|<span data-ttu-id="2cea7-176">Visual Studio .NET 2003</span><span class="sxs-lookup"><span data-stu-id="2cea7-176">Visual Studio .NET 2003</span></span>|<span data-ttu-id="2cea7-177">1.1</span><span class="sxs-lookup"><span data-stu-id="2cea7-177">1.1</span></span>|<span data-ttu-id="2cea7-178">1.1</span><span class="sxs-lookup"><span data-stu-id="2cea7-178">1.1</span></span>|  
|<span data-ttu-id="2cea7-179">Visual Studio 2005</span><span class="sxs-lookup"><span data-stu-id="2cea7-179">Visual Studio 2005</span></span>|<span data-ttu-id="2cea7-180">2,0</span><span class="sxs-lookup"><span data-stu-id="2cea7-180">2.0</span></span>|<span data-ttu-id="2cea7-181">2,0</span><span class="sxs-lookup"><span data-stu-id="2cea7-181">2.0</span></span>|  
|<span data-ttu-id="2cea7-182">Visual Studio 2008</span><span class="sxs-lookup"><span data-stu-id="2cea7-182">Visual Studio 2008</span></span>|<span data-ttu-id="2cea7-183">3.0 ve 3.5</span><span class="sxs-lookup"><span data-stu-id="2cea7-183">3.0 and 3.5</span></span>|<span data-ttu-id="2cea7-184">3.0 ve 3.5</span><span class="sxs-lookup"><span data-stu-id="2cea7-184">3.0 and 3.5</span></span>|  
|<span data-ttu-id="2cea7-185">Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="2cea7-185">Visual Studio 2010</span></span>|<span data-ttu-id="2cea7-186">4.0</span><span class="sxs-lookup"><span data-stu-id="2cea7-186">4.0</span></span>|<span data-ttu-id="2cea7-187">4.0</span><span class="sxs-lookup"><span data-stu-id="2cea7-187">4.0</span></span>|  
  
 <span data-ttu-id="2cea7-188">Winres.exe 2.0 sürümü ile daha eski bir kaynak dosyasını açmaya çalışırsanız, dosyasının biçimini .NET Framework 2.0 sürümü ile uyumlu olacak şekilde yükseltmeniz istenir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-188">If you attempt to open an older resource file with version 2.0 of Winres.exe, you will be prompted to upgrade the format of the file to be compatible with version 2.0 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="2cea7-189">.NET Framework'ün 2.0'dan önceki sürümlerinde, Winres.exe ve Visual Studio Form Tasarımcısı kültüre özgü olan ve olmayan uyumsuz kaynak dosyaları oluşturmaktaydı.</span><span class="sxs-lookup"><span data-stu-id="2cea7-189">In versions of the .NET Framework prior to version 2.0, Winres.exe and the Forms Designer of Visual Studio created incompatible culture-neutral and culture-specific resource files.</span></span> <span data-ttu-id="2cea7-190">Bu nedenle, yerelleştirme işlemi başladıktan sonra yalnızca aynı aracı kullanarak devam etmek zorundaydınız.</span><span class="sxs-lookup"><span data-stu-id="2cea7-190">Therefore, once the localization process began, you had to continue using only the same tool.</span></span> <span data-ttu-id="2cea7-191">Ancak, Winres.exe 2.0 sürümüyle birlikte, Visual Studio Dosya Modu (VSFM) eklendi.</span><span class="sxs-lookup"><span data-stu-id="2cea7-191">However, with version 2.0 of Winres.exe, the Visual Studio File Mode (VSFM) was added.</span></span> <span data-ttu-id="2cea7-192">Adından da anlaşılacağı gibi, bu uyumluluk modunda kaydedilmiş bir kaynak dosyası her iki araçla da düzenlenebilmektedir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-192">As the name implies, a resource file saved in this compatibility mode can be edited with either tool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2cea7-193">VSFM'de, Visual Studio ile uyumluluk avantajı bulunuyor olsa da, kaynak dosyaya yalnızca değiştirilmiş değerleri depoladığından, Winres.exe geçerli kaynak dosyanın üst öğelerinin aynı dizinde bulunmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="2cea7-193">Although VSFM has the advantage of being compatible with Visual Studio, since it stores only changed values in the resource file, Winres.exe requires that the parents of the current resource file be located in the same directory.</span></span> <span data-ttu-id="2cea7-194">Örneğin, düzenleme `TestApp.de-DE.resources`, Almanca Almanya kaynak dosyasında gerektirir varsayılan kaynak dosyasının varlığı, `TestApp.resx`ve büyük olasılıkla kültür Tarafsız kaynak dosyası `TestApp.de.resources`.</span><span class="sxs-lookup"><span data-stu-id="2cea7-194">For example, editing `TestApp.de-DE.resources`, a German in Germany resource file, requires the presence of the default resource file, `TestApp.resx`, and possibly the culture-neutral resource file, `TestApp.de.resources`.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2cea7-195">Örnekler</span><span class="sxs-lookup"><span data-stu-id="2cea7-195">Examples</span></span>  
  
#### <a name="to-localize-a-resx-or-resources-file-associated-with-a-form"></a><span data-ttu-id="2cea7-196">Bir formla ilişkili .resx veya .resources dosyasını yerelleştirmek için</span><span class="sxs-lookup"><span data-stu-id="2cea7-196">To localize a .resx or .resources file associated with a form</span></span>  
  
1.  <span data-ttu-id="2cea7-197">Tür `winres` Winres.exe çalıştırmak için geliştirici komut istemindeki.</span><span class="sxs-lookup"><span data-stu-id="2cea7-197">Type `winres` in the developer command prompt to run Winres.exe.</span></span>  
  
2.  <span data-ttu-id="2cea7-198">Yerelleştirme için bir form için varsayılan kaynaklar'ı açmak için **açmak** komutunu **dosya** menü ve açmak için dosyaya gidin.</span><span class="sxs-lookup"><span data-stu-id="2cea7-198">To open the default resources for a form to localize, click the **Open** command on the **File** menu and navigate to the file to open it.</span></span>  
  
     <span data-ttu-id="2cea7-199">veya</span><span class="sxs-lookup"><span data-stu-id="2cea7-199">-or-</span></span>  
  
     <span data-ttu-id="2cea7-200">Winres.exe'yi başlattığınızda komut satırında açılacak dosyayı belirtin.</span><span class="sxs-lookup"><span data-stu-id="2cea7-200">Specify the file to open at the command line when you start Winres.exe.</span></span>  
  
     <span data-ttu-id="2cea7-201">Aşağıdaki komut Winres.exe başlar ve ilişkili form yüklediğinde `TestApp.resx` Form tasarımcısında.</span><span class="sxs-lookup"><span data-stu-id="2cea7-201">The following command starts Winres.exe and loads the form associated with `TestApp.resx` in the Form Designer.</span></span>  
  
    ```  
    winres TestApp.resx  
    ```  
  
     <span data-ttu-id="2cea7-202">Aşağıdaki komut Winres.exe başlar ve ilişkili form yüklediğinde `TestApp.resources` Form tasarımcısında.</span><span class="sxs-lookup"><span data-stu-id="2cea7-202">The following command starts Winres.exe and loads the form associated with `TestApp.resources` in the Form Designer.</span></span>  
  
    ```  
    winres TestApp.resources  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="2cea7-203">Kaynaklarını düzenlediğiniz form devralınmış bir form ise, hem formun içindeki derleme hem de devralan (türetilmiş) formu içeren derleme Genel Derleme Önbelleği'ne (GAC) kaydettirilmeli veya WinRes.exe ile aynı dizinde bulunmalıdır.</span><span class="sxs-lookup"><span data-stu-id="2cea7-203">If the form whose resources you are editing is an inherited form, both the assembly contained the inherited form and the assembly containing the inheriting (derived) form must either be registered in the Global Assembly Cache (GAC), or must reside in the same directory as WinRes.exe.</span></span> <span data-ttu-id="2cea7-204">GAC içine .NET Framework bileşenlerini yükleme hakkında daha fazla bilgi için bkz: [genel derleme önbelleği](../../../docs/framework/app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="2cea7-204">For more information about installing .NET Framework components into the GAC, see [Global Assembly Cache](../../../docs/framework/app-domains/gac.md).</span></span>  
  
3.  <span data-ttu-id="2cea7-205">Form üzerinde denetimleri seçin ve değiştirin kendi <xref:System.Windows.Forms.Control.Text%2A> ve diğer özellikleri yerelleştirilmiş kültür ve dili yansıtır.</span><span class="sxs-lookup"><span data-stu-id="2cea7-205">Select controls on the form and change their <xref:System.Windows.Forms.Control.Text%2A> and other properties to reflect the localized culture and its language.</span></span> <span data-ttu-id="2cea7-206">Yerelleştirilmiş metnin sığmasını sağlayacak şekilde denetimleri gerektiği gibi taşıyın veya yeniden boyutlandırın.</span><span class="sxs-lookup"><span data-stu-id="2cea7-206">Move or resize controls as necessary to accommodate the localized text.</span></span>  
  
4.  <span data-ttu-id="2cea7-207">.Resx veya .resources dosyası yerelleştirilmiş sürümünü kaydetmek için tıklatın **kaydetmek** simgesine veya aynı komutunu **dosya** menüsü.</span><span class="sxs-lookup"><span data-stu-id="2cea7-207">To save the localized version of the .resx or .resources file, click the **Save** icon or the same command on the **File** menu.</span></span> <span data-ttu-id="2cea7-208">Aracı görüntüler **seçin kültür** penceresi.</span><span class="sxs-lookup"><span data-stu-id="2cea7-208">The tool displays the **Select Culture** window.</span></span>  
  
5.  <span data-ttu-id="2cea7-209">Uygun kültür ve dosya modunu seçip'i tıklatın **Tamam**.</span><span class="sxs-lookup"><span data-stu-id="2cea7-209">Select the appropriate culture and file mode then click **OK**.</span></span> <span data-ttu-id="2cea7-210">Araç, çalışma zamanının yerelleştirilmiş kaynak dosyaları için beklediği adlandırma kuralını kullanarak dosyayı kaydeder.</span><span class="sxs-lookup"><span data-stu-id="2cea7-210">The tool saves the file, using the naming convention that the run time expects for localized resource files.</span></span> <span data-ttu-id="2cea7-211">Örneğin, yerelleştirme `TestApp.resources` Almanya Almanca için aracı dosyası olarak kaydeder `TestApp.de-DE.resources`.</span><span class="sxs-lookup"><span data-stu-id="2cea7-211">For example, if you localize `TestApp.resources` for German in Germany, the tool saves the file as `TestApp.de-DE.resources`.</span></span> <span data-ttu-id="2cea7-212">Yerelleştirme, `TestApp.resx` Almanya Almanca için aracı dosyası olarak kaydeder `TestApp.de-DE.resx`.</span><span class="sxs-lookup"><span data-stu-id="2cea7-212">If you localize `TestApp.resx` for German in Germany, the tool saves the file as `TestApp.de-DE.resx`.</span></span> <span data-ttu-id="2cea7-213">Kaynak adlandırma kuralları hakkında daha fazla bilgi için bkz: [paketleme ve dağıtma kaynakları](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md).</span><span class="sxs-lookup"><span data-stu-id="2cea7-213">For more information about resource naming conventions, see [Packaging and Deploying Resources](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md).</span></span> <span data-ttu-id="2cea7-214">Çalışma zamanı tarafından kullanılan önceden tanımlanmış kültür adları listesi için bkz: <xref:System.Globalization.CultureInfo> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="2cea7-214">For a list of the predefined culture names used by the run time, see the <xref:System.Globalization.CultureInfo> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cea7-215">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2cea7-215">See Also</span></span>  
 <xref:System.ComponentModel.LocalizableAttribute>  
 <xref:System.Globalization.CultureInfo>  
 <xref:System.Resources.ResourceManager>  
 <xref:System.Resources.ResourceReader>  
 <xref:System.Resources.ResourceWriter>  
 [<span data-ttu-id="2cea7-216">Araçları</span><span class="sxs-lookup"><span data-stu-id="2cea7-216">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="2cea7-217">Masaüstü uygulamalarındaki kaynaklar</span><span class="sxs-lookup"><span data-stu-id="2cea7-217">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)  
 [<span data-ttu-id="2cea7-218">Genelleştirme ve yerelleştirme</span><span class="sxs-lookup"><span data-stu-id="2cea7-218">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)