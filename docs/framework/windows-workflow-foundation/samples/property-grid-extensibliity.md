---
title: "Özellik Kılavuzu Extensibliity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3530c3a3-756d-4712-9f10-fb2897414d3a
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e0df8ed572a0a02147e3bdf45dd880305363e8bd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="property-grid-extensibliity"></a><span data-ttu-id="4a8e7-102">Özellik Kılavuzu Extensibliity</span><span class="sxs-lookup"><span data-stu-id="4a8e7-102">Property Grid Extensibliity</span></span>
<span data-ttu-id="4a8e7-103">Bir geliştirici, belirli bir etkinlik Tasarımcısı'nda seçildiğinde görüntülenen özellik Kılavuzu özelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-103">A developer can customize the property grid that is displayed when a given activity is selected within the designer.</span></span> <span data-ttu-id="4a8e7-104">Bu bir zengin düzenleme deneyimi oluşturmak için yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-104">This can be done to create a rich editing experience.</span></span> <span data-ttu-id="4a8e7-105">Bu örnek, bu nasıl yapılabilir göstermektedir.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-105">This sample shows how this can be done.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="4a8e7-106">Gösteriler</span><span class="sxs-lookup"><span data-stu-id="4a8e7-106">Demonstrates</span></span>  
 <span data-ttu-id="4a8e7-107">İş Akışı Tasarımcısı özelliği kılavuz genişletilebilirliği.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-107">Workflow designer property grid extensibility.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4a8e7-108">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4a8e7-109">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4a8e7-110">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4a8e7-111">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`  
  
## <a name="discussion"></a><span data-ttu-id="4a8e7-112">Tartışma</span><span class="sxs-lookup"><span data-stu-id="4a8e7-112">Discussion</span></span>  
 <span data-ttu-id="4a8e7-113">Özellik Kılavuzu genişletmek için bir geliştirici özellik kılavuz Düzenleyici satır içi görünüşünü özelleştirme veya görünen bir iletişim kutusu için daha gelişmiş bir düzenleme yüzey sağlamak için seçenekleri vardır.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-113">To extend the property grid, a developer has options to customize the inline appearance of a property grid editor or provide a dialog that appears for a more advanced editing surface.</span></span> <span data-ttu-id="4a8e7-114">Bu örnekte gösterilen iki farklı düzenleyicileri vardır; bir satır içi düzenleyici ve bir iletişim kutusu Düzenleyicisi.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-114">There are two different editors demonstrated in this sample; an inline editor and a dialog editor.</span></span>  
  
## <a name="inline-editor"></a><span data-ttu-id="4a8e7-115">Satır içi Düzenleyicisi</span><span class="sxs-lookup"><span data-stu-id="4a8e7-115">Inline Editor</span></span>  
 <span data-ttu-id="4a8e7-116">Satır içi Düzenleyicisi örnek şunlar gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="4a8e7-116">The inline editor sample demonstrates the following:</span></span>  
  
-   <span data-ttu-id="4a8e7-117">Türetilen bir tür oluşturur <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-117">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.</span></span>  
  
-   <span data-ttu-id="4a8e7-118">Oluşturucu, <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> değeri ayarlandığında bir [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] veri şablonu yok.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-118">In the constructor, the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value is set with a [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] data template.</span></span> <span data-ttu-id="4a8e7-119">Bu bir XAML şablona bağlı olabilir, ancak bu örnekte, veri bağlama başlatmak için kod kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-119">This can be bound to a XAML template, but in this sample, code is used to initialize data binding.</span></span>  
  
-   <span data-ttu-id="4a8e7-120">Bir veri bağlamı veri şablonu bulunan <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> özellik kılavuzunda çizilir öğesi.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-120">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="4a8e7-121">Bu bağlamda sonra bağlar aşağıdaki kodu (ile CustomInlineEditor.cs) Not `Value` özelliği.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-121">Note in the following code (from CustomInlineEditor.cs) that this context then binds to the `Value` property.</span></span>  
  
    ```csharp  
    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));  
    FrameworkElementFactory slider = new FrameworkElementFactory(typeof(Slider));  
    Binding sliderBinding = new Binding("Value");  
    sliderBinding.Mode = BindingMode.TwoWay;  
    slider.SetValue(Slider.MinimumProperty, 0.0);  
    slider.SetValue(Slider.MaximumProperty, 100.0);  
    slider.SetValue(Slider.ValueProperty, sliderBinding);  
    stack.AppendChild(slider);  
    ```  
  
-   <span data-ttu-id="4a8e7-122">Etkinlik ve tasarımcı aynı bütünleştirilmiş kodda olduğundan, etkinlik Tasarımcısı özniteliklerinin kayıt elde etkinlik kendisini statik oluşturucuda SimpleCodeActivity.cs aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-122">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>  
  
    ```  
    static SimpleCodeActivity()  
    {  
        AttributeTableBuilder builder = new AttributeTableBuilder();  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));  
        MetadataStore.AddAttributeTable(builder.CreateTable());  
    }  
    ```  
  
