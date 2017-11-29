---
title: "İzlenecek yol: Visual Basic İle Bileşik Denetim Yazma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Visual Basic]
- user controls [Visual Basic]
- UserControl class [Windows Forms], walkthroughs
- user controls [Windows Forms], creating with Visual Basic
- controls [Windows Forms], composite controls
- composite controls [Windows Forms], creating
- custom controls [Windows Forms], creating
ms.assetid: f50e270e-4db2-409a-8319-6db6ca5c7daf
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c86a3d420b85c1287597cda738c6d72f0433d0f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-authoring-a-composite-control-with-visual-basic"></a><span data-ttu-id="14b66-102">İzlenecek yol: Visual Basic İle Bileşik Denetim Yazma</span><span class="sxs-lookup"><span data-stu-id="14b66-102">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>
<span data-ttu-id="14b66-103">Bileşik denetimler olarak özel grafik arabirimler oluşturulabilir yeniden ve bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="14b66-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="14b66-104">Bileşik Denetim aslında bir görsel gösterimi ile bileşenidir.</span><span class="sxs-lookup"><span data-stu-id="14b66-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="14b66-105">Bu nedenle, bir veya daha fazla Windows Forms denetimleri, bileşenleri veya kullanıcı girişini doğrulama, görüntü özelliklerini değiştirme veya yazar tarafından gerekli diğer görevleri gerçekleştirme işlevselliğini genişletebildiği kod bloklarını oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="14b66-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="14b66-106">Bileşik denetimler, diğer denetimler aynı şekilde Windows Forms'ta yerleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="14b66-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="14b66-107">Bu kılavuzun ilk bölümünde oluşturduğunuz adlı basit bir bileşik denetim `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="14b66-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="14b66-108">İzlenecek yol ikinci bölümünde, işlevselliğini genişletmek `ctlClock` devralma yoluyla.</span><span class="sxs-lookup"><span data-stu-id="14b66-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14b66-109">Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="14b66-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="14b66-110">Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.</span><span class="sxs-lookup"><span data-stu-id="14b66-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="14b66-111">Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="14b66-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="14b66-112">Projeyi Oluşturma</span><span class="sxs-lookup"><span data-stu-id="14b66-112">Creating the Project</span></span>  
 <span data-ttu-id="14b66-113">Yeni bir proje oluşturduğunuzda, kök ad alanı, derleme adı ve proje adı ayarlayabilir ve varsayılan bileşen doğru ad alanında olduğundan emin olmak için adı belirtin.</span><span class="sxs-lookup"><span data-stu-id="14b66-113">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>  
  
#### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="14b66-114">CtlClockLib denetim kitaplığı ve ctlClock denetimi oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="14b66-114">To create the ctlClockLib control library and the ctlClock control</span></span>  
  
1.  <span data-ttu-id="14b66-115">Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje** açmak için **yeni proje** iletişim kutusu.</span><span class="sxs-lookup"><span data-stu-id="14b66-115">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="14b66-116">Listesinden [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] projeleri, select **Windows Denetim Kitaplığı** proje şablonu, türü `ctlClockLib` içinde **adı** kutusuna ve ardından **Tamam**.</span><span class="sxs-lookup"><span data-stu-id="14b66-116">From the list of [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] projects, select the **Windows Control Library** project template, type `ctlClockLib` in the **Name** box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="14b66-117">Proje adı `ctlClockLib`, kök ad alanı için varsayılan olarak da atanmış.</span><span class="sxs-lookup"><span data-stu-id="14b66-117">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="14b66-118">Kök ad derleme bileşenlerinde adlarını nitelemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="14b66-118">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="14b66-119">Örneğin, iki derleme adlı bileşenleri sağlarsanız `ctlClock`, belirtebilirsiniz, `ctlClock` bileşenini kullanarak`ctlClockLib.ctlClock.`</span><span class="sxs-lookup"><span data-stu-id="14b66-119">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>  
  
3.  <span data-ttu-id="14b66-120">Çözüm Gezgini'nde sağ **UserControl1.vb**ve ardından **yeniden adlandırma**.</span><span class="sxs-lookup"><span data-stu-id="14b66-120">In Solution Explorer, right-click **UserControl1.vb**, and then click **Rename**.</span></span> <span data-ttu-id="14b66-121">Dosya adını değiştirmek `ctlClock.vb`.</span><span class="sxs-lookup"><span data-stu-id="14b66-121">Change the file name to `ctlClock.vb`.</span></span> <span data-ttu-id="14b66-122">Tıklatın **Evet** düğmesini code öğesi "UserControl1" yapılan tüm başvuruları yeniden adlandırmak istediğiniz sorulduğunda.</span><span class="sxs-lookup"><span data-stu-id="14b66-122">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="14b66-123">Varsayılan olarak, bileşik denetim devraldığı <xref:System.Windows.Forms.UserControl> sistem tarafından sağlanan sınıfı.</span><span class="sxs-lookup"><span data-stu-id="14b66-123">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="14b66-124"><xref:System.Windows.Forms.UserControl> Sınıf tarafından tüm bileşik denetimler gerekli işlevselliği sunar ve standart yöntemleri ve özellikleri uygular.</span><span class="sxs-lookup"><span data-stu-id="14b66-124">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>  
  
4.  <span data-ttu-id="14b66-125">Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet** projeyi kaydetmek için.</span><span class="sxs-lookup"><span data-stu-id="14b66-125">On the **File** menu, click **Save All** to save the project.</span></span>  
  
## <a name="adding-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="14b66-126">Windows ekleme denetimleri ve bileşenleri bileşik denetim için</span><span class="sxs-lookup"><span data-stu-id="14b66-126">Adding Windows Controls and Components to the Composite Control</span></span>  
 <span data-ttu-id="14b66-127">Görsel bir arabirim bileşik denetim önemli bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="14b66-127">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="14b66-128">Bu görsel arabirimi bir veya daha fazla Windows denetimleri Tasarımcı yüzeyine eklenmesi tarafından uygulanır.</span><span class="sxs-lookup"><span data-stu-id="14b66-128">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="14b66-129">Aşağıdaki örnekte Windows denetimleri bileşik denetime birleştirme ve işlevselliği uygulamak için kod yazma.</span><span class="sxs-lookup"><span data-stu-id="14b66-129">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>  
  
#### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="14b66-130">Bir etiket ve bir Zamanlayıcı, bileşik denetim eklemek için</span><span class="sxs-lookup"><span data-stu-id="14b66-130">To add a Label and a Timer to your composite control</span></span>  
  
1.  <span data-ttu-id="14b66-131">Çözüm Gezgini'nde sağ **ctlClock.vb**ve ardından **Görünüm Tasarımcısı**.</span><span class="sxs-lookup"><span data-stu-id="14b66-131">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Designer**.</span></span>  
  
2.  <span data-ttu-id="14b66-132">Araç kutusunda genişletin **ortak denetimler** düğümü ve çift tıklatarak **etiket**.</span><span class="sxs-lookup"><span data-stu-id="14b66-132">In the Toolbox, expand the **Common Controls** node, and then double-click **Label**.</span></span>  
  
     <span data-ttu-id="14b66-133">A <xref:System.Windows.Forms.Label> adlı Denetim `Label1` Tasarımcı yüzeyine denetiminizde eklenir.</span><span class="sxs-lookup"><span data-stu-id="14b66-133">A <xref:System.Windows.Forms.Label> control named `Label1` is added to your control on the designer surface.</span></span>  
  
3.  <span data-ttu-id="14b66-134">Tasarımcısı'nda tıklayın **Label1**.</span><span class="sxs-lookup"><span data-stu-id="14b66-134">In the designer, click **Label1**.</span></span> <span data-ttu-id="14b66-135">Özellikler penceresinde aşağıdaki özellikleri ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="14b66-135">In the Properties window, set the following properties.</span></span>  
  
    |<span data-ttu-id="14b66-136">Özellik</span><span class="sxs-lookup"><span data-stu-id="14b66-136">Property</span></span>|<span data-ttu-id="14b66-137">Değiştirin</span><span class="sxs-lookup"><span data-stu-id="14b66-137">Change to</span></span>|  
    |--------------|---------------|  
    |<span data-ttu-id="14b66-138">**Ad**</span><span class="sxs-lookup"><span data-stu-id="14b66-138">**Name**</span></span>|`lblDisplay`|  
    |<span data-ttu-id="14b66-139">**Metin**</span><span class="sxs-lookup"><span data-stu-id="14b66-139">**Text**</span></span>|`(blank space)`|  
    |<span data-ttu-id="14b66-140">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="14b66-140">**TextAlign**</span></span>|`MiddleCenter`|  
    |<span data-ttu-id="14b66-141">**Font.Size**</span><span class="sxs-lookup"><span data-stu-id="14b66-141">**Font.Size**</span></span>|`14`|  
  
4.  <span data-ttu-id="14b66-142">İçinde **araç**, genişletin **bileşenleri** düğümü ve çift tıklatarak **Zamanlayıcı**.</span><span class="sxs-lookup"><span data-stu-id="14b66-142">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>  
  
     <span data-ttu-id="14b66-143">Çünkü bir <xref:System.Windows.Forms.Timer> bir bileşen olan çalışma zamanında görsel gösterimi bulunmaz.</span><span class="sxs-lookup"><span data-stu-id="14b66-143">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="14b66-144">Bu nedenle, Tasarımcı yüzeyine, ancak yerine tasarımcıda bileşeni (tasarımcı yüzeyine altındaki bir Tepsisi) denetimleriyle görünmez.</span><span class="sxs-lookup"><span data-stu-id="14b66-144">Therefore, it does not appear with the controls on the designer surface, but rather in the Component Designer (a tray at the bottom of the designer surface).</span></span>  
  
5.  <span data-ttu-id="14b66-145">Bileşen Tasarımcısı'nda tıklayın **Süreölçer1**ve ardından <xref:System.Windows.Forms.Timer.Interval%2A> özelliğine `1000` ve <xref:System.Windows.Forms.Timer.Enabled%2A> özelliğine `True`.</span><span class="sxs-lookup"><span data-stu-id="14b66-145">In the Component Designer, click **Timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `True`.</span></span>  
  
     <span data-ttu-id="14b66-146"><xref:System.Windows.Forms.Timer.Interval%2A> Özelliği ile Zamanlayıcı bileşeni işaretlerini sıklığı denetler.</span><span class="sxs-lookup"><span data-stu-id="14b66-146">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the timer component ticks.</span></span> <span data-ttu-id="14b66-147">Her zaman `Timer1` çizgilerine, bunu çalışan kodu `Timer1_Tick` olay.</span><span class="sxs-lookup"><span data-stu-id="14b66-147">Each time `Timer1` ticks, it runs the code in the `Timer1_Tick` event.</span></span> <span data-ttu-id="14b66-148">Aralık çizgilerine arasındaki milisaniye sayısını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="14b66-148">The interval represents the number of milliseconds between ticks.</span></span>  
  
6.  <span data-ttu-id="14b66-149">Bileşen tasarımcısında çift **Süreölçer1** gitmek için `Timer1_Tick` olayı `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="14b66-149">In the Component Designer, double-click **Timer1** to go to the `Timer1_Tick` event for `ctlClock`.</span></span>  
  
