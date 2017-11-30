---
title: "x:Class Yönergesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
caps.latest.revision: "27"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 1828ef3614cc1f3a81d8aeff62c15ed5accfe380
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="xclass-directive"></a><span data-ttu-id="5182f-102">x:Class Yönergesi</span><span class="sxs-lookup"><span data-stu-id="5182f-102">x:Class Directive</span></span>
<span data-ttu-id="5182f-103">XAML biçimlendirme derleme biçimlendirmesi ve arka plan kodu arasında kısmi sınıflar katılmak için yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="5182f-103">Configures XAML markup compilation to join partial classes between markup and code-behind.</span></span> <span data-ttu-id="5182f-104">Kod kısmi sınıfı ayrı kod dosyasında tanımlanan bir [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)] dil biçimlendirme parçalı sınıf genellikle XAML derleme sırasında kod oluşturma tarafından oluşturulur ancak.</span><span class="sxs-lookup"><span data-stu-id="5182f-104">The code partial class is defined in a separate code file in a [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)] language, whereas the markup partial class is typically created by code generation during XAML compilation.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="5182f-105">XAML Öznitelik Kullanımı</span><span class="sxs-lookup"><span data-stu-id="5182f-105">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="5182f-106">XAML Değerleri</span><span class="sxs-lookup"><span data-stu-id="5182f-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`namespace`|<span data-ttu-id="5182f-107">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="5182f-107">Optional.</span></span> <span data-ttu-id="5182f-108">Belirten bir [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] tarafından tanımlanan parçalı sınıf içerir ad alanı `classname`.</span><span class="sxs-lookup"><span data-stu-id="5182f-108">Specifies a [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] namespace that contains the partial class identified by `classname`.</span></span> <span data-ttu-id="5182f-109">Varsa `namespace` belirtilirse, nokta (.) ayıran `namespace` ve `classname`.</span><span class="sxs-lookup"><span data-stu-id="5182f-109">If `namespace` is specified, a dot (.) separates `namespace` and `classname`.</span></span> <span data-ttu-id="5182f-110">Açıklamalar bakın.</span><span class="sxs-lookup"><span data-stu-id="5182f-110">See Remarks.</span></span>|  
|`classname`|<span data-ttu-id="5182f-111">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="5182f-111">Required.</span></span> <span data-ttu-id="5182f-112">Belirtir [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] yüklenen XAML ve, arka plan kod bu XAML bağlayan parçalı sınıf adı.</span><span class="sxs-lookup"><span data-stu-id="5182f-112">Specifies the [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] name of the partial class that connects the loaded XAML and your code-behind for that XAML.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="5182f-113">Bağımlılıklar</span><span class="sxs-lookup"><span data-stu-id="5182f-113">Dependencies</span></span>  
 <span data-ttu-id="5182f-114">`x:Class`yalnızca bir XAML üretim kök öğesinde belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="5182f-114">`x:Class` can only be specified on the root element of a XAML production.</span></span> <span data-ttu-id="5182f-115">`x:Class`XAML üretimde üst öğesi olan herhangi bir nesne üzerinde geçerli değil.</span><span class="sxs-lookup"><span data-stu-id="5182f-115">`x:Class` is invalid on any object that has a parent in the XAML production.</span></span> <span data-ttu-id="5182f-116">Daha fazla bilgi için bkz: [ \[MS XAML\] bölüm 4.3.1.6](http://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="5182f-116">For more information, see [\[MS-XAML\] Section 4.3.1.6](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5182f-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5182f-117">Remarks</span></span>  
 <span data-ttu-id="5182f-118">`namespace` Değeri, ilgili ad alanları, bir ortak bir .NET Framework programlama tekniktir adı Hiyerarşiler düzenlemek için ek noktalar içerebilir.</span><span class="sxs-lookup"><span data-stu-id="5182f-118">The `namespace` value may contain additional dots to organize related namespaces into name hierarchies, which is a common technique in .NET Framework programming.</span></span> <span data-ttu-id="5182f-119">Yalnızca son nokta bir dizesinde `x:Class` değerleri ayırmak için yorumlanır `namespace` ve `classname.` olarak kullanılan sınıf `x:Class` iç içe geçmiş sınıf olamaz.</span><span class="sxs-lookup"><span data-stu-id="5182f-119">Only the last dot in a string of `x:Class` values is interpreted to separate `namespace` and `classname.` The class that is used as `x:Class` cannot be a nested class.</span></span> <span data-ttu-id="5182f-120">İç içe geçmiş sınıflar noktalar için anlamını belirlemek için verilmez `x:Class` dizeleri iç içe geçmiş sınıflar izin veriyorsa belirsiz.</span><span class="sxs-lookup"><span data-stu-id="5182f-120">Nested classes are not allowed because determining the meaning of dots for `x:Class` strings is ambiguous if nested classes are permitted.</span></span>  
  
 <span data-ttu-id="5182f-121">Varolan programlama kullanmak modeli `x:Class`, `x:Class` hiçbir arka plan kodu içeren bir XAML sayfası sahip tamamen geçerli olduğunu anlamda isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="5182f-121">In existing programming models that use `x:Class`, `x:Class` is optional in the sense that it is entirely valid to have a XAML page that has no code-behind.</span></span> <span data-ttu-id="5182f-122">Ancak, bu yetenek XAML kullanan çerçeveleri tarafından uygulandığı gibi yapı eylemleri ile etkileşime girer.</span><span class="sxs-lookup"><span data-stu-id="5182f-122">However, that capability interacts with the build actions as implemented by frameworks that use XAML.</span></span> <span data-ttu-id="5182f-123">`x:Class`Yetenek XAML belirtilen içeriği çeşitli sınıflandırmaları bir uygulama modeli vardır ve ilgili eylemler yapı rolleri tarafından da etkiler.</span><span class="sxs-lookup"><span data-stu-id="5182f-123">`x:Class` capability is also influenced by the roles that various classifications of XAML-specified content have in an application model and in the corresponding build actions.</span></span> <span data-ttu-id="5182f-124">XAML olay işleme öznitelik değerleri veya özel öğeleri tanımlayan sınıflar arka plan kodu sınıfında nerede başlatır bildirirse, sağlamak zorunda `x:Class` yönerge başvurusu (veya [x: Subclass](../../../docs/framework/xaml-services/x-subclass-directive.md)) için arka plan kodu için uygun sınıf.</span><span class="sxs-lookup"><span data-stu-id="5182f-124">If your XAML declares event-handling attribute values or instantiates custom elements where the defining classes are in the code-behind class, you have to provide the `x:Class` directive reference (or [x:Subclass](../../../docs/framework/xaml-services/x-subclass-directive.md)) to the appropriate class for code-behind.</span></span>  
  
 <span data-ttu-id="5182f-125">Değeri `x:Class` yönergesi bir sınıfın ancak derleme bilgi olmadan tam adı belirten bir dize olması gerekir (eşdeğer <xref:System.Type.FullName%2A?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="5182f-125">The value of the `x:Class` directive must be a string that specifies the fully qualified name of a class but without any assembly information (equivalent to the <xref:System.Type.FullName%2A?displayProperty=nameWithType>).</span></span> <span data-ttu-id="5182f-126">Basit uygulamalar için arka plan kodu aynı zamanda (sınıf düzeyinde kodu tanımı başlar) bu şekilde yapılandırılırsa CLR ad alanı bilgilerini atlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5182f-126">For simple applications, you can omit CLR namespace information if the code-behind is also structured in that manner (code definition starts at the class level).</span></span>  
  
 <span data-ttu-id="5182f-127">Bir sayfa veya uygulama tanımı için arka plan kod dosyası, derlenen bir uygulama oluşturur ve biçimlendirme derleme ilgilidir projenin bir parçası olarak dahil olan bir kod dosya içinde olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="5182f-127">The code-behind file for a page or application definition must be within a code file that is included as part of the project that produces a compiled application and involves markup compilation.</span></span> <span data-ttu-id="5182f-128">CLR sınıflarını adı kuralları izlemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="5182f-128">You must follow name rules for CLR classes.</span></span> <span data-ttu-id="5182f-129">Daha fazla bilgi için bkz: [Framework tasarım yönergeleri](../../../docs/standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="5182f-129">For more information, see [Framework Design Guidelines](../../../docs/standard/design-guidelines/index.md).</span></span> <span data-ttu-id="5182f-130">Varsayılan olarak, arka plandaki kod sınıfı olmalıdır `public`; ancak, kullanarak onu farklı bir erişim düzeyinde tanımlayabilirsiniz [x: ClassModifier yönergesi](../../../docs/framework/xaml-services/x-classmodifier-directive.md).</span><span class="sxs-lookup"><span data-stu-id="5182f-130">By default, the code-behind class must be `public`; however, you can define it at a different access level by using the [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).</span></span>  
  
 <span data-ttu-id="5182f-131">Bu yorumu `x:Class` özniteliğini uygular. yalnızca bir CLR tabanlı XAML uygulama, özellikle de .NET Framework XAML Hizmetleri için.</span><span class="sxs-lookup"><span data-stu-id="5182f-131">This interpretation of the `x:Class` attribute applies only to a CLR-based XAML implementation, in particular to .NET Framework XAML Services.</span></span> <span data-ttu-id="5182f-132">CLR üzerinde dayalı olmayan ve .NET Framework XAML hizmetlerinde kullanmayan diğer XAML uygulamaları XAML işaretleme birbirine bağlamak ve çalışma zamanı koduyla yedekleme için farklı bir çözünürlük formülü kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5182f-132">Other XAML implementations that are not based on CLR and that do not use .NET Framework XAML Services might use a different resolution formula for connecting XAML markup and backing run-time code.</span></span> <span data-ttu-id="5182f-133">Daha fazla genel yorumlarınızı hakkında daha fazla bilgi için `x:Class`, bkz: [ \[MS XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="5182f-133">For more information about more general interpretations of `x:Class`, see [\[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
 <span data-ttu-id="5182f-134">Belirli bir mimari, anlamını düzeyinde `x:Class` .NET Framework XAML hizmetlerinde tanımlanmamış.</span><span class="sxs-lookup"><span data-stu-id="5182f-134">At a certain level of architecture, the meaning of `x:Class` is undefined in .NET Framework XAML Services.</span></span> <span data-ttu-id="5182f-135">.NET Framework XAML Hizmetleri tarafından hangi XAML biçimlendirme ve kodun yedekleme bağlı programlama modeli belirtmediğinden budur.</span><span class="sxs-lookup"><span data-stu-id="5182f-135">This is because .NET Framework XAML Services does not specify the programming model by which XAML markup and backing code are connected.</span></span> <span data-ttu-id="5182f-136">Ek kullanımlarını `x:Class` yönergesi programlama modelleri veya uygulama modelleri XAML biçimlendirme ve CLR tabanlı gerideki koddan nasıl bağlayacağınızı tanımlamak için kullanmak belirli çerçeveleri tarafından uygulanan.</span><span class="sxs-lookup"><span data-stu-id="5182f-136">Additional uses of the `x:Class` directive might be implemented by specific frameworks that use programming models or application models to define how to connect XAML markup and CLR-based code-behind.</span></span> <span data-ttu-id="5182f-137">Her framework bazı davranışı veya yapı ortamında eklenmelidir belirli bileşenleri etkinleştirmek kendi yapı eylemleri olabilir.</span><span class="sxs-lookup"><span data-stu-id="5182f-137">Each framework can have its own build actions that enable some of the behavior or specific components that must be included in the build environment.</span></span> <span data-ttu-id="5182f-138">Bir çerçeve içinde yapı eylemleri de arka plan kod için kullanılan belirli CLR dil bağlı olarak değişebilir.</span><span class="sxs-lookup"><span data-stu-id="5182f-138">Within a framework, build actions can also vary depending on the specific CLR language that is used for the code-behind.</span></span>  
  
## <a name="xclass-in-the-wpf-programming-model"></a><span data-ttu-id="5182f-139">x: Class WPF programlama modeli</span><span class="sxs-lookup"><span data-stu-id="5182f-139">x:Class in the WPF Programming Model</span></span>  
 <span data-ttu-id="5182f-140">WPF uygulamaları ve WPF uygulama modeli `x:Class` XAML dosyasının kök ve derleniyor herhangi bir öğe için bir özniteliği olarak bildirilebilir (burada XAML dahil bir WPF uygulaması projesi ile `Page` derleme eylemi), veya < C4 > <xref:System.Windows.Application>  uygulama tanımında derlenmiş WPF uygulaması, kök.</span><span class="sxs-lookup"><span data-stu-id="5182f-140">In WPF applications and the WPF application model, `x:Class` can be declared as an attribute for any element that is the root of a XAML file and is being compiled (where the XAML is included in a WPF application project with `Page` build action), or for the <xref:System.Windows.Application> root in the application definition of a compiled WPF application.</span></span> <span data-ttu-id="5182f-141">Bildirme `x:Class` sayfa kök veya uygulama kökü dışında bir öğe üzerinde veya değil derlenmiş bir WPF XAML dosyası, altında bir derleme zamanı hatasına neden oluyor [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] ve [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] WPF XAML derleyici.</span><span class="sxs-lookup"><span data-stu-id="5182f-141">Declaring `x:Class` on an element other than a page root or application root, or on a WPF XAML file that is not compiled, causes a compile-time error under the [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] and [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] WPF XAML compiler.</span></span> <span data-ttu-id="5182f-142">Diğer yönleri hakkında bilgi için `x:Class` WPF'de işleme, bkz: [arka plan kod ve WPF XAML](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="5182f-142">For information about other aspects of `x:Class` handling in WPF, see [Code-Behind and XAML in WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).</span></span>  
  
## <a name="xclass-for-windows-workflow-foundation"></a><span data-ttu-id="5182f-143">x: Class Windows Workflow Foundation için</span><span class="sxs-lookup"><span data-stu-id="5182f-143">x:Class for Windows Workflow Foundation</span></span>  
 <span data-ttu-id="5182f-144">Windows Workflow Foundation için `x:Class` tamamen XAML'de oluşan özel bir etkinlik sınıf adları veya arka plan kodu ile bir etkinlik Tasarımcısı için XAML sayfası kısmi sınıfı adları.</span><span class="sxs-lookup"><span data-stu-id="5182f-144">For Windows Workflow Foundation, `x:Class` names the class of a custom activity composed entirely in XAML, or names the partial class of the XAML page for  an activity designer with code-behind.</span></span>  
  
## <a name="silverlight-usage-notes"></a><span data-ttu-id="5182f-145">Silverlight kullanım notları</span><span class="sxs-lookup"><span data-stu-id="5182f-145">Silverlight Usage Notes</span></span>  
 <span data-ttu-id="5182f-146">`x:Class`Silverlight için ayrı olarak belgelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="5182f-146">`x:Class` for Silverlight is documented separately.</span></span> <span data-ttu-id="5182f-147">Daha fazla bilgi için bkz: [XAML Namespace (x:) Dil özellikleri (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).</span><span class="sxs-lookup"><span data-stu-id="5182f-147">For more information, see [XAML Namespace (x:) Language Features (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5182f-148">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5182f-148">See Also</span></span>  
 [<span data-ttu-id="5182f-149">x: Subclass yönergesi</span><span class="sxs-lookup"><span data-stu-id="5182f-149">x:Subclass Directive</span></span>](../../../docs/framework/xaml-services/x-subclass-directive.md)  
 [<span data-ttu-id="5182f-150">XAML ve WPF için özel sınıflar</span><span class="sxs-lookup"><span data-stu-id="5182f-150">XAML and Custom Classes for WPF</span></span>](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [<span data-ttu-id="5182f-151">x: ClassModifier yönergesi</span><span class="sxs-lookup"><span data-stu-id="5182f-151">x:ClassModifier Directive</span></span>](../../../docs/framework/xaml-services/x-classmodifier-directive.md)  
 [<span data-ttu-id="5182f-152">WPF'den System.xaml'e geçirilen türler</span><span class="sxs-lookup"><span data-stu-id="5182f-152">Types Migrated from WPF to System.Xaml</span></span>](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)