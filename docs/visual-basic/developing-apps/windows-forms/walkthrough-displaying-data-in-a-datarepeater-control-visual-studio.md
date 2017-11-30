---
title: "İzlenecek Yol: DataRepeater Denetimindeki Verileri Görüntüleme (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 39c3b56404c981e674766354463e23aa349994cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="d6950-102">İzlenecek Yol: DataRepeater Denetimindeki Verileri Görüntüleme (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="d6950-102">Walkthrough: Displaying Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="d6950-103">Bu kılavuzda ilişkili verileri görüntülemek için bir temel başlangıç-bitiş senaryo sağlar bir <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-103">This walkthrough provides a basic start-to-finish scenario for displaying bound data in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="d6950-104">Önkoşul</span><span class="sxs-lookup"><span data-stu-id="d6950-104">Prerequisite</span></span>  
 <span data-ttu-id="d6950-105">Bu kılavuz, Northwind örnek veritabanı gerektirir.</span><span class="sxs-lookup"><span data-stu-id="d6950-105">This walkthrough requires the Northwind sample database.</span></span>  
  
 <span data-ttu-id="d6950-106">Bu veritabanı geliştirme bilgisayarınızda yoksa, buradan indirebilirsiniz [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088).</span><span class="sxs-lookup"><span data-stu-id="d6950-106">If you do not have this database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088).</span></span> <span data-ttu-id="d6950-107">Yönergeler için bkz: [örnek veritabanları yükleme](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="d6950-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="d6950-108">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="d6950-108">Overview</span></span>  
 <span data-ttu-id="d6950-109">Bu kılavuzun ilk bölümü dört ana görevden oluşur:</span><span class="sxs-lookup"><span data-stu-id="d6950-109">The first part of this walkthrough consists of four main tasks:</span></span>  
  
-   <span data-ttu-id="d6950-110">Bir çözümü oluşturma.</span><span class="sxs-lookup"><span data-stu-id="d6950-110">Creating a solution.</span></span>  
  
-   <span data-ttu-id="d6950-111">Ekleme bir <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-111">Adding a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="d6950-112">Veri kaynağı ekleme.</span><span class="sxs-lookup"><span data-stu-id="d6950-112">Adding a data source.</span></span>  
  
-   <span data-ttu-id="d6950-113">Verilere bağlı denetimler ekleme.</span><span class="sxs-lookup"><span data-stu-id="d6950-113">Adding data-bound controls.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-a-datarepeater-solution"></a><span data-ttu-id="d6950-114">DataRepeater çözümü oluşturma</span><span class="sxs-lookup"><span data-stu-id="d6950-114">Creating a DataRepeater Solution</span></span>  
 <span data-ttu-id="d6950-115">İlk adımda bir proje ve çözüm oluşturun.</span><span class="sxs-lookup"><span data-stu-id="d6950-115">In the first step, you create a project and solution.</span></span>  
  
#### <a name="to-create-a-datarepeater-solution"></a><span data-ttu-id="d6950-116">DataRepeater çözüm oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="d6950-116">To create a DataRepeater solution</span></span>  
  
1.  <span data-ttu-id="d6950-117">Visual Studio üzerinde **dosya** menüsünde tıklatın **yeni proje**.</span><span class="sxs-lookup"><span data-stu-id="d6950-117">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="d6950-118">İçinde **proje türleri** bölmesinde **yeni proje** iletişim kutusunda, genişletin **Visual Basic**ve ardından **Windows**.</span><span class="sxs-lookup"><span data-stu-id="d6950-118">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3.  <span data-ttu-id="d6950-119">İçinde **şablonları** bölmesinde tıklatın **Windows Forms uygulaması**.</span><span class="sxs-lookup"><span data-stu-id="d6950-119">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="d6950-120">İçinde **adı** kutusuna `DataRepeaterApp`.</span><span class="sxs-lookup"><span data-stu-id="d6950-120">In the **Name** box, type `DataRepeaterApp`.</span></span>  
  
5.  <span data-ttu-id="d6950-121">**Tamam**'ı tıklatın.</span><span class="sxs-lookup"><span data-stu-id="d6950-121">Click **OK**.</span></span>  
  
     <span data-ttu-id="d6950-122">Windows Forms Tasarımcısı'nı açar.</span><span class="sxs-lookup"><span data-stu-id="d6950-122">The Windows Forms Designer opens.</span></span>  
  
6.  <span data-ttu-id="d6950-123">Windows Forms Tasarımcısı'nda formu seçin.</span><span class="sxs-lookup"><span data-stu-id="d6950-123">Select the form in the Windows Forms Designer.</span></span> <span data-ttu-id="d6950-124">İçinde **özellikleri** penceresindeki ayarlayın **boyutu** özelliğine `800, 700`.</span><span class="sxs-lookup"><span data-stu-id="d6950-124">In the **Properties** window, set the **Size** property to `800, 700`.</span></span>  
  
## <a name="adding-a-datarepeater-control"></a><span data-ttu-id="d6950-125">DataRepeater denetimi ekleme</span><span class="sxs-lookup"><span data-stu-id="d6950-125">Adding a DataRepeater Control</span></span>  
 <span data-ttu-id="d6950-126">Bu adımda eklediğiniz bir <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> forma denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-126">In this step, you add a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to the form.</span></span>  
  
#### <a name="to-add-a-datarepeater-control"></a><span data-ttu-id="d6950-127">DataRepeater denetimi eklemek için</span><span class="sxs-lookup"><span data-stu-id="d6950-127">To add a DataRepeater control</span></span>  
  
1.  <span data-ttu-id="d6950-128">Üzerinde **Görünüm** menüsünde tıklatın **araç**.</span><span class="sxs-lookup"><span data-stu-id="d6950-128">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="d6950-129">**Araç** açar.</span><span class="sxs-lookup"><span data-stu-id="d6950-129">The **Toolbox** opens.</span></span>  
  
2.  <span data-ttu-id="d6950-130">Seçin **Visual Basic PowerPacks** sekmesi.</span><span class="sxs-lookup"><span data-stu-id="d6950-130">Select the **Visual Basic PowerPacks** tab.</span></span>  
  
3.  <span data-ttu-id="d6950-131">Sürükleme bir <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> üzerine kontrol **Form1**.</span><span class="sxs-lookup"><span data-stu-id="d6950-131">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control onto **Form1**.</span></span>  
  
4.  <span data-ttu-id="d6950-132">Özellikler penceresinde ayarlayın **konumu** özelliğine `0, 25`.</span><span class="sxs-lookup"><span data-stu-id="d6950-132">In the Properties window, set the **Location** property to `0, 25`.</span></span>  
  
5.  <span data-ttu-id="d6950-133">Ayarlama **boyutu** özelliğine `460, 600`.</span><span class="sxs-lookup"><span data-stu-id="d6950-133">Set the **Size** property to `460, 600`.</span></span>  
  
## <a name="adding-a-data-source"></a><span data-ttu-id="d6950-134">Veri kaynağı ekleme</span><span class="sxs-lookup"><span data-stu-id="d6950-134">Adding a Data Source</span></span>  
 <span data-ttu-id="d6950-135">Bu adımda, bir veri kaynağı için ekleme <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-135">In this step, you add a data source for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-add-a-data-source"></a><span data-ttu-id="d6950-136">Bir veri kaynağı eklemek için</span><span class="sxs-lookup"><span data-stu-id="d6950-136">To add a data source</span></span>  
  
1.  <span data-ttu-id="d6950-137">Üzerinde **veri** menüsünde tıklatın **veri kaynaklarını Göster**.</span><span class="sxs-lookup"><span data-stu-id="d6950-137">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
2.  <span data-ttu-id="d6950-138">İçinde **veri kaynakları** penceresinde tıklatın **yeni veri kaynağı Ekle**.</span><span class="sxs-lookup"><span data-stu-id="d6950-138">In the **Data Sources** window, click **Add New Data Source**.</span></span>  
  
3.  <span data-ttu-id="d6950-139">Seçin **veritabanı** üzerinde **bir veri kaynağı türü seç** sayfasında ve ardından **sonraki**.</span><span class="sxs-lookup"><span data-stu-id="d6950-139">Select **Database** on the **Choose a Data Source Type** page, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="d6950-140">Üzerinde **veri bağlantınızı** sayfasında, aşağıdaki adımlardan birini gerçekleştirin:</span><span class="sxs-lookup"><span data-stu-id="d6950-140">On the **Choose Your Data Connection** page, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="d6950-141">Northwind örnek veritabanıyla kurulan veri bağlantısı açılan listede kullanılabilir durumdaysa bu bağlantıya tıklayın.</span><span class="sxs-lookup"><span data-stu-id="d6950-141">If a data connection to the Northwind sample database is available in the drop-down list, click it.</span></span>  
  
         <span data-ttu-id="d6950-142">veya</span><span class="sxs-lookup"><span data-stu-id="d6950-142">-or-</span></span>  
  
    -   <span data-ttu-id="d6950-143">Tıklatın **yeni bağlantı** yeni bir veri bağlantısı yapılandırmak için.</span><span class="sxs-lookup"><span data-stu-id="d6950-143">Click **New Connection** to configure a new data connection.</span></span> <span data-ttu-id="d6950-144">Daha fazla bilgi için bkz: [nasıl yapılır: SQL Server veritabanları için bağlantıları oluşturma](http://msdn.microsoft.com/en-us/360c340d-e5a6-4a7e-a569-e95d500be43d).</span><span class="sxs-lookup"><span data-stu-id="d6950-144">For more information, see [How to: Create Connections to SQL Server Databases](http://msdn.microsoft.com/en-us/360c340d-e5a6-4a7e-a569-e95d500be43d).</span></span>  
  
5.  <span data-ttu-id="d6950-145">Veritabanı parola gerektiriyorsa, hassas bilgileri Ekle ve ardından seçeneğini **sonraki**.</span><span class="sxs-lookup"><span data-stu-id="d6950-145">If the database requires a password, select the option to include sensitive data, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6950-146">Bir iletişim kutusu görüntülenirse, tıklatın **Evet** dosyayı projenize kaydetmek için.</span><span class="sxs-lookup"><span data-stu-id="d6950-146">If a dialog box appears, click **Yes** to save the file to your project.</span></span>  
  
6.  <span data-ttu-id="d6950-147">Tıklatın **sonraki** üzerinde **uygulama yapılandırma dosyasında bağlantı dizesini kaydedin** sayfası.</span><span class="sxs-lookup"><span data-stu-id="d6950-147">Click **Next** on the **Save Connection String to the Application Configuration file** page.</span></span>  
  
7.  <span data-ttu-id="d6950-148">Genişletme **tabloları** düğümde **veritabanı nesnelerinizi** sayfası.</span><span class="sxs-lookup"><span data-stu-id="d6950-148">Expand the **Tables** node on the **Choose Your Database Objects** page.</span></span>  
  
8.  <span data-ttu-id="d6950-149">Onay kutularını işaretleyin **müşteriler** ve **siparişleri** tablolar ve ardından **son**.</span><span class="sxs-lookup"><span data-stu-id="d6950-149">Select the check boxes next to the **Customers** and **Orders** tables, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="d6950-150">**NorthwindDataSet** projenize eklenir ve **müşteriler** ve **siparişleri** tabloları görünür **veri kaynakları** penceresi.</span><span class="sxs-lookup"><span data-stu-id="d6950-150">**NorthwindDataSet** is added to your project and the **Customers** and **Orders** tables appear in the **Data Sources** window.</span></span>  
  
## <a name="adding-data-bound-controls"></a><span data-ttu-id="d6950-151">Verilere bağlı denetimler ekleme</span><span class="sxs-lookup"><span data-stu-id="d6950-151">Adding Data-Bound Controls</span></span>  
 <span data-ttu-id="d6950-152">Bu adımda, verilere bağlı denetimler ekleme <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span><span class="sxs-lookup"><span data-stu-id="d6950-152">In this step, you add data-bound controls to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
#### <a name="to-add-data-bound-controls"></a><span data-ttu-id="d6950-153">Verilere bağlı denetimler eklemek için</span><span class="sxs-lookup"><span data-stu-id="d6950-153">To add data-bound controls</span></span>  
  
1.  <span data-ttu-id="d6950-154">İçinde **veri kaynakları** penceresi, üst düzey düğümü seçin **müşteriler** tablo.</span><span class="sxs-lookup"><span data-stu-id="d6950-154">In the **Data Sources** window, select the top-level node for the **Customers** table.</span></span>  
  
2.  <span data-ttu-id="d6950-155">Tabloya açılan türünü değiştirme **ayrıntıları** tıklayarak **ayrıntıları** Tablo düğümü aşağı açılan listesinde.</span><span class="sxs-lookup"><span data-stu-id="d6950-155">Change the drop type of the table to **Details** by clicking **Details** in the drop-down list on the table node.</span></span>  
  
3.  <span data-ttu-id="d6950-156">Seçin **müşteriler** Tablo düğümü ve Madde şablonu bölgesini (üst bölge) sürükleyin <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-156">Select the **Customers** table node and drag it onto the item template region (the upper region) of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="d6950-157">A <xref:System.Windows.Forms.BindingNavigator> denetimi forma eklenir ve **NorthwindDataSet**, **CustomersBindingSource**, **TableAdapter**,  **TableAdapterManager**, ve **CustomersBindingNavigator** bileşenleri bileşen Tepsisi eklenir.</span><span class="sxs-lookup"><span data-stu-id="d6950-157">A <xref:System.Windows.Forms.BindingNavigator> control is added to the form, and the **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, and **CustomersBindingNavigator** components are added to the Component Tray.</span></span>  
  
4.  <span data-ttu-id="d6950-158">Tüm alanları ve bunların ilişkili etiketleri seçin ve Madde şablonu bölgesi sol kenarı yerleştir.</span><span class="sxs-lookup"><span data-stu-id="d6950-158">Select all of the fields and their associated labels and position them near the left edge of the item template region.</span></span>  
  
5.  <span data-ttu-id="d6950-159">Son beş alanları seçin (**bölge**, **posta kodu**, **Ülke**, **telefon**, ve **faks**) ve bunların ilişkili etiketleri ve en fazla ve ilk altı alanlarının sağa taşıyın.</span><span class="sxs-lookup"><span data-stu-id="d6950-159">Select the last five fields (**Region**, **Postal Code**, **Country**, **Phone**, and **Fax**) and their associated labels and move them up and to the right of the first six fields.</span></span>  
  
6.  <span data-ttu-id="d6950-160">Öğe şablonu (Denetim üst bölge) seçin.</span><span class="sxs-lookup"><span data-stu-id="d6950-160">Select the item template (the upper region of the control).</span></span>  
  
7.  <span data-ttu-id="d6950-161">Özellikler penceresinde ayarlayın **boyutu** özelliğine `427, 170`.</span><span class="sxs-lookup"><span data-stu-id="d6950-161">In the Properties window, set the **Size** property to `427, 170`.</span></span>  
  
 <span data-ttu-id="d6950-162">Bu noktada, yinelenen müşterilerin listesini görüntüler ve çalışan bir uygulama vardır.</span><span class="sxs-lookup"><span data-stu-id="d6950-162">At this point, you have a working application that will display a repeating list of customers.</span></span> <span data-ttu-id="d6950-163">Uygulamayı çalıştırın, verileri değiştirebilir ve eklemek veya Müşteri kayıtlarını silmek için F5 tuşuna basabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d6950-163">You can press F5 to run the application, change the data, and add or delete customer records.</span></span>  
  
 <span data-ttu-id="d6950-164">İsteğe bağlı sonraki adımlarda özelleştirme hakkında bilgi edineceksiniz <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-164">In the next optional steps, you will learn how to customize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="next-steps-optional"></a><span data-ttu-id="d6950-165">Sonraki adımlar (isteğe bağlı)</span><span class="sxs-lookup"><span data-stu-id="d6950-165">Next Steps (Optional)</span></span>  
 <span data-ttu-id="d6950-166">Kılavuzun bu bölümü dört isteğe bağlı görevden oluşur:</span><span class="sxs-lookup"><span data-stu-id="d6950-166">This part of the walkthrough consists of four optional tasks:</span></span>  
  
-   <span data-ttu-id="d6950-167">Görünümünü değiştirme <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-167">Changing the appearance of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="d6950-168">Kullanıcıların ekleme veya kayıt silme engelliyor.</span><span class="sxs-lookup"><span data-stu-id="d6950-168">Preventing users from adding or deleting records.</span></span>  
  
-   <span data-ttu-id="d6950-169">İçin arama yeteneğine ekleme <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-169">Adding search capability to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="d6950-170">Ana ve ayrıntı tabloya ekleme <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-170">Adding a master and detail table to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a><span data-ttu-id="d6950-171">DataRepeater denetiminin görünümünü değiştirme</span><span class="sxs-lookup"><span data-stu-id="d6950-171">Changing the Appearance of the DataRepeater Control</span></span>  
 <span data-ttu-id="d6950-172">Bu isteğe bağlı adım, değişiklik `BackColor` , <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> tasarım zamanında denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-172">In this optional step, you change the `BackColor` of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time.</span></span> <span data-ttu-id="d6950-173">Ayrıca değişen renklerde satırları görüntülemek ve bir etiketin değiştirmek için kodu ekleyin `ForeColor` koşullu.</span><span class="sxs-lookup"><span data-stu-id="d6950-173">You also add code to display rows in alternating colors and to change a label's `ForeColor` conditionally.</span></span>  
  
#### <a name="to-change-the-appearance-of-the-control"></a><span data-ttu-id="d6950-174">Denetimin görünümünü değiştirmek için</span><span class="sxs-lookup"><span data-stu-id="d6950-174">To change the appearance of the control</span></span>  
  
1.  <span data-ttu-id="d6950-175">Windows Forms Tasarımcısı'nda ana (alt) bölgesini seçin <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-175">In the Windows Forms Designer, select the main (lower) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="d6950-176">Özellikler penceresinde ayarlayın `BackColor` beyaz özelliği.</span><span class="sxs-lookup"><span data-stu-id="d6950-176">In the Properties window, set the `BackColor` property to white.</span></span>  
  
3.  <span data-ttu-id="d6950-177">Çift <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Kod Düzenleyicisi'ni açın.</span><span class="sxs-lookup"><span data-stu-id="d6950-177">Double-click the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> to open the Code Editor.</span></span>  
  
4.  <span data-ttu-id="d6950-178">Kod Düzenleyicisi'nde olay açılan listesinde, **DrawItem**.</span><span class="sxs-lookup"><span data-stu-id="d6950-178">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
5.  <span data-ttu-id="d6950-179">İçinde <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> olay işleyicisi için alternatif aşağıdaki kodu ekleyin `BackColor`:</span><span class="sxs-lookup"><span data-stu-id="d6950-179">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to alternate the `BackColor`:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]  
  
6.  <span data-ttu-id="d6950-180">İçinde <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> olay işleyicisi değiştirmek için aşağıdaki kodu ekleyin `ForeColor` etiket bağlı bir koşul olarak:</span><span class="sxs-lookup"><span data-stu-id="d6950-180">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to change the `ForeColor` of a label depending on a condition:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]  
  