## <a name="dialog-editor"></a><span data-ttu-id="4a8e7-123">İletişim Kutusu Düzenleyicisi</span><span class="sxs-lookup"><span data-stu-id="4a8e7-123">Dialog Editor</span></span>  
 <span data-ttu-id="4a8e7-124">İletişim kutusu Düzenleyicisi örnek şunlar gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="4a8e7-124">The dialog editor sample demonstrates the following:</span></span>  
  
1.  <span data-ttu-id="4a8e7-125">Türetilen bir tür oluşturur <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-125">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.</span></span>  
  
2.  <span data-ttu-id="4a8e7-126">Ayarlar <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> Oluşturucu değerinde bir [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] veri şablonu yok.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-126">Sets the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value in the constructor with a [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] data template.</span></span> <span data-ttu-id="4a8e7-127">Bu XAML içinde oluşturulabilir, ancak bu örnekte, bu kod içinde oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-127">This can be created in XAML, but in this sample, this is created in code.</span></span>  
  
3.  <span data-ttu-id="4a8e7-128">Bir veri bağlamı veri şablonu bulunan <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> özellik kılavuzunda çizilir öğesi.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-128">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="4a8e7-129">Bu daha sonra aşağıdaki kodda bağlar `Value` özelliği.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-129">In the following code, this then binds to the `Value` property.</span></span> <span data-ttu-id="4a8e7-130">De dahil etmek için kritik bir <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> FilePickerEditor.cs iletişim başlatır düğmesi sağlayacak şekilde.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-130">It is critical to also include an <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> to provide the button that raises the dialog in FilePickerEditor.cs.</span></span>  
  
    ```  
    this.InlineEditorTemplate = new DataTemplate();  
  
    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));  
    stack.SetValue(StackPanel.OrientationProperty, Orientation.Horizontal);  
    FrameworkElementFactory label = new FrameworkElementFactory(typeof(Label));  
    Binding labelBinding = new Binding("Value");  
    label.SetValue(Label.ContentProperty, labelBinding);  
    label.SetValue(Label.MaxWidthProperty, 90.0);  
  
    stack.AppendChild(label);  
  
    FrameworkElementFactory editModeSwitch = new FrameworkElementFactory(typeof(EditModeSwitchButton));  
  
    editModeSwitch.SetValue(EditModeSwitchButton.TargetEditModeProperty, PropertyContainerEditMode.Dialog);  
  
    stack.AppendChild(editModeSwitch);  
  
    this.InlineEditorTemplate.VisualTree = stack;  
    ```  
  
4.  <span data-ttu-id="4a8e7-131">Geçersiz kılmaları <!--zz <xref:Microsoft.Windows.Design.PropertyEditing.ShowDialog%2A>--> `Microsoft.Windows.Design.PropertyEditing.ShowDialog` iletişim görüntüsünü işlemek için tasarımcı türündeki yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-131">Overrides the <!--zz <xref:Microsoft.Windows.Design.PropertyEditing.ShowDialog%2A>--> `Microsoft.Windows.Design.PropertyEditing.ShowDialog` method in the designer type to handle the display of the dialog.</span></span> <span data-ttu-id="4a8e7-132">Bu örnekte, temel bir <xref:System.Windows.Forms.FileDialog> gösterilir.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-132">In this sample, a basic <xref:System.Windows.Forms.FileDialog> is shown.</span></span>  
  
    ```  
    public override void ShowDialog(PropertyValue propertyValue, IInputElement commandSource)  
    {  
        Microsoft.Win32.OpenFileDialog ofd = new Microsoft.Win32.OpenFileDialog();  
        if (ofd.ShowDialog() == true)  
        {  
            propertyValue.Value = ofd.FileName;  
        }  
    }  
    ```  
  
5.  <span data-ttu-id="4a8e7-133">Etkinlik ve tasarımcı aynı bütünleştirilmiş kodda olduğundan, etkinlik Tasarımcısı özniteliklerinin kayıt elde etkinlik kendisini statik oluşturucuda SimpleCodeActivity.cs aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-133">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>  
  
    ```  
    static SimpleCodeActivity()  
    {  
        AttributeTableBuilder builder = new AttributeTableBuilder();  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));  
        MetadataStore.AddAttributeTable(builder.CreateTable());  
    }  
    ```  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4a8e7-134">Ayarlamak için derleme ve örnek çalıştırın</span><span class="sxs-lookup"><span data-stu-id="4a8e7-134">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4a8e7-135">Çözümü derlemek ve Workflow1.xaml açın.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-135">Build the solution, and then open Workflow1.xaml.</span></span>  
  
2.  <span data-ttu-id="4a8e7-136">Sürükleme bir **SimpleCodeActivity** Tasarımcı tuvaline Kutusu'ndan.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-136">Drag a **SimpleCodeActivity** from the toolbox onto the designer canvas.</span></span>  
  
3.  <span data-ttu-id="4a8e7-137">Tıklatın **SimpleCodeActivity** ve özellik ızgarasının kaydırıcı denetimi olduğu ve denetim çekme bir dosya açın.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-137">Click the **SimpleCodeActivity** and then open the property grid where there is a slider control and a file picking control.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4a8e7-138">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4a8e7-139">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-139">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4a8e7-140">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4a8e7-141">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="4a8e7-141">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`