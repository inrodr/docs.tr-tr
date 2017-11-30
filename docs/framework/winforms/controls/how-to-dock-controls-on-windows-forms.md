---
title: "Nasıl yapılır: Windows Formlarına Denetimleri Yerleştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4897a195dcafb8264bbab619f1a46118a829f44e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="60add-102">Nasıl yapılır: Windows Formlarına Denetimleri Yerleştirme</span><span class="sxs-lookup"><span data-stu-id="60add-102">How to: Dock Controls on Windows Forms</span></span>
<span data-ttu-id="60add-103">Denetimleri form kenarlarına yerleştirme ya da bunları denetimin kapsayıcı (bir form veya bir kapsayıcı denetiminin) doldurun.</span><span class="sxs-lookup"><span data-stu-id="60add-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="60add-104">Örneğin, Windows Gezgini noktalarını kendi <xref:System.Windows.Forms.TreeView> pencerenin sol tarafında denetimine ve kendi <xref:System.Windows.Forms.ListView> pencerenin sağ tarafında denetimine.</span><span class="sxs-lookup"><span data-stu-id="60add-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="60add-105">Kullanım <xref:System.Windows.Forms.Control.Dock%2A> takma modunu tanımlamak tüm görünür Windows Forms denetimleri için özelliği.</span><span class="sxs-lookup"><span data-stu-id="60add-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60add-106">Denetimleri ters z-sırada sabitlenir.</span><span class="sxs-lookup"><span data-stu-id="60add-106">Controls are docked in reverse z-order.</span></span>  
  
 <span data-ttu-id="60add-107"><xref:System.Windows.Forms.Control.Dock%2A> Özelliği etkileşime <xref:System.Windows.Forms.Control.AutoSize%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="60add-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="60add-108">Daha fazla bilgi için bkz: [AutoSize özelliğine genel bakış](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="60add-108">For more information, see [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span></span>  
  
### <a name="to-dock-a-control"></a><span data-ttu-id="60add-109">Bir denetim sabitlemek için</span><span class="sxs-lookup"><span data-stu-id="60add-109">To dock a control</span></span>  
  
1.  <span data-ttu-id="60add-110">Sabitlemek istediğiniz denetimi seçin.</span><span class="sxs-lookup"><span data-stu-id="60add-110">Select the control that you want to dock.</span></span>  
  
2.  <span data-ttu-id="60add-111">Özellikler penceresinde sağındaki oku <xref:System.Windows.Forms.Control.Dock%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="60add-111">In the Properties window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="60add-112">Bir düzenleyici kutuları kenarları ve form merkezini temsil eden bir dizi gösteren görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="60add-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>  
  
3.  <span data-ttu-id="60add-113">Denetimi yerleştirmek istediğiniz formun kenarına temsil eden düğmesini tıklatın.</span><span class="sxs-lookup"><span data-stu-id="60add-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="60add-114">Denetimin form veya kapsayıcı denetiminin içeriğini doldurmak için merkezi kutuyu tıklatın.</span><span class="sxs-lookup"><span data-stu-id="60add-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="60add-115">Tıklatın **(hiçbiri)** yerleştirme devre dışı bırakmak için.</span><span class="sxs-lookup"><span data-stu-id="60add-115">Click **(none)** to disable docking.</span></span>  
  
     <span data-ttu-id="60add-116">Denetim yerleşik kenar sınırlarına uyacak şekilde otomatik olarak boyutlandırılır.</span><span class="sxs-lookup"><span data-stu-id="60add-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="60add-117">Devralınan denetimleri olmalıdır `Protected` yerleşik için.</span><span class="sxs-lookup"><span data-stu-id="60add-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="60add-118">Bir denetim erişim düzeyini değiştirmek için ayarlayın, **değiştiricisi** Özellikleri penceresinde özelliği.</span><span class="sxs-lookup"><span data-stu-id="60add-118">To change the access level of a control, set its **Modifier** property in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60add-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="60add-119">See Also</span></span>  
 [<span data-ttu-id="60add-120">Windows Forms denetimleri</span><span class="sxs-lookup"><span data-stu-id="60add-120">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="60add-121">Windows Forms'ta denetimleri düzenleme</span><span class="sxs-lookup"><span data-stu-id="60add-121">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="60add-122">Ayrı Windows Forms denetimlerini etiketleme ve kısayollarını sunma</span><span class="sxs-lookup"><span data-stu-id="60add-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="60add-123">Windows Forms'ta kullanılacak denetimler</span><span class="sxs-lookup"><span data-stu-id="60add-123">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="60add-124">Windows Forms denetimleri işlevi</span><span class="sxs-lookup"><span data-stu-id="60add-124">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [<span data-ttu-id="60add-125">Nasıl yapılır: FlowLayoutPanel denetiminde alt denetimleri sabitleme ve yerleştirme</span><span class="sxs-lookup"><span data-stu-id="60add-125">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="60add-126">Nasıl yapılır: TableLayoutPanel denetiminde alt denetimleri sabitleme ve yerleştirme</span><span class="sxs-lookup"><span data-stu-id="60add-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="60add-127">AutoSize özelliğine genel bakış</span><span class="sxs-lookup"><span data-stu-id="60add-127">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [<span data-ttu-id="60add-128">Nasıl yapılır: Windows formlarında denetimleri sabitleme</span><span class="sxs-lookup"><span data-stu-id="60add-128">How to: Anchor Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)