7.  <span data-ttu-id="d6950-181">Uygulamayı çalıştırın ve özelleştirmeleri görmek için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="d6950-181">Press F5 to run the application and see the customizations.</span></span>  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a><span data-ttu-id="d6950-182">Kullanıcıların ekleme veya kayıt silme önleme</span><span class="sxs-lookup"><span data-stu-id="d6950-182">Preventing Users from Adding or Deleting Records</span></span>  
 <span data-ttu-id="d6950-183">İsteğe bağlı Bu adımda, kullanıcıların ekleme veya kayıt silme engeller kodu ekleyin <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-183">In this optional step, you add code that prevents users from adding or deleting records in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a><span data-ttu-id="d6950-184">Kayıtları ekleme ve silme kullanıcıların engellemek için</span><span class="sxs-lookup"><span data-stu-id="d6950-184">To prevent users from adding and deleting records</span></span>  
  
1.  <span data-ttu-id="d6950-185">Windows Forms Tasarımcısı'nda formun Kod Düzenleyicisi'ni açmak için çift tıklayın.</span><span class="sxs-lookup"><span data-stu-id="d6950-185">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="d6950-186">Aşağıdaki kodu ekleyin `Form_Load` olay:</span><span class="sxs-lookup"><span data-stu-id="d6950-186">Add the following code to the `Form_Load` event:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]  
  