7.  <span data-ttu-id="14b66-150">Aşağıdaki kod örneği benzer şekilde kodu değiştirin.</span><span class="sxs-lookup"><span data-stu-id="14b66-150">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="14b66-151">Gelen erişim değiştiricisi değiştirdiğinizden emin olun `Private` için `Protected`.</span><span class="sxs-lookup"><span data-stu-id="14b66-151">Be sure to change the access modifier from `Private` to `Protected`.</span></span>  
  
    ```vb  
    Protected Sub Timer1_Tick(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles Timer1.Tick  
        ' Causes the label to display the current time.    
        lblDisplay.Text = Format(Now, "hh:mm:ss")  
    End Sub  
    ```  
  
     <span data-ttu-id="14b66-152">Bu kod gösterilecek geçerli saati neden olacak `lblDisplay`.</span><span class="sxs-lookup"><span data-stu-id="14b66-152">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="14b66-153">Çünkü aralığı `Timer1` ayarlandı `1000`, böylece her saniye geçerli saati güncelleştiriliyor her bin milisaniyede bu olay meydana gelir.</span><span class="sxs-lookup"><span data-stu-id="14b66-153">Because the interval of `Timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>  
  
8.  <span data-ttu-id="14b66-154">Geçersiz kılınabilir olacak şekilde değiştirin.</span><span class="sxs-lookup"><span data-stu-id="14b66-154">Modify the method to be overridable.</span></span> <span data-ttu-id="14b66-155">Daha fazla bilgi için aşağıdaki "Devralan bir kullanıcı denetimi" bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="14b66-155">For more information, see the "Inheriting from a User Control" section below.</span></span>  
  
    ```vb  
    Protected Overridable Sub Timer1_Tick(ByVal sender As Object, ByVal _  
        e As System.EventArgs) Handles Timer1.Tick  
    ```  
  
9. <span data-ttu-id="14b66-156">Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet** projeyi kaydetmek için.</span><span class="sxs-lookup"><span data-stu-id="14b66-156">On the **File** menu, click **Save All** to save the project.</span></span>  
  
## <a name="adding-properties-to-the-composite-control"></a><span data-ttu-id="14b66-157">Bileşik Denetim Özellikler ekleme</span><span class="sxs-lookup"><span data-stu-id="14b66-157">Adding Properties to the Composite Control</span></span>  
 <span data-ttu-id="14b66-158">Saat denetiminizi şimdi yalıtan bir <xref:System.Windows.Forms.Label> denetim ve <xref:System.Windows.Forms.Timer> bileşeni, her biri kendi devralınmış özellikler kümesi.</span><span class="sxs-lookup"><span data-stu-id="14b66-158">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="14b66-159">Bu denetimlerin ayrı ayrı özellikler denetiminizi sonraki kullanıcılara erişilemeyecek olsa da, oluşturabilir ve uygun kod bloklarını yazarak özel özelliklerini ortaya.</span><span class="sxs-lookup"><span data-stu-id="14b66-159">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="14b66-160">Aşağıdaki yordamda, arka plan ve metin rengini değiştirmek kullanıcının denetiminizi özellikler ekleyeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="14b66-160">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>  
  
#### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="14b66-161">Bir özellik için bileşik denetim eklemek için</span><span class="sxs-lookup"><span data-stu-id="14b66-161">To add a property to your composite control</span></span>  
  
1.  <span data-ttu-id="14b66-162">Çözüm Gezgini'nde sağ **ctlClock.vb**ve ardından **görünümü kodu**.</span><span class="sxs-lookup"><span data-stu-id="14b66-162">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Code**.</span></span>  
  
     <span data-ttu-id="14b66-163">Kod Düzenleyicisi'ni denetlemek için açılır.</span><span class="sxs-lookup"><span data-stu-id="14b66-163">The Code Editor for your control opens.</span></span>  
  
2.  <span data-ttu-id="14b66-164">Bulun `Public Class ctlClock` deyimi.</span><span class="sxs-lookup"><span data-stu-id="14b66-164">Locate the `Public Class ctlClock` statement.</span></span> <span data-ttu-id="14b66-165">Altında aşağıdaki kodu yazın.</span><span class="sxs-lookup"><span data-stu-id="14b66-165">Beneath it, type the following code.</span></span>  
  
    ```vb  
    Private colFColor as Color  
    Private colBColor as Color  
    ```  
  
     <span data-ttu-id="14b66-166">Bu deyimler oluşturmak üzere olduğunuz özelliklerinin değerlerini depolamak için kullanacağı özel değişkenler oluşturun.</span><span class="sxs-lookup"><span data-stu-id="14b66-166">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>  
  
3.  <span data-ttu-id="14b66-167">Adım 2 ' değişken bildirimleri altına aşağıdaki kodu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="14b66-167">Insert the following code beneath the variable declarations from step 2.</span></span>  
  
    ```vb  
    ' Declares the name and type of the property.  
    Property ClockBackColor() as Color  
        ' Retrieves the value of the private variable colBColor.  
        Get  
            Return colBColor  
        End Get  
        ' Stores the selected value in the private variable colBColor, and   
        ' updates the background color of the label control lblDisplay.  
        Set(ByVal value as Color)  
            colBColor = value  
            lblDisplay.BackColor = colBColor     
        End Set  
  
    End Property  
    ' Provides a similar set of instructions for the foreground color.  
    Property ClockForeColor() as Color  
        Get  
            Return colFColor  
        End Get  
        Set(ByVal value as Color)  
            colFColor = value  
            lblDisplay.ForeColor = colFColor  
        End Set  
    End Property  
    ```  
  
     <span data-ttu-id="14b66-168">Önceki kod iki özel özellikler yapar `ClockForeColor` ve `ClockBackColor`, çağırma tarafından bu denetimin sonraki kullanıcıların kullanımına `Property` deyimi.</span><span class="sxs-lookup"><span data-stu-id="14b66-168">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control by invoking the `Property` statement.</span></span> <span data-ttu-id="14b66-169">`Get` Ve `Set` deyimleri, depolama ve alma, işlevselliği uygulamak için kodu yanı sıra özellik değeri, özellik için uygun için sağlar.</span><span class="sxs-lookup"><span data-stu-id="14b66-169">The `Get` and `Set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>  
  
