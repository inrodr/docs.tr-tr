---
title: "ToolTip Denetim Türü için UI Otomasyon Desteği"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, ToolTip control type
- ToolTip control type
- control types, ToolTip
ms.assetid: c3779d78-3164-43ae-8dae-bfaeafffdd65
caps.latest.revision: "22"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 2040020ba32aed97c613260948f0772355c1287f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-support-for-the-tooltip-control-type"></a><span data-ttu-id="3cd9a-102">ToolTip Denetim Türü için UI Otomasyon Desteği</span><span class="sxs-lookup"><span data-stu-id="3cd9a-102">UI Automation Support for the ToolTip Control Type</span></span>
> [!NOTE]
>  <span data-ttu-id="3cd9a-103">Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3cd9a-104">Hakkında en yeni bilgiler için [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Otomasyon API: UI Otomasyonu](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="3cd9a-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="3cd9a-105">Bu konu aşağıdakiler hakkında bilgi sağlar [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ToolTip denetim türü için destek.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-105">This topic provides information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] support for the ToolTip control type.</span></span> <span data-ttu-id="3cd9a-106">İçinde [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], Denetim türü bir denetimi kullanmak için karşılaması gereken koşulları kümesidir <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> özelliği.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-106">In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], a control type is a set of conditions that a control must meet in order to use the <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> property.</span></span> <span data-ttu-id="3cd9a-107">Koşullar özel yönergeleri dahil [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ağaç yapısı, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] özellik değerlerini ve denetim düzenleri.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-107">The conditions include specific guidelines for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] property values and control patterns.</span></span>  
  
 <span data-ttu-id="3cd9a-108">Araç İpucu denetimlerinin metin içeren açılır pencereleri ' dir.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-108">Tool tip controls are pop-up windows that contain text.</span></span>  
  
 <span data-ttu-id="3cd9a-109">Aşağıdaki bölümlerde gerekli tanımlamak [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ağaç yapısı, özellikler, Denetim desenleri ve olayları ToolTip denetim türü için.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-109">The following sections define the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, properties, control patterns, and events for the ToolTip control type.</span></span> <span data-ttu-id="3cd9a-110">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Gereksinimleri tüm araç ipucu denetimleri için geçerli olup olmadığını [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], veya [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cd9a-110">The [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requirements apply to all tool tip controls, whether [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], or [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a><span data-ttu-id="3cd9a-111">Gerekli UI Otomasyon ağaç yapısı</span><span class="sxs-lookup"><span data-stu-id="3cd9a-111">Required UI Automation Tree Structure</span></span>  
 <span data-ttu-id="3cd9a-112">Denetim Görünüm ve içerik görünümünü aşağıdaki tabloda gösterilmektedir [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] araç ipucu ilgilidir ağaç denetler ve her bir görünümde bulunabilir açıklar.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-112">The following table depicts the control view and the content view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree that pertains to tool tip controls and describes what can be contained in each view.</span></span> <span data-ttu-id="3cd9a-113">Daha fazla bilgi için [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ağaç bkz [UI Otomasyon ağacına genel bakış](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3cd9a-113">For more information on the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree, see [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span></span>  
  
|<span data-ttu-id="3cd9a-114">Denetim Görünüm</span><span class="sxs-lookup"><span data-stu-id="3cd9a-114">Control View</span></span>|<span data-ttu-id="3cd9a-115">İçerik görünümü</span><span class="sxs-lookup"><span data-stu-id="3cd9a-115">Content View</span></span>|  
|------------------|------------------|  
|<span data-ttu-id="3cd9a-116">ToolTip</span><span class="sxs-lookup"><span data-stu-id="3cd9a-116">ToolTip</span></span><br /><br /> <span data-ttu-id="3cd9a-117">-Metin (0 veya daha fazla)</span><span class="sxs-lookup"><span data-stu-id="3cd9a-117">-   Text (0 or more)</span></span><br /><span data-ttu-id="3cd9a-118">-İmage (0 veya daha fazla)</span><span class="sxs-lookup"><span data-stu-id="3cd9a-118">-   Image (0 or more)</span></span>|<span data-ttu-id="3cd9a-119">ToolTip</span><span class="sxs-lookup"><span data-stu-id="3cd9a-119">ToolTip</span></span>|  
  
 <span data-ttu-id="3cd9a-120">Araç İpucu denetimleri görünür yalnızca içerik görünümünde [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klavye odağını alırsanız ağacı.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-120">Tool tip controls appear only in the Content View of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree if they can receive keyboard focus.</span></span> <span data-ttu-id="3cd9a-121">Aksi takdirde, araç ipucu 's bilgilerin tümünü edinilebilir `HelpTextProperty` üzerinde [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] için araç ipucu başvuran öğesi.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-121">Otherwise, all of the tool tip's information is available from the `HelpTextProperty` on the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element that the tool tip is referring to.</span></span>  
  
 <span data-ttu-id="3cd9a-122">Araç ipuçları için kendi bilgilerini başvuran Denetim ögesinin altında görünmelidir.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-122">Tool tips should appear beneath the control that their information is referring to.</span></span> <span data-ttu-id="3cd9a-123">İstemciler için dinleme gerekir `ToolTipOpenedEvent` bunlar tutarlı bir şekilde araç ipuçları içerdiği bilgi elde emin olmak için.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-123">Clients must listen for the `ToolTipOpenedEvent` to ensure that they consistently obtain information contained in tool tips.</span></span>  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a><span data-ttu-id="3cd9a-124">Gerekli UI Otomasyon özellikleri</span><span class="sxs-lookup"><span data-stu-id="3cd9a-124">Required UI Automation Properties</span></span>  
 <span data-ttu-id="3cd9a-125">Aşağıdaki tabloda [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , değer veya tanımı için araç ipucu denetimleri özellikle ilgili özellikler.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-125">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties whose value or definition is especially relevant to tool tip controls.</span></span> <span data-ttu-id="3cd9a-126">Hakkında daha fazla bilgi için [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] özellikleri, görmek [istemciler için UI Otomasyon özellikleri](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="3cd9a-126">For more information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties, see [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="3cd9a-127">Özelliği</span><span class="sxs-lookup"><span data-stu-id="3cd9a-127"> Property</span></span>|<span data-ttu-id="3cd9a-128">Değer</span><span class="sxs-lookup"><span data-stu-id="3cd9a-128">Value</span></span>|<span data-ttu-id="3cd9a-129">Notlar</span><span class="sxs-lookup"><span data-stu-id="3cd9a-129">Notes</span></span>|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|<span data-ttu-id="3cd9a-130">Notlarına bakın.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-130">See notes.</span></span>|<span data-ttu-id="3cd9a-131">Bu özelliğin değeri bir uygulamadaki tüm denetimler arasında benzersiz olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-131">The value of this property needs to be unique across all controls in an application.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|<span data-ttu-id="3cd9a-132">Notlarına bakın.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-132">See notes.</span></span>|<span data-ttu-id="3cd9a-133">Tam denetimi içeren en dıştaki dikdörtgen.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-133">The outermost rectangle that contains the whole control.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|<span data-ttu-id="3cd9a-134">Notlarına bakın.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-134">See notes.</span></span>|<span data-ttu-id="3cd9a-135">Tıklatılabilir noktası denetimi kapatmak araç ipucu parçası olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-135">The clickable point should be the part of the tool tip that will dismiss the control.</span></span> <span data-ttu-id="3cd9a-136">Bazı araç ipuçları bu yeteneği yoktur ve tıklatılabilir noktası olmaz.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-136">Some tool tips do not have this ability and will not have a clickable point.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|<span data-ttu-id="3cd9a-137">Notlarına bakın.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-137">See notes.</span></span>|<span data-ttu-id="3cd9a-138">Klavye odağı denetimi alamıyorsa, bu özelliği desteklemelidir.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-138">If the control can receive keyboard focus, it must support this property.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|<span data-ttu-id="3cd9a-139">Notlarına bakın.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-139">See notes.</span></span>|<span data-ttu-id="3cd9a-140">Araç İpucu içinde görüntülenen metin araç ipucunu denetimini adıdır.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-140">The name of the tool tip control is the text that is displayed within the tool tip.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|<span data-ttu-id="3cd9a-141">Araç İpucu denetimleri içeriklerini tarafından her zaman otomatik olarak etiketlenir.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-141">Tool tip controls are always self-labeled by their contents.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|<span data-ttu-id="3cd9a-142">ToolTip</span><span class="sxs-lookup"><span data-stu-id="3cd9a-142">ToolTip</span></span>|<span data-ttu-id="3cd9a-143">Bu değer tüm UI çerçeveler için aynıdır.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-143">This value is the same for all UI frameworks.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|<span data-ttu-id="3cd9a-144">"araç ipucu"</span><span class="sxs-lookup"><span data-stu-id="3cd9a-144">"tool tip"</span></span>|<span data-ttu-id="3cd9a-145">ToolTip denetim türü için karşılık gelen yerelleştirilmiş dize.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-145">Localized string corresponding to the ToolTip control type.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|<span data-ttu-id="3cd9a-146">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="3cd9a-146">Depends</span></span>|<span data-ttu-id="3cd9a-147">Araç ipucunu denetimini klavye odağını alırsanız içerik görünümünde ağacı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-147">If the tool tip control can receive keyboard focus, it must be in the Content View of the tree.</span></span> <span data-ttu-id="3cd9a-148">Yalnızca metin ise, sonra ortaya çıkan denetiminden HelpTextProperty olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-148">If it is text only, then it is available as the HelpTextProperty from the control that raised it.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|<span data-ttu-id="3cd9a-149">Doğru</span><span class="sxs-lookup"><span data-stu-id="3cd9a-149">True</span></span>|<span data-ttu-id="3cd9a-150">Araç ipucunu denetimini her zaman bir denetim olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-150">The tool tip control must always be a control.</span></span>|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a><span data-ttu-id="3cd9a-151">Gerekli UI Otomasyon denetim düzenleri</span><span class="sxs-lookup"><span data-stu-id="3cd9a-151">Required UI Automation Control Patterns</span></span>  
 <span data-ttu-id="3cd9a-152">Aşağıdaki tabloda [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] denetim düzenleri araç ipucu denetimleri tarafından desteklenmesi için gerekli.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-152">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] control patterns required to be supported by tool tip controls.</span></span> <span data-ttu-id="3cd9a-153">Denetim desenleri hakkında daha fazla bilgi için bkz: [UI Otomasyon denetim düzenlerine genel bakış](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3cd9a-153">For more information on control patterns, see [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span></span>  
  
|<span data-ttu-id="3cd9a-154">Denetim düzeni</span><span class="sxs-lookup"><span data-stu-id="3cd9a-154">Control Pattern</span></span>|<span data-ttu-id="3cd9a-155">Destek</span><span class="sxs-lookup"><span data-stu-id="3cd9a-155">Support</span></span>|<span data-ttu-id="3cd9a-156">Notlar</span><span class="sxs-lookup"><span data-stu-id="3cd9a-156">Notes</span></span>|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider>|<span data-ttu-id="3cd9a-157">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="3cd9a-157">Depends</span></span>|<span data-ttu-id="3cd9a-158">Kapalı böylece otomatik olarak bir kullanıcı Arabirimi öğesi tıklayarak kapatılabilir araç ipuçları WindowPattern'ı desteklemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-158">Tool tips that can be closed by clicking a UI item must support WindowPattern so that they can closed automatically.</span></span>|  
|<xref:System.Windows.Automation.Provider.ITextProvider>|<span data-ttu-id="3cd9a-159">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="3cd9a-159">Depends</span></span>|<span data-ttu-id="3cd9a-160">Gerekli olmamasına rağmen daha iyi erişilebilirlik için bir araç ipucunu denetimini metin denetim düzenini destekler.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-160">For better accessibility, a tool tip control can support the Text control pattern, although it is not required.</span></span> <span data-ttu-id="3cd9a-161">Metin denetim düzeni metin zengin stili ve öznitelikler (örneğin, rengi, kalın ve italik) olduğunda yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-161">The Text control pattern is useful when the text has rich style and attributes (for example, color, bold, and italics).</span></span>|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a><span data-ttu-id="3cd9a-162">Gerekli UI Otomasyon olayları</span><span class="sxs-lookup"><span data-stu-id="3cd9a-162">Required UI Automation Events</span></span>  
 <span data-ttu-id="3cd9a-163">Araç İpucu denetimleri gerekir Yükselt `ToolTipOpenedEvent` ekranda görüntülendiğinde.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-163">Tool tip controls must raise the `ToolTipOpenedEvent` when they appear on the screen.</span></span> <span data-ttu-id="3cd9a-164">Olay bir başvuru içerecektir [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] araç ipucu öğesidir.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-164">The event will include a reference to the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element of the tool tip itself.</span></span>  
  
 <span data-ttu-id="3cd9a-165">Aşağıdaki tabloda [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] olayları tüm araç ipucu denetimleri tarafından desteklenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-165">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] events required to be supported by all tool tip controls.</span></span> <span data-ttu-id="3cd9a-166">Olaylar hakkında daha fazla bilgi için bkz: [UI Otomasyonu olaylarına genel bakış](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3cd9a-166">For more information about events, see [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="3cd9a-167">Olay</span><span class="sxs-lookup"><span data-stu-id="3cd9a-167"> Event</span></span>|<span data-ttu-id="3cd9a-168">Destek</span><span class="sxs-lookup"><span data-stu-id="3cd9a-168">Support</span></span>|<span data-ttu-id="3cd9a-169">Notlar</span><span class="sxs-lookup"><span data-stu-id="3cd9a-169">Notes</span></span>|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextSelectionChangedEvent>|<span data-ttu-id="3cd9a-170">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="3cd9a-170">Depends</span></span>|<span data-ttu-id="3cd9a-171">Yok.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-171">None</span></span>|  
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextChangedEvent>|<span data-ttu-id="3cd9a-172">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="3cd9a-172">Depends</span></span>|<span data-ttu-id="3cd9a-173">Yok.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-173">None</span></span>|  
|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowClosedEvent>|<span data-ttu-id="3cd9a-174">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="3cd9a-174">Depends</span></span>|<span data-ttu-id="3cd9a-175">Yok.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-175">None</span></span>|  
|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowOpenedEvent>|<span data-ttu-id="3cd9a-176">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="3cd9a-176">Depends</span></span>|<span data-ttu-id="3cd9a-177">Yok.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-177">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ToolTipOpenedEvent>|<span data-ttu-id="3cd9a-178">Gerekli</span><span class="sxs-lookup"><span data-stu-id="3cd9a-178">Required</span></span>|<span data-ttu-id="3cd9a-179">Yok.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-179">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ToolTipClosedEvent>|<span data-ttu-id="3cd9a-180">Gerekli</span><span class="sxs-lookup"><span data-stu-id="3cd9a-180">Required</span></span>|<span data-ttu-id="3cd9a-181">Yok.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-181">None</span></span>|  
|<span data-ttu-id="3cd9a-182"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>özellik değişti olayı.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-182"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> property-changed event.</span></span>|<span data-ttu-id="3cd9a-183">Gerekli</span><span class="sxs-lookup"><span data-stu-id="3cd9a-183">Required</span></span>|<span data-ttu-id="3cd9a-184">Yok.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-184">None</span></span>|  
|<span data-ttu-id="3cd9a-185"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>özellik değişti olayı.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-185"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> property-changed event.</span></span>|<span data-ttu-id="3cd9a-186">Gerekli</span><span class="sxs-lookup"><span data-stu-id="3cd9a-186">Required</span></span>|<span data-ttu-id="3cd9a-187">Yok.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-187">None</span></span>|  
|<span data-ttu-id="3cd9a-188"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>özellik değişti olayı.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-188"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> property-changed event.</span></span>|<span data-ttu-id="3cd9a-189">Gerekli</span><span class="sxs-lookup"><span data-stu-id="3cd9a-189">Required</span></span>|<span data-ttu-id="3cd9a-190">Yok.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-190">None</span></span>|  
|<span data-ttu-id="3cd9a-191"><xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>özellik değişti olayı.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-191"><xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> property-changed event.</span></span>|<span data-ttu-id="3cd9a-192">Gerekli</span><span class="sxs-lookup"><span data-stu-id="3cd9a-192">Required</span></span>|<span data-ttu-id="3cd9a-193">Yok.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-193">None</span></span>|  
|<span data-ttu-id="3cd9a-194"><xref:System.Windows.Automation.WindowPatternIdentifiers.WindowVisualStateProperty>özellik değişti olayı.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-194"><xref:System.Windows.Automation.WindowPatternIdentifiers.WindowVisualStateProperty> property-changed event.</span></span>|<span data-ttu-id="3cd9a-195">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="3cd9a-195">Depends</span></span>|<span data-ttu-id="3cd9a-196">Yok.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-196">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|<span data-ttu-id="3cd9a-197">Gerekli</span><span class="sxs-lookup"><span data-stu-id="3cd9a-197">Required</span></span>|<span data-ttu-id="3cd9a-198">Yok.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-198">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|<span data-ttu-id="3cd9a-199">Gerekli</span><span class="sxs-lookup"><span data-stu-id="3cd9a-199">Required</span></span>|<span data-ttu-id="3cd9a-200">Yok.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-200">None</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3cd9a-201">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3cd9a-201">See Also</span></span>  
 <xref:System.Windows.Automation.ControlType.ToolTip>  
 [<span data-ttu-id="3cd9a-202">UI Otomasyon denetim türlerine genel bakış</span><span class="sxs-lookup"><span data-stu-id="3cd9a-202">UI Automation Control Types Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [<span data-ttu-id="3cd9a-203">UI Otomasyon genel bakış</span><span class="sxs-lookup"><span data-stu-id="3cd9a-203">UI Automation Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-overview.md)