3.  <span data-ttu-id="d6950-187">Sınıf adı açılan listeye tıklayın **BindingNavigatorDeleteItem**.</span><span class="sxs-lookup"><span data-stu-id="d6950-187">In the Class Name drop-down list, click **BindingNavigatorDeleteItem**.</span></span> <span data-ttu-id="d6950-188">Yöntem adı açılan listeye tıklayın **EnabledChanged**.</span><span class="sxs-lookup"><span data-stu-id="d6950-188">In the Method Name drop-down list, click **EnabledChanged**.</span></span>  
  
4.  <span data-ttu-id="d6950-189">Aşağıdaki kodu ekleyin `BindingNavigatorDeleteItem_EnabledChanged` olay işleyicisi:</span><span class="sxs-lookup"><span data-stu-id="d6950-189">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="d6950-190">Bu adım gereklidir çünkü <xref:System.Windows.Forms.BindingSource> etkinleştirecek **DeleteItem** düğmesini geçerli kayıt değişiklikleri her zaman.</span><span class="sxs-lookup"><span data-stu-id="d6950-190">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
5.  <span data-ttu-id="d6950-191">Uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="d6950-191">Press F5 to run the application.</span></span> <span data-ttu-id="d6950-192">Dikkat **DeleteItem** düğmesi devre dışıdır ve DELETE tuşuna basarak öğelerini, silemezsiniz.</span><span class="sxs-lookup"><span data-stu-id="d6950-192">Notice that the **DeleteItem** button is disabled and that you cannot delete items by pressing the DELETE key.</span></span>  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a><span data-ttu-id="d6950-193">DataRepeater denetimi için arama yeteneğine ekleme</span><span class="sxs-lookup"><span data-stu-id="d6950-193">Adding Search Capability to the DataRepeater Control</span></span>  
 <span data-ttu-id="d6950-194">İsteğe bağlı Bu adımda, bir değer için arama yeteneği uygulamak <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-194">In this optional step, you implement the capability to search for a value in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="d6950-195">Arama dizesi bulunursa, denetim değeri içeren ve öğe görünüme gelene öğeyi seçer.</span><span class="sxs-lookup"><span data-stu-id="d6950-195">If the search string is found, the control selects the item that contains the value and scrolls the item into view.</span></span>  
  