4.  <span data-ttu-id="14b66-170">Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet** projeyi kaydetmek için.</span><span class="sxs-lookup"><span data-stu-id="14b66-170">On the **File** menu, click **Save All** to save the project.</span></span>  
  
## <a name="testing-the-control"></a><span data-ttu-id="14b66-171">Denetim test etme</span><span class="sxs-lookup"><span data-stu-id="14b66-171">Testing the Control</span></span>  
 <span data-ttu-id="14b66-172">Denetimleri tek başına projeleri değildir; bir kapsayıcıda barındırılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="14b66-172">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="14b66-173">Denetimin çalışma zamanı davranışını sınama ve özellikleriyle birlikte çalışma **UserControl Test kapsayıcısı**.</span><span class="sxs-lookup"><span data-stu-id="14b66-173">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="14b66-174">Daha fazla bilgi için bkz: [nasıl yapılır: bir UserControl denetiminin çalışma zamanı davranışını sınama](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="14b66-174">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
#### <a name="to-test-your-control"></a><span data-ttu-id="14b66-175">Denetim sınamak için</span><span class="sxs-lookup"><span data-stu-id="14b66-175">To test your control</span></span>  
  
1.  <span data-ttu-id="14b66-176">Projeyi derlemek ve denetiminizin çalıştırmak için F5 tuşuna basın **UserControl Test kapsayıcısı**.</span><span class="sxs-lookup"><span data-stu-id="14b66-176">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>  
  
2.  <span data-ttu-id="14b66-177">Test kapsayıcının özellik kılavuzunda seçin `ClockBackColor` özelliği ve renk paletini görüntülemek için açılan oku tıklatın.</span><span class="sxs-lookup"><span data-stu-id="14b66-177">In the test container's property grid, select the `ClockBackColor` property, and then click the drop-down arrow to display the color palette.</span></span>  
  
3.  <span data-ttu-id="14b66-178">Bir renk tıklayarak seçin.</span><span class="sxs-lookup"><span data-stu-id="14b66-178">Choose a color by clicking it.</span></span>  
  
     <span data-ttu-id="14b66-179">Denetim arka plan rengini seçtiğiniz renge dönüşür.</span><span class="sxs-lookup"><span data-stu-id="14b66-179">The background color of your control changes to the color you selected.</span></span>  
  
4.  <span data-ttu-id="14b66-180">Doğrulamak için benzer bir olay dizisi kullanmak `ClockForeColor` özelliği beklendiği gibi çalışmıyor.</span><span class="sxs-lookup"><span data-stu-id="14b66-180">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>  
  
5.  <span data-ttu-id="14b66-181">Tıklatın **kapatmak** kapatmak için **UserControl Test kapsayıcısı**.</span><span class="sxs-lookup"><span data-stu-id="14b66-181">Click **Close** to close the **UserControl Test Container**.</span></span>  
  
     <span data-ttu-id="14b66-182">Bu bölümde ve önceki bölümlerde, bileşenleri ve Windows denetimleri nasıl birleştirileceğini gördünüz kodla ve paketleme bileşik denetim biçiminde özel işlevsellik sağlar.</span><span class="sxs-lookup"><span data-stu-id="14b66-182">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="14b66-183">Bileşik Denetim ve onu tamamlandıktan sonra Denetim test etme özelliklerinde kullanıma sunmak öğrendiniz.</span><span class="sxs-lookup"><span data-stu-id="14b66-183">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="14b66-184">Sonraki bölümde nasıl kullanarak bir devralınan bileşik denetim oluşturulacağını öğreneceksiniz `ctlClock` temel olarak.</span><span class="sxs-lookup"><span data-stu-id="14b66-184">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>  
  
## <a name="inheriting-from-a-composite-control"></a><span data-ttu-id="14b66-185">Bileşik denetimden devralma</span><span class="sxs-lookup"><span data-stu-id="14b66-185">Inheriting from a Composite Control</span></span>  
 <span data-ttu-id="14b66-186">Önceki bölümlerde Windows denetimleri, bileşenleri ve kod yeniden kullanılabilir bileşik denetimlere birleştirmek öğrendiniz.</span><span class="sxs-lookup"><span data-stu-id="14b66-186">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="14b66-187">Bileşik Denetim artık bağlı diğer denetimleri oluşturulabilir temel olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="14b66-187">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="14b66-188">Sınıf bir taban sınıftan türetme işlemi adlı *devralma*.</span><span class="sxs-lookup"><span data-stu-id="14b66-188">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="14b66-189">Bu bölümde, adlı bileşik denetim oluşturacak `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="14b66-189">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="14b66-190">Bu denetim kendi üst denetiminden türetilen `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="14b66-190">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="14b66-191">İşlevlerini genişletmek öğreneceksiniz `ctlClock` üst yöntemleri geçersiz kılma ve yeni yöntemleri ve özellikleri ekleyerek.</span><span class="sxs-lookup"><span data-stu-id="14b66-191">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>  
  
 <span data-ttu-id="14b66-192">Devralınan bir denetim oluşturmanın ilk adımı, üst öğesinden türetilen olmaktır.</span><span class="sxs-lookup"><span data-stu-id="14b66-192">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="14b66-193">Bu eylem tüm özellikleri, yöntemleri ve üst denetim grafik özelliklere sahip yeni bir denetim oluşturur, ancak aynı zamanda yeni veya değiştirilmiş işlevselliği eklenmesi için bir temel olarak çalışabilir.</span><span class="sxs-lookup"><span data-stu-id="14b66-193">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>  
  
#### <a name="to-create-the-inherited-control"></a><span data-ttu-id="14b66-194">Devralınan denetimi oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="14b66-194">To create the inherited control</span></span>  
  
1.  <span data-ttu-id="14b66-195">Çözüm Gezgini'nde sağ **ctlClockLib**, işaret **Ekle**ve ardından **kullanıcı denetimi**.</span><span class="sxs-lookup"><span data-stu-id="14b66-195">In Solution Explorer, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>  
  
     <span data-ttu-id="14b66-196">**Yeni Öğe Ekle** iletişim kutusu açılır.</span><span class="sxs-lookup"><span data-stu-id="14b66-196">The **Add New Item** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="14b66-197">Seçin **devralınan kullanıcı denetimi** şablonu.</span><span class="sxs-lookup"><span data-stu-id="14b66-197">Select the **Inherited User Control** template.</span></span>  
  
3.  <span data-ttu-id="14b66-198">İçinde **adı** kutusuna `ctlAlarmClock.vb`ve ardından **Ekle**.</span><span class="sxs-lookup"><span data-stu-id="14b66-198">In the **Name** box, type `ctlAlarmClock.vb`, and then click **Add**.</span></span>  
  
     <span data-ttu-id="14b66-199">**Devralma Seçici** iletişim kutusu görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="14b66-199">The **Inheritance Picker** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="14b66-200">Altında **bileşen adı**, çift **ctlClock**.</span><span class="sxs-lookup"><span data-stu-id="14b66-200">Under **Component Name**, double-click **ctlClock**.</span></span>  
  
5.  <span data-ttu-id="14b66-201">Çözüm Gezgini'nde geçerli projeleri göz atın.</span><span class="sxs-lookup"><span data-stu-id="14b66-201">In Solution Explorer, browse through the current projects.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="14b66-202">Dosya adında **ctlAlarmClock.vb** geçerli projeye eklendi.</span><span class="sxs-lookup"><span data-stu-id="14b66-202">A file called **ctlAlarmClock.vb** has been added to the current project.</span></span>  
  
### <a name="adding-the-alarm-properties"></a><span data-ttu-id="14b66-203">Uyarı Özellikler ekleme</span><span class="sxs-lookup"><span data-stu-id="14b66-203">Adding the Alarm Properties</span></span>  
 <span data-ttu-id="14b66-204">Özellikler devralınan bir denetimi için bileşik denetim eklenen aynı şekilde eklenir.</span><span class="sxs-lookup"><span data-stu-id="14b66-204">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="14b66-205">Şimdi özelliği bildiriminin sözdizimi denetiminize iki özellik eklemek için kullanacağınız: `AlarmTime`, tarih ve saat uyarı olduğu kapalı, Git değerini depolar ve `AlarmSet`, hangi uyarı ayarlanıp ayarlanmadığını gösterilir.</span><span class="sxs-lookup"><span data-stu-id="14b66-205">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>  
  
##### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="14b66-206">Bileşik denetiminizi özellikleri eklemek için</span><span class="sxs-lookup"><span data-stu-id="14b66-206">To add properties to your composite control</span></span>  
  
1.  <span data-ttu-id="14b66-207">Çözüm Gezgini'nde sağ **ctlAlarmClock**ve ardından **görünümü kodu**.</span><span class="sxs-lookup"><span data-stu-id="14b66-207">In Solution Explorer, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="14b66-208">Sınıf bildirimi olarak görünür ctlAlarmClock denetiminin bulun `Public Class ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="14b66-208">Locate the class declaration for the ctlAlarmClock control, which appears as `Public Class ctlAlarmClock`.</span></span>  <span data-ttu-id="14b66-209">Sınıf bildiriminde aşağıdaki kodu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="14b66-209">In the class declaration, insert the following code.</span></span>  
  
    ```vb  
    Private dteAlarmTime As Date  
    Private blnAlarmSet As Boolean  
    ' These properties will be declared as Public to allow future   
    ' developers to access them.  
    Public Property AlarmTime() As Date  
        Get  
            Return dteAlarmTime  
        End Get  
        Set(ByVal value as Date)  
            dteAlarmTime = value  
        End Set  
    End Property  
    Public Property AlarmSet() As Boolean  
        Get  
            Return blnAlarmSet  
        End Get  
        Set(ByVal value as Boolean)  
            blnAlarmSet = value  
        End Set  
    End Property  
    ```  
  
### <a name="adding-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="14b66-210">Denetim grafik arabirimine ekleme</span><span class="sxs-lookup"><span data-stu-id="14b66-210">Adding to the Graphical Interface of the Control</span></span>  
 <span data-ttu-id="14b66-211">Devralınan denetiminizi öğesinden devralınan denetlemek için aynı olan bir görsel arabirimine sahiptir.</span><span class="sxs-lookup"><span data-stu-id="14b66-211">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="14b66-212">Aynı bağlı denetimler, üst denetim olarak sahip, ancak özellikle sunulan sürece bağlı denetimlerin özelliklerini kullanılabilir olmaz.</span><span class="sxs-lookup"><span data-stu-id="14b66-212">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="14b66-213">Herhangi bir bileşik denetimi eklediğiniz gibi aynı şekilde devralınan bir bileşik denetim grafik arabirimine ekleyebilir.</span><span class="sxs-lookup"><span data-stu-id="14b66-213">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="14b66-214">Uyarı saatin visual arabirimine eklemeye devam etmek için uyarı uyarabilir yükleyen yanar bir etiket denetimi ekleyeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="14b66-214">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>  
  
##### <a name="to-add-the-label-control"></a><span data-ttu-id="14b66-215">Etiket denetimi eklemek için</span><span class="sxs-lookup"><span data-stu-id="14b66-215">To add the label control</span></span>  
  
1.  <span data-ttu-id="14b66-216">Çözüm Gezgini'nde sağ **ctlAlarmClock**, tıklatıp **Görünüm Tasarımcısı**.</span><span class="sxs-lookup"><span data-stu-id="14b66-216">In Solution Explorer, right-click **ctlAlarmClock**, and click **View Designer**.</span></span>  
  
     <span data-ttu-id="14b66-217">Tasarımcı `ctlAlarmClock` ana pencerede açar.</span><span class="sxs-lookup"><span data-stu-id="14b66-217">The designer for `ctlAlarmClock` opens in the main window.</span></span>  
  
2.  <span data-ttu-id="14b66-218">Tıklatın `lblDisplay` (denetimin görüntüleme bölümü) ve Özellikler penceresini görüntüleyin.</span><span class="sxs-lookup"><span data-stu-id="14b66-218">Click `lblDisplay` (the display portion of the control), and view the Properties window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="14b66-219">Tüm özellikleri görüntülenir, ancak bunlar soluklaştırılır.</span><span class="sxs-lookup"><span data-stu-id="14b66-219">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="14b66-220">Bu bu özellikleri için yerel gösterir `lblDisplay` ve değiştirilemez veya Özellikler penceresinde erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="14b66-220">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="14b66-221">Varsayılan olarak, bu bileşik denetim içinde yer alan denetimleridir `Private`, ve bunların özelliklerini herhangi bir yolla erişilemiyor.</span><span class="sxs-lookup"><span data-stu-id="14b66-221">By default, controls contained in a composite control are `Private`, and their properties are not accessible by any means.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="14b66-222">Bileşik denetiminizin sonraki kullanıcıların iç denetimlerinden erişmesini isterseniz, bunları olarak bildirin `Public` veya `Protected`.</span><span class="sxs-lookup"><span data-stu-id="14b66-222">If you want subsequent users of your composite control to have access to its internal controls, declare them as `Public` or `Protected`.</span></span> <span data-ttu-id="14b66-223">Bu, ayarlamak ve uygun kodu kullanarak bileşik denetim içinde yer alan denetimlerin özelliklerini değiştirmek olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="14b66-223">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>  
  
3.  <span data-ttu-id="14b66-224">Ekleme bir <xref:System.Windows.Forms.Label> denetimi için bileşik denetim.</span><span class="sxs-lookup"><span data-stu-id="14b66-224">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>  
  
4.  <span data-ttu-id="14b66-225">Fareyle sürükleyin <xref:System.Windows.Forms.Label> kutusunu hemen altındaki denetim.</span><span class="sxs-lookup"><span data-stu-id="14b66-225">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="14b66-226">Özellikler penceresinde aşağıdaki özellikleri ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="14b66-226">In the Properties window, set the following properties.</span></span>  
  
    |<span data-ttu-id="14b66-227">Özellik</span><span class="sxs-lookup"><span data-stu-id="14b66-227">Property</span></span>|<span data-ttu-id="14b66-228">Ayar</span><span class="sxs-lookup"><span data-stu-id="14b66-228">Setting</span></span>|  
    |--------------|-------------|  
    |<span data-ttu-id="14b66-229">**Ad**</span><span class="sxs-lookup"><span data-stu-id="14b66-229">**Name**</span></span>|`lblAlarm`|  
    |<span data-ttu-id="14b66-230">**Metin**</span><span class="sxs-lookup"><span data-stu-id="14b66-230">**Text**</span></span>|<span data-ttu-id="14b66-231">**Uyarı!**</span><span class="sxs-lookup"><span data-stu-id="14b66-231">**Alarm!**</span></span>|  
    |<span data-ttu-id="14b66-232">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="14b66-232">**TextAlign**</span></span>|`MiddleCenter`|  
    |<span data-ttu-id="14b66-233">**Görünür**</span><span class="sxs-lookup"><span data-stu-id="14b66-233">**Visible**</span></span>|`False`|  
  
### <a name="adding-the-alarm-functionality"></a><span data-ttu-id="14b66-234">Uyarı işlevsellik ekleme</span><span class="sxs-lookup"><span data-stu-id="14b66-234">Adding the Alarm Functionality</span></span>  
 <span data-ttu-id="14b66-235">Önceki yordamlarda, özellikleri ve bileşik denetim alarm işlevselliği sağlayacak bir denetim eklendi.</span><span class="sxs-lookup"><span data-stu-id="14b66-235">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="14b66-236">Bu yordamda, alarm saati geçerli zamanın karşılaştırmak için kod ekleyeceksiniz ve aynı, ses ve bir alarm flash olmaları durumunda.</span><span class="sxs-lookup"><span data-stu-id="14b66-236">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to sound and flash an alarm.</span></span> <span data-ttu-id="14b66-237">Geçersiz kılma tarafından `Timer1_Tick` yöntemi `ctlClock` ve ek kod eklemeyi, yeteneğini uzatır `ctlAlarmClock` tüm devralınmış işlevselliğini korurken `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="14b66-237">By overriding the `Timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>  
  
##### <a name="to-override-the-timer1tick-method-of-ctlclock"></a><span data-ttu-id="14b66-238">CtlClock Timer1_Tick yöntemi geçersiz kılmak için</span><span class="sxs-lookup"><span data-stu-id="14b66-238">To override the Timer1_Tick method of ctlClock</span></span>  
  
1.  <span data-ttu-id="14b66-239">Çözüm Gezgini'nde sağ **ctlAlarmClock.vb**ve ardından **görünümü kodu**.</span><span class="sxs-lookup"><span data-stu-id="14b66-239">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="14b66-240">Bulun `Private blnAlarmSet As Boolean` deyimi.</span><span class="sxs-lookup"><span data-stu-id="14b66-240">Locate the `Private blnAlarmSet As Boolean` statement.</span></span> <span data-ttu-id="14b66-241">Hemen altında aşağıdaki deyimini ekleyin.</span><span class="sxs-lookup"><span data-stu-id="14b66-241">Immediately beneath it, add the following statement.</span></span>  
  
    ```vb  
    Dim blnColorTicker as Boolean  
    ```  
  
3.  <span data-ttu-id="14b66-242">Bulun `End Class` sayfanın sonundaki deyimi.</span><span class="sxs-lookup"><span data-stu-id="14b66-242">Locate the `End Class` statement at the bottom of the page.</span></span> <span data-ttu-id="14b66-243">Hemen önce `End Class` deyimi, aşağıdaki kodu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="14b66-243">Just before the `End Class` statement, add the following code.</span></span>  
  
    ```vb  
    Protected Overrides Sub Timer1_Tick(ByVal sender As Object, ByVal e _  
        As System.EventArgs)  
        ' Calls the Timer1_Tick method of ctlClock.  
        MyBase.Timer1_Tick(sender, e)  
        ' Checks to see if the Alarm is set.  
        If AlarmSet = False Then  
            Exit Sub  
        End If  
        ' If the date, hour, and minute of the alarm time are the same as  
        ' now, flash and beep an alarm.   
        If AlarmTime.Date = Now.Date And AlarmTime.Hour = Now.Hour And _  
            AlarmTime.Minute = Now.Minute Then  
            ' Sounds an audible beep.  
            Beep()  
            ' Sets lblAlarmVisible to True, and changes the background color based on the   
            ' value of blnColorTicker. The background color of the label will   
            ' flash once per tick of the clock.  
            lblAlarm.Visible = True  
            If blnColorTicker = False Then  
                lblAlarm.BackColor = Color.PeachPuff  
                blnColorTicker = True  
            Else  
                lblAlarm.BackColor = Color.Plum  
                blnColorTicker = False  
            End If  
        Else  
            ' Once the alarm has sounded for a minute, the label is made   
            ' invisible again.  
            lblAlarm.Visible = False  
        End If  
    End Sub  
    ```  
  
     <span data-ttu-id="14b66-244">Bu kod ayrıca çeşitli görevleri gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="14b66-244">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="14b66-245">`Overrides` Deyimi temel denetiminden devralındı yöntemi yerine bu yöntemi kullanmak için Denetim yönlendirir.</span><span class="sxs-lookup"><span data-stu-id="14b66-245">The `Overrides` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="14b66-246">Bu yöntem çağrıldığında, geçersiz kılmalar harekete geçirerek yöntemi çağırır `MyBase.Timer1_Tick` deyimi, tüm işlevleri özgün denetiminde birleştirilmiş sağlayarak bu denetimde çoğaltılamaz.</span><span class="sxs-lookup"><span data-stu-id="14b66-246">When this method is called, it calls the method it overrides by invoking the `MyBase.Timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="14b66-247">Daha sonra uyarı işlevselliği birleştirmek için ek kod çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="14b66-247">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="14b66-248">Uyarı oluşur ve bir sesli bip seslerini yanıp sönen bir etiket denetimi görünür.</span><span class="sxs-lookup"><span data-stu-id="14b66-248">A flashing label control will appear when the alarm occurs, and an audible beep will be heard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="14b66-249">Devralınmış olay işleyicisi geçersiz kılmak için olay ile belirtmeniz gerekmez `Handles` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="14b66-249">Because you are overriding an inherited event handler, you do not have to specify the event with the `Handles` keyword.</span></span> <span data-ttu-id="14b66-250">Olay zaten sayfaya.</span><span class="sxs-lookup"><span data-stu-id="14b66-250">The event is already hooked up.</span></span> <span data-ttu-id="14b66-251">Geçersiz kılma tek şey işleyicisinin uygulaması.</span><span class="sxs-lookup"><span data-stu-id="14b66-251">All you are overriding is the implementation of the handler.</span></span>  
  
     <span data-ttu-id="14b66-252">Alarm saati denetiminizi neredeyse tamamlandı.</span><span class="sxs-lookup"><span data-stu-id="14b66-252">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="14b66-253">Kalan tek şey, devre dışı bırakmak için bir yol uygulamaktır.</span><span class="sxs-lookup"><span data-stu-id="14b66-253">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="14b66-254">Bunu yapmak için kod ekleyeceksiniz `lblAlarm_Click` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="14b66-254">To do this, you will add code to the `lblAlarm_Click` method.</span></span>  
  
##### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="14b66-255">Kesici yöntemi uygulamak için</span><span class="sxs-lookup"><span data-stu-id="14b66-255">To implement the shutoff method</span></span>  
  
1.  <span data-ttu-id="14b66-256">Çözüm Gezgini'nde sağ **ctlAlarmClock.vb**ve ardından **Görünüm Tasarımcısı**.</span><span class="sxs-lookup"><span data-stu-id="14b66-256">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Designer**.</span></span>  
  
2.  <span data-ttu-id="14b66-257">Tasarımcıda çift **lblAlarm**.</span><span class="sxs-lookup"><span data-stu-id="14b66-257">In the designer, double-click **lblAlarm**.</span></span> <span data-ttu-id="14b66-258">**Kod düzenleyicisinde** açılır `Private Sub lblAlarm_Click` satır.</span><span class="sxs-lookup"><span data-stu-id="14b66-258">The **Code Editor** opens to the `Private Sub lblAlarm_Click` line.</span></span>  
  
3.  <span data-ttu-id="14b66-259">Bu yöntem, aşağıdaki kodu benzer şekilde değiştirin.</span><span class="sxs-lookup"><span data-stu-id="14b66-259">Modify this method so that it resembles the following code.</span></span>  
  
    ```vb  
    Private Sub lblAlarm_Click(ByVal sender As Object, ByVal e As _  
     System.EventArgs) Handles lblAlarm.Click  
        ' Turns off the alarm.  
        AlarmSet = False  
        ' Hides the flashing label.  
        lblAlarm.Visible = False  
    End Sub  
    ```  
  
4.  <span data-ttu-id="14b66-260">Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet** projeyi kaydetmek için.</span><span class="sxs-lookup"><span data-stu-id="14b66-260">On the **File** menu, click **Save All** to save the project.</span></span>  
  
### <a name="using-the-inherited-control-on-a-form"></a><span data-ttu-id="14b66-261">Bir Form üzerinde devralınan denetimi kullanma</span><span class="sxs-lookup"><span data-stu-id="14b66-261">Using the Inherited Control on a Form</span></span>  
 <span data-ttu-id="14b66-262">Taban sınıfı denetim test aynı şekilde, devralınan denetim sınayabilirsiniz `ctlClock`: F5 tuşuna basarak projeyi oluşturun ve denetiminizin Çalıştır **UserControl Test kapsayıcısı**.</span><span class="sxs-lookup"><span data-stu-id="14b66-262">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="14b66-263">Daha fazla bilgi için bkz: [nasıl yapılır: bir UserControl denetiminin çalışma zamanı davranışını sınama](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="14b66-263">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
 <span data-ttu-id="14b66-264">Kullanmak için denetim yerleştirmek için bir form üzerinde barındırmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="14b66-264">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="14b66-265">Standart bileşik denetim olarak, devralınan bir bileşik denetim tek başına olamaz ve bir form veya diğer kapsayıcı barındırılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="14b66-265">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="14b66-266">Bu yana `ctlAlarmClock` daha derinlemesine sahip işlevselliğini, test için ek kod gereklidir.</span><span class="sxs-lookup"><span data-stu-id="14b66-266">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="14b66-267">Bu yordamda işlevselliğini sınamak için basit bir program yazacaksınız `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="14b66-267">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="14b66-268">Ayarlama ve görüntülemek için kod yazacaksınız `AlarmTime` özelliği `ctlAlarmClock`ve devralınan işlevleri test.</span><span class="sxs-lookup"><span data-stu-id="14b66-268">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>  
  
##### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="14b66-269">Yapı ve test forma denetim ekleme</span><span class="sxs-lookup"><span data-stu-id="14b66-269">To build and add your control to a test form</span></span>  
  
1.  <span data-ttu-id="14b66-270">Çözüm Gezgini'nde sağ **ctlClockLib**ve ardından **yapı**.</span><span class="sxs-lookup"><span data-stu-id="14b66-270">In Solution Explorer, right-click **ctlClockLib**, and then click **Build**.</span></span>  
  
2.  <span data-ttu-id="14b66-271">Üzerinde **dosya** menüsündeki **Ekle**ve ardından **yeni proje**.</span><span class="sxs-lookup"><span data-stu-id="14b66-271">On the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
3.  <span data-ttu-id="14b66-272">Yeni bir ekleme **Windows uygulaması** proje çözüme ve adlandırın `Test`.</span><span class="sxs-lookup"><span data-stu-id="14b66-272">Add a new **Windows Application** project to the solution, and name it `Test`.</span></span>  
  
     <span data-ttu-id="14b66-273">**Test** proje çözüm Gezgini'ne eklenir.</span><span class="sxs-lookup"><span data-stu-id="14b66-273">The **Test** project is added to Solution Explorer.</span></span>  
  
4.  <span data-ttu-id="14b66-274">Çözüm Gezgini'nde sağ `Test` proje düğümünü ve ardından **Başvuru Ekle** görüntülemek için **Başvuru Ekle** iletişim kutusu.</span><span class="sxs-lookup"><span data-stu-id="14b66-274">In Solution Explorer, right-click the `Test` project node, and then click **Add Reference** to display the **Add Reference** dialog box.</span></span>  
  
5.  <span data-ttu-id="14b66-275">Etiketli sekmesini **projeleri**.</span><span class="sxs-lookup"><span data-stu-id="14b66-275">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="14b66-276">Proje **ctlClockLib** altında listelenen **proje adı**.</span><span class="sxs-lookup"><span data-stu-id="14b66-276">The project **ctlClockLib** will be listed under **Project Name**.</span></span> <span data-ttu-id="14b66-277">Çift **ctlClockLib** test projesinin başvuru eklemek için.</span><span class="sxs-lookup"><span data-stu-id="14b66-277">Double-click **ctlClockLib** to add the reference to the test project.</span></span>  
  
6.  <span data-ttu-id="14b66-278">Çözüm Gezgini'nde sağ **Test**ve ardından **yapı**.</span><span class="sxs-lookup"><span data-stu-id="14b66-278">In Solution Explorer, right-click **Test**, and then click **Build**.</span></span>  
  
7.  <span data-ttu-id="14b66-279">İçinde **araç**, genişletin **ctlClockLib bileşenleri** düğümü.</span><span class="sxs-lookup"><span data-stu-id="14b66-279">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>  
  
8.  <span data-ttu-id="14b66-280">Çift **ctlAlarmClock** örneği eklemek için `ctlAlarmClock` formunuza.</span><span class="sxs-lookup"><span data-stu-id="14b66-280">Double-click **ctlAlarmClock** to add an instance of `ctlAlarmClock` to your form.</span></span>  
  
9. <span data-ttu-id="14b66-281">İçinde **araç**, bulun ve çift tıklatın **DateTimePicker** eklemek için bir <xref:System.Windows.Forms.DateTimePicker> formunuza denetlemek ve ardından ekleyin bir <xref:System.Windows.Forms.Label> çift tıklatarak denetim **etiket**.</span><span class="sxs-lookup"><span data-stu-id="14b66-281">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>  
  
10. <span data-ttu-id="14b66-282">Denetimleri form üzerinde uygun bir konuma yerleştirmek için fare kullanın.</span><span class="sxs-lookup"><span data-stu-id="14b66-282">Use the mouse to position the controls in a convenient place on the form.</span></span>  
  
11. <span data-ttu-id="14b66-283">Bu denetimlerin özelliklerini aşağıdaki şekilde ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="14b66-283">Set the properties of these controls in the following manner.</span></span>  
  
    |<span data-ttu-id="14b66-284">Denetim</span><span class="sxs-lookup"><span data-stu-id="14b66-284">Control</span></span>|<span data-ttu-id="14b66-285">Özellik</span><span class="sxs-lookup"><span data-stu-id="14b66-285">Property</span></span>|<span data-ttu-id="14b66-286">Değer</span><span class="sxs-lookup"><span data-stu-id="14b66-286">Value</span></span>|  
    |-------------|--------------|-----------|  
    |`label1`|<span data-ttu-id="14b66-287">**Metin**</span><span class="sxs-lookup"><span data-stu-id="14b66-287">**Text**</span></span>|`(blank space)`|  
    ||<span data-ttu-id="14b66-288">**Ad**</span><span class="sxs-lookup"><span data-stu-id="14b66-288">**Name**</span></span>|`lblTest`|  
    |`dateTimePicker1`|<span data-ttu-id="14b66-289">**Ad**</span><span class="sxs-lookup"><span data-stu-id="14b66-289">**Name**</span></span>|`dtpTest`|  
    ||<span data-ttu-id="14b66-290">**Biçimi**</span><span class="sxs-lookup"><span data-stu-id="14b66-290">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|  
  
12. <span data-ttu-id="14b66-291">Tasarımcıda çift **dtpTest**.</span><span class="sxs-lookup"><span data-stu-id="14b66-291">In the designer, double-click **dtpTest**.</span></span>  
  
     <span data-ttu-id="14b66-292">**Kod düzenleyicisinde** açılır `Private Sub dtpTest_ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="14b66-292">The **Code Editor** opens to `Private Sub dtpTest_ValueChanged`.</span></span>  
  
13. <span data-ttu-id="14b66-293">Aşağıdakine benzer şekilde kodu değiştirin.</span><span class="sxs-lookup"><span data-stu-id="14b66-293">Modify the code so that it resembles the following.</span></span>  
  
    ```vb  
    Private Sub dtpTest_ValueChanged(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles dtpTest.ValueChanged  
        ctlAlarmClock1.AlarmTime = dtpTest.Value  
        ctlAlarmClock1.AlarmSet = True  
        lblTest.Text = "Alarm Time is " & Format(ctlAlarmClock1.AlarmTime, _  
            "hh:mm")  
    End Sub  
    ```  
  
14. <span data-ttu-id="14b66-294">Çözüm Gezgini'nde sağ **Test**ve ardından **başlangıç projesi olarak ayarla**.</span><span class="sxs-lookup"><span data-stu-id="14b66-294">In Solution Explorer, right-click **Test**, and then click **Set as StartUp Project**.</span></span>  
  
15. <span data-ttu-id="14b66-295">Üzerinde **hata ayıklama** menüsünde tıklatın **hata ayıklamayı Başlat**.</span><span class="sxs-lookup"><span data-stu-id="14b66-295">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="14b66-296">Test program başlar.</span><span class="sxs-lookup"><span data-stu-id="14b66-296">The test program starts.</span></span> <span data-ttu-id="14b66-297">Geçerli saat içinde güncelleştirilir Not `ctlAlarmClock` denetimi ve başlangıç saatini gösterildiği <xref:System.Windows.Forms.DateTimePicker> denetim.</span><span class="sxs-lookup"><span data-stu-id="14b66-297">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>  
  
16. <span data-ttu-id="14b66-298">Tıklatın <xref:System.Windows.Forms.DateTimePicker> saat, dakika görüntülendiği.</span><span class="sxs-lookup"><span data-stu-id="14b66-298">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>  
  
17. <span data-ttu-id="14b66-299">Klavye kullanılarak ayarlanan bir dakika tarafından gösterilen geçerli saatten büyük bir değer dakika `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="14b66-299">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>  
  
     <span data-ttu-id="14b66-300">Uyarı ayarı süredir gösterilen `lblTest`.</span><span class="sxs-lookup"><span data-stu-id="14b66-300">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="14b66-301">Uyarı ayarı zaman ulaşmak görüntülenen bir süre bekleyin.</span><span class="sxs-lookup"><span data-stu-id="14b66-301">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="14b66-302">Görüntülenen saati alarmı ayarlamak saatine ulaştığında, bip sesi ve `lblAlarm` flash.</span><span class="sxs-lookup"><span data-stu-id="14b66-302">When the displayed time reaches the time to which the alarm is set, the beep will sound and `lblAlarm` will flash.</span></span>  
  
18. <span data-ttu-id="14b66-303">Tıklayarak alarmı devre dışı bırakma `lblAlarm`.</span><span class="sxs-lookup"><span data-stu-id="14b66-303">Turn off the alarm by clicking `lblAlarm`.</span></span> <span data-ttu-id="14b66-304">Uyarı artık sıfırlayabilir.</span><span class="sxs-lookup"><span data-stu-id="14b66-304">You may now reset the alarm.</span></span>  
  
     <span data-ttu-id="14b66-305">Bu kılavuz temel kavramları sayısı ele.</span><span class="sxs-lookup"><span data-stu-id="14b66-305">This walkthrough has covered a number of key concepts.</span></span> <span data-ttu-id="14b66-306">Bileşik Denetim kapsayıcıya denetimleri ve bileşenleri birleştiren bileşik denetim oluşturmak öğrendiniz.</span><span class="sxs-lookup"><span data-stu-id="14b66-306">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="14b66-307">Denetiminize özellikleri ekleyin ve özel işlevsellik uygulamak için kod yazma öğrendiniz.</span><span class="sxs-lookup"><span data-stu-id="14b66-307">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="14b66-308">Son bölümünde devralma yoluyla belirli bir bileşik denetim işlevselliğini genişletmek ve bu yöntemi geçersiz kılarak konak yöntemleri işlevselliğini alter öğrendiniz.</span><span class="sxs-lookup"><span data-stu-id="14b66-308">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14b66-309">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="14b66-309">See Also</span></span>  
 [<span data-ttu-id="14b66-310">Özel denetim çeşitleri</span><span class="sxs-lookup"><span data-stu-id="14b66-310">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="14b66-311">Nasıl yapılır: bileşik denetimler yazma</span><span class="sxs-lookup"><span data-stu-id="14b66-311">How to: Author Composite Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [<span data-ttu-id="14b66-312">Nasıl yapılır: bir denetimi görüntüleme araç kutusu öğelerini Seç iletişim kutusu</span><span class="sxs-lookup"><span data-stu-id="14b66-312">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 [<span data-ttu-id="14b66-313">Bileşen geliştirme izlenecek yollar</span><span class="sxs-lookup"><span data-stu-id="14b66-313">Component Authoring Walkthroughs</span></span>](http://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)