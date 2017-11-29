---
title: "Nasıl yapılır: Bir Windows Formunda Windows Gezgini Stilinde bir Arabirim Oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 96f2ca8189d6840bc68f063ef9b97539c24b0e6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="a6adb-102">Nasıl yapılır: Bir Windows Formunda Windows Gezgini Stilinde bir Arabirim Oluşturma</span><span class="sxs-lookup"><span data-stu-id="a6adb-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="a6adb-103">Windows Gezgini'nde bir ortak kullanıcı arabirimi uygulamalar için kendi hazır benzerlik nedeniyle seçimdir.</span><span class="sxs-lookup"><span data-stu-id="a6adb-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>  
  
 <span data-ttu-id="a6adb-104">Esas olarak, Windows Gezgini olan bir <xref:System.Windows.Forms.TreeView> denetim ve <xref:System.Windows.Forms.ListView> ayrı Panel denetimi.</span><span class="sxs-lookup"><span data-stu-id="a6adb-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="a6adb-105">Paneller Bölümlendirici tarafından yeniden boyutlandırılabilir hale getirilir.</span><span class="sxs-lookup"><span data-stu-id="a6adb-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="a6adb-106">Bu denetimlerin düzenlenmesi görüntüleme ve bilgi gözatma için çok etkili olur.</span><span class="sxs-lookup"><span data-stu-id="a6adb-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>  
  
 <span data-ttu-id="a6adb-107">Aşağıdaki adımlar Windows Explorer benzeri formu denetimlerini düzenlemek nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="a6adb-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="a6adb-108">Windows Gezgini uygulama dosyasına göz atma işlevselliğini ekleme gösterme.</span><span class="sxs-lookup"><span data-stu-id="a6adb-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6adb-109">Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="a6adb-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a6adb-110">Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.</span><span class="sxs-lookup"><span data-stu-id="a6adb-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a6adb-111">Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="a6adb-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="a6adb-112">Bir Windows Gezgini stilinde Windows Form oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="a6adb-112">To create a Windows Explorer-style Windows Form</span></span>  
  
1.  <span data-ttu-id="a6adb-113">Yeni bir Windows uygulama projesi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="a6adb-113">Create a new Windows Application project.</span></span> <span data-ttu-id="a6adb-114">Ayrıntılar için bkz [nasıl yapılır: bir Windows uygulaması projesi oluşturduğunuzda](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="a6adb-114">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="a6adb-115">Gelen **araç**:</span><span class="sxs-lookup"><span data-stu-id="a6adb-115">From the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="a6adb-116">Sürükleme bir <xref:System.Windows.Forms.SplitContainer> Formunuza denetim.</span><span class="sxs-lookup"><span data-stu-id="a6adb-116">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>  
  
    2.  <span data-ttu-id="a6adb-117">Sürükleme bir <xref:System.Windows.Forms.TreeView> içine kontrol **SplitterPanel1** (panelini <xref:System.Windows.Forms.SplitContainer> işaretlenmiş denetim **Panel1**).</span><span class="sxs-lookup"><span data-stu-id="a6adb-117">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>  
  
    3.  <span data-ttu-id="a6adb-118">Sürükleme bir <xref:System.Windows.Forms.ListView> içine kontrol **SplitterPanel2** (panelini <xref:System.Windows.Forms.SplitContainer> işaretlenmiş denetim **Panel2**).</span><span class="sxs-lookup"><span data-stu-id="a6adb-118">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>  
  
3.  <span data-ttu-id="a6adb-119">Tüm üç denetimleri CTRL tuşuna basarak ve bunları sırayla tıklayarak seçin.</span><span class="sxs-lookup"><span data-stu-id="a6adb-119">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="a6adb-120">Seçtiğinizde, <xref:System.Windows.Forms.SplitContainer> denetlemek, paneller yerine ayırıcıyı'ı tıklatın.</span><span class="sxs-lookup"><span data-stu-id="a6adb-120">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a6adb-121">Kullanmayın **Tümünü Seç** komutunu **Düzenle** menüsü.</span><span class="sxs-lookup"><span data-stu-id="a6adb-121">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="a6adb-122">Bunu yaparsanız, sonraki adımda gerekli özellik görüntülenmez **özellikleri** penceresi.</span><span class="sxs-lookup"><span data-stu-id="a6adb-122">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>  
  
4.  <span data-ttu-id="a6adb-123">İçinde **özellikleri** penceresindeki ayarlayın <xref:System.Windows.Forms.SplitContainer.Dock%2A> özelliğine <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="a6adb-123">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5.  <span data-ttu-id="a6adb-124">Uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="a6adb-124">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="a6adb-125">Form, Windows Gezgini benzer iki parçalı kullanıcı arabirimi görüntüler.</span><span class="sxs-lookup"><span data-stu-id="a6adb-125">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a6adb-126">Bölümlendirici sürüklediğinizde, paneller kendilerini yeniden boyutlandırın.</span><span class="sxs-lookup"><span data-stu-id="a6adb-126">When you drag the splitter, the panels resize themselves.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6adb-127">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a6adb-127">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 [<span data-ttu-id="a6adb-128">Nasıl yapılır: Windows formları ile çok bölmeli kullanıcı arabirimi oluşturma</span><span class="sxs-lookup"><span data-stu-id="a6adb-128">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 [<span data-ttu-id="a6adb-129">Nasıl yapılır: yeniden boyutlandırma ve bölünmüş pencerede davranışı konumlandırma tanımlayın</span><span class="sxs-lookup"><span data-stu-id="a6adb-129">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 [<span data-ttu-id="a6adb-130">Nasıl yapılır: pencereyi yatay bölme</span><span class="sxs-lookup"><span data-stu-id="a6adb-130">How to: Split a Window Horizontally</span></span>](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 [<span data-ttu-id="a6adb-131">SplitContainer denetimi</span><span class="sxs-lookup"><span data-stu-id="a6adb-131">SplitContainer Control</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)