#### <a name="to-add-search-capability"></a><span data-ttu-id="d6950-196">Arama özelliği eklemek için</span><span class="sxs-lookup"><span data-stu-id="d6950-196">To add search capability</span></span>  
  
1.  <span data-ttu-id="d6950-197">Sürükleme bir <xref:System.Windows.Forms.TextBox> gelen denetim **araç** içeren forma <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-197">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="d6950-198">Bunun altına getirin <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-198">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="d6950-199">Özellikler penceresinde değiştirin **adı** özelliğine **SearchTextBox**.</span><span class="sxs-lookup"><span data-stu-id="d6950-199">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="d6950-200">Sürükleme bir <xref:System.Windows.Forms.Button> gelen denetim **araç** içeren forma <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-200">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="d6950-201">Bunun altına getirin <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-201">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="d6950-202">Özellikler penceresinde değiştirin **adı** özelliğine **SearchButton**.</span><span class="sxs-lookup"><span data-stu-id="d6950-202">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="d6950-203">Değişiklik **metin** özelliğine **arama**.</span><span class="sxs-lookup"><span data-stu-id="d6950-203">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="d6950-204">Çift <xref:System.Windows.Forms.Button> Kod Düzenleyicisi'ni açmak için Denetim ve aşağıdaki kodu ekleyin `SearchButton_Click` olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="d6950-204">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]  
  
6.  <span data-ttu-id="d6950-205">Uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="d6950-205">Press F5 to run the application.</span></span> <span data-ttu-id="d6950-206">Bir müşteri kimliği yazın **SearchTextBox** tıklatıp **arama** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="d6950-206">Type a customer ID in **SearchTextBox** and click the **Search** button.</span></span>  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a><span data-ttu-id="d6950-207">Ana ve ayrıntı tablosunu DataRepeater ekleme</span><span class="sxs-lookup"><span data-stu-id="d6950-207">Adding a Master and Detail Table to the DataRepeater</span></span>  
 <span data-ttu-id="d6950-208">İsteğe bağlı Bu adımda eklediğiniz ikinci bir <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> her müşteri için ilgili siparişleri görüntülemek için denetimi.</span><span class="sxs-lookup"><span data-stu-id="d6950-208">In this optional step, you add a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to display related orders for each customer.</span></span>  
  
#### <a name="to-add-a-master-and-detail-table"></a><span data-ttu-id="d6950-209">Ana ve ayrıntı tablo eklemek için</span><span class="sxs-lookup"><span data-stu-id="d6950-209">To add a master and detail table</span></span>  
  
1.  <span data-ttu-id="d6950-210">İkinci bir sürükleyin <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> gelen denetim **Visual Basic PowerPacks** sekmesinde **araç** forma.</span><span class="sxs-lookup"><span data-stu-id="d6950-210">Drag a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="d6950-211">Özellikler penceresinde ayarlayın **konumu** özelliğine `465, 25`.</span><span class="sxs-lookup"><span data-stu-id="d6950-211">In the Properties window, set the **Location** property to `465, 25`.</span></span>  
  
3.  <span data-ttu-id="d6950-212">Ayarlama **boyutu** özelliğine `315, 600`.</span><span class="sxs-lookup"><span data-stu-id="d6950-212">Set the **Size** property to `315, 600`.</span></span>  
  
4.  <span data-ttu-id="d6950-213">İçinde **veri kaynakları** penceresinde genişletin **müşteriler** Tablo düğümü ve ayrıntı düğümü seçin **siparişleri** tablo.</span><span class="sxs-lookup"><span data-stu-id="d6950-213">In the **Data Sources** window, expand the **Customers** table node and select the detail node for the **Orders** table.</span></span>  
  
5.  <span data-ttu-id="d6950-214">Bu açılan türünü değiştirme **siparişleri** tıklatarak ayrıntıları tabloya **ayrıntıları** Tablo düğümü aşağı açılan listesinde.</span><span class="sxs-lookup"><span data-stu-id="d6950-214">Change the drop type of this **Orders** table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="d6950-215">Bu sürükleme **siparişleri** Tablo düğümü ikinci öğe şablonu bölgesi (üst bölge) üzerine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-215">Drag this **Orders** table node onto the item template region (the upper region) of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="d6950-216">Bir **OrdersBindingSource** bileşeni ve bir **OrdersTableAdapter** bileşen için bileşen Tepsisi eklenir.</span><span class="sxs-lookup"><span data-stu-id="d6950-216">An **OrdersBindingSource** component and an **OrdersTableAdapter** component are added to the Component Tray.</span></span>  
  
7.  <span data-ttu-id="d6950-217">Uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="d6950-217">Press F5 to run the application.</span></span> <span data-ttu-id="d6950-218">Her bir müşteri ilk seçtiğinizde <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetlemek, siparişler o müşteri görüntülenir için ikinci <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetim.</span><span class="sxs-lookup"><span data-stu-id="d6950-218">When you select each customer in the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control, the orders for that customer are displayed in the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6950-219">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d6950-219">See Also</span></span>  
 [<span data-ttu-id="d6950-220">DataRepeater denetimine giriş</span><span class="sxs-lookup"><span data-stu-id="d6950-220">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d6950-221">Nasıl yapılır: DataRepeater denetiminde veri bağlı</span><span class="sxs-lookup"><span data-stu-id="d6950-221">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d6950-222">Nasıl yapılır: ilişkisiz denetimleri DataRepeater denetiminde görüntüleme</span><span class="sxs-lookup"><span data-stu-id="d6950-222">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d6950-223">Nasıl yapılır: DataRepeater denetimi düzenini değiştirme</span><span class="sxs-lookup"><span data-stu-id="d6950-223">How to: Change the Layout of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d6950-224">Nasıl yapılır: DataRepeater denetiminde öğe üstbilgilerini görüntüleme</span><span class="sxs-lookup"><span data-stu-id="d6950-224">How to: Display Item Headers in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d6950-225">Nasıl yapılır: DataRepeater denetiminde veri arama</span><span class="sxs-lookup"><span data-stu-id="d6950-225">How to: Search Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d6950-226">Nasıl yapılır: iki DataRepeater denetimi (Visual Studio) kullanarak ana/ayrıntı formu oluşturma</span><span class="sxs-lookup"><span data-stu-id="d6950-226">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [<span data-ttu-id="d6950-227">Nasıl yapılır: DataRepeater denetiminin görünümünü değiştirme</span><span class="sxs-lookup"><span data-stu-id="d6950-227">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="d6950-228">Nasıl yapılır: DataRepeater öğelerini eklemeyi ve silmeyi devre dışı bırak</span><span class="sxs-lookup"><span data-stu-id="d6950-228">How to: Disable Adding and Deleting DataRepeater Items</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)  
 [<span data-ttu-id="d6950-229">DataRepeater denetiminde sorun giderme</span><span class="sxs-lookup"><span data-stu-id="d6950-229">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)