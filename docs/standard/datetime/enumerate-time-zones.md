---
title: "Nasıl yapılır: bir bilgisayarda mevcut saat dilimlerini numaralandırma"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f77afc8a0f2e6c110f4dc037c12ecc8b06908e60
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a><span data-ttu-id="afb66-102">Nasıl yapılır: bir bilgisayarda mevcut saat dilimlerini numaralandırma</span><span class="sxs-lookup"><span data-stu-id="afb66-102">How to: Enumerate time zones present on a computer</span></span>

<span data-ttu-id="afb66-103">Başarıyla atanan bir saat dilimi ile çalışma, saat dilimi bilgilerini sistemi için kullanılabilir olmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="afb66-103">Successfully working with a designated time zone requires that information about that time zone be available to the system.</span></span> <span data-ttu-id="afb66-104">Windows XP ve Windows Vista işletim sistemleri, kayıt defterinde bu bilgileri depolar.</span><span class="sxs-lookup"><span data-stu-id="afb66-104">The Windows XP and Windows Vista operating systems store this information in the registry.</span></span> <span data-ttu-id="afb66-105">Ancak, dünyanın her yerinde mevcut saat dilimlerini toplam sayısı büyük olsa da, kayıt defteri bunları yalnızca bir alt hakkında bilgiler içerir.</span><span class="sxs-lookup"><span data-stu-id="afb66-105">However, although the total number of time zones that exist throughout the world is large, the registry contains information about only a subset of them.</span></span> <span data-ttu-id="afb66-106">Ayrıca, kayıt defteri kasıtlı ve yanlışlıkla değiştirilebilir içeriği olan bir dinamik yapısıdır.</span><span class="sxs-lookup"><span data-stu-id="afb66-106">In addition, the registry itself is a dynamic structure whose contents are subject to both deliberate and accidental change.</span></span> <span data-ttu-id="afb66-107">Sonuç olarak, uygulama her zaman belirli bir saat dilimi tanımlı ve kullanılabilir bir sistemde olduğunu varsayın olamaz.</span><span class="sxs-lookup"><span data-stu-id="afb66-107">As a result, an application cannot always assume that a particular time zone is defined and available on a system.</span></span> <span data-ttu-id="afb66-108">İlk saat dilimi bilgileri uygulamaları pek çok uygulama gerekli saat dilimleri yerel sistem üzerinde kullanılabilir olup olmadığını belirlemek ya da kullanıcı seçmek için saat dilimleri listesini vermek için adımdır.</span><span class="sxs-lookup"><span data-stu-id="afb66-108">The first step for many applications that use time zone information applications is to determine whether required time zones are available on the local system, or to give the user a list of time zones from which to select.</span></span> <span data-ttu-id="afb66-109">Bu, bir uygulamanın yerel sistemde tanımlanan saat dilimlerini numaralandırma gerektirir.</span><span class="sxs-lookup"><span data-stu-id="afb66-109">This requires that an application enumerate the time zones defined on a local system.</span></span>

> [!NOTE]
> <span data-ttu-id="afb66-110">Bir uygulamanın yerel sistemde tanımlı değil belirli bir saat dilimi varlığına dayalıysa, seri hale getirme ve seri durumdan saat dilimi bilgilerini uygulamanın varlığını emin olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="afb66-110">If an application relies on the presence of a particular time zone that may not be defined on a local system, the application can ensure its presence by serializing and deserializing information about the time zone.</span></span> <span data-ttu-id="afb66-111">Uygulama kullanıcısı seçebilmesi saat dilimi sonra bir liste denetimini eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="afb66-111">The time zone can then be added to a list control so that the application user can select it.</span></span> <span data-ttu-id="afb66-112">Ayrıntılar için bkz [nasıl yapılır: Kaydet saat dilimlerini katıştırılmış kaynağa](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) ve [nasıl yapılır: katıştırılmış bir kaynaktan saat dilimlerini geri yükleme](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="afb66-112">For details, see [How to: Save Time Zones to an Embedded Resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) and [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span></span>

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a><span data-ttu-id="afb66-113">Yerel sistemdeki saat dilimlerini numaralandırma için</span><span class="sxs-lookup"><span data-stu-id="afb66-113">To enumerate the time zones present on the local system</span></span>

1. <span data-ttu-id="afb66-114">Çağrı <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="afb66-114">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="afb66-115">Genel yöntem <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> koleksiyonu <xref:System.TimeZoneInfo> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="afb66-115">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span> <span data-ttu-id="afb66-116">Koleksiyon girdileri göre sıralanır kendi <xref:System.TimeZoneInfo.DisplayName%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="afb66-116">The entries in the collection are sorted by their <xref:System.TimeZoneInfo.DisplayName%2A> property.</span></span> <span data-ttu-id="afb66-117">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="afb66-117">For example:</span></span>

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. <span data-ttu-id="afb66-118">Tek tek listeleme <xref:System.TimeZoneInfo> kullanarak koleksiyonundaki nesneleri bir `foreach` döngüde (C# ' ta) veya bir `For Each`...`Next`</span><span class="sxs-lookup"><span data-stu-id="afb66-118">Enumerate the individual <xref:System.TimeZoneInfo> objects in the collection by using a `foreach` loop (in C#) or a `For Each`…`Next`</span></span> <span data-ttu-id="afb66-119">(Visual Basic'te) döngü ve her nesne üzerinde gerekli herhangi bir işlem gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="afb66-119">loop (in Visual Basic), and perform any necessary processing on each object.</span></span> <span data-ttu-id="afb66-120">Örneğin, aşağıdaki kodu numaralandırır <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> koleksiyonu <xref:System.TimeZoneInfo> nesne içinde döndürülen adım 1 ve her bir saat dilimi konsolunda görünen adını listeler.</span><span class="sxs-lookup"><span data-stu-id="afb66-120">For example, the following code enumerates the <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects returned in step 1 and lists the display name of each time zone on the console.</span></span>

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a><span data-ttu-id="afb66-121">Saat dilimleri yerel sistemde listesini içeren kullanıcı sunmak için</span><span class="sxs-lookup"><span data-stu-id="afb66-121">To present the user with a list of time zones present on the local system</span></span>

1. <span data-ttu-id="afb66-122">Çağrı <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="afb66-122">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="afb66-123">Genel yöntem <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> koleksiyonu <xref:System.TimeZoneInfo> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="afb66-123">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span>

2. <span data-ttu-id="afb66-124">Adım 1'de döndürülen koleksiyon atamak `DataSource` özelliği bir Windows forms ya da ASP.NET denetim listesi.</span><span class="sxs-lookup"><span data-stu-id="afb66-124">Assign the collection returned in step 1 to the `DataSource` property of a Windows forms or ASP.NET list control.</span></span>

3. <span data-ttu-id="afb66-125">Alma <xref:System.TimeZoneInfo> kullanıcının seçtiği nesnesi.</span><span class="sxs-lookup"><span data-stu-id="afb66-125">Retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span>

<span data-ttu-id="afb66-126">Örnek bir Windows uygulaması için bir çizim verilmektedir.</span><span class="sxs-lookup"><span data-stu-id="afb66-126">The example provides an illustration for a Windows application.</span></span>

## <a name="example"></a><span data-ttu-id="afb66-127">Örnek</span><span class="sxs-lookup"><span data-stu-id="afb66-127">Example</span></span>

<span data-ttu-id="afb66-128">Örnek bir liste kutusunda bir sistemde tanımlanan saat dilimlerini görüntüleyen bir Windows uygulaması başlatır.</span><span class="sxs-lookup"><span data-stu-id="afb66-128">The example starts a Windows application that displays the time zones defined on a system in a list box.</span></span> <span data-ttu-id="afb66-129">Örnek sonra değerini içeren bir iletişim kutusu görüntüler <xref:System.TimeZoneInfo.DisplayName%2A> kullanıcı tarafından seçilen saat dilimi nesnesinin özelliği.</span><span class="sxs-lookup"><span data-stu-id="afb66-129">The example then displays a dialog box that contains the value of the <xref:System.TimeZoneInfo.DisplayName%2A> property of the time zone object selected by the user.</span></span>

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

<span data-ttu-id="afb66-130">En, Denetim listesi (gibi <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> veya <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> denetimi) nesne değişkenleri koleksiyonu atamanızı izin kendi `DataSource` özelliği o koleksiyona uygulayan sürece <xref:System.Collections.IEnumerable> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="afb66-130">Most list controls (such as the <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> or <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> control) allow you to assign a collection of object variables to their `DataSource` property as long as that collection implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="afb66-131">(Genel <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> sınıfı yapar.) Koleksiyonda tek bir nesneyi görüntülemek için bu nesnenin denetimi çağırır `ToString` nesneyi göstermek için kullanılan dize ayıklamak için yöntem.</span><span class="sxs-lookup"><span data-stu-id="afb66-131">(The generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class does this.) To display an individual object in the collection, the control calls that object's `ToString` method to extract the string that is used to represent the object.</span></span> <span data-ttu-id="afb66-132">Durumunda <xref:System.TimeZoneInfo> nesneleri `ToString` yöntemi döndürür <xref:System.TimeZoneInfo> nesnenin görünen adını (değerini kendi <xref:System.TimeZoneInfo.DisplayName%2A> özelliği).</span><span class="sxs-lookup"><span data-stu-id="afb66-132">In the case of <xref:System.TimeZoneInfo> objects, the `ToString` method returns the <xref:System.TimeZoneInfo> object's display name (the value of its <xref:System.TimeZoneInfo.DisplayName%2A> property).</span></span>

> [!NOTE]
> <span data-ttu-id="afb66-133">Liste denetimleri nesnenin çağırması nedeniyle `ToString` yöntemi, bir koleksiyonu atayabilirsiniz <xref:System.TimeZoneInfo> denetim nesnelere sahip her nesne için anlamlı bir ad görüntülemek ve almak denetimi <xref:System.TimeZoneInfo> kullanıcının seçtiği nesnesi.</span><span class="sxs-lookup"><span data-stu-id="afb66-133">Because list controls call an object's `ToString` method, you can assign a collection of <xref:System.TimeZoneInfo> objects to the control, have the control display a meaningful name for each object, and retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span> <span data-ttu-id="afb66-134">Bu koleksiyondaki her nesne için bir dize ayıklamak, denetimin sırayla atanmış bir koleksiyon için dize Ata gereğini ortadan kaldırır `DataSource` özelliği, kullanıcı seçildi dizesi alma ve nesne ayıklamak için bu dizeyi kullanın Bu BT açıklar.</span><span class="sxs-lookup"><span data-stu-id="afb66-134">This eliminates the need to extract a string for each object in the collection, assign the string to a collection that is in turn assigned to the control's `DataSource` property, retrieve the string the user has selected, and then use this string to extract the object that it describes.</span></span> 

## <a name="compiling-the-code"></a><span data-ttu-id="afb66-135">Kod derleme</span><span class="sxs-lookup"><span data-stu-id="afb66-135">Compiling the code</span></span>

<span data-ttu-id="afb66-136">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="afb66-136">This example requires:</span></span>

* <span data-ttu-id="afb66-137">Bir başvuru System.Core.dll projeye eklenmesini.</span><span class="sxs-lookup"><span data-stu-id="afb66-137">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="afb66-138">Şu ad alanlarından alınan olduğunu:</span><span class="sxs-lookup"><span data-stu-id="afb66-138">That the following namespaces be imported:</span></span>

  <span data-ttu-id="afb66-139"><xref:System>(C# kodunda)</span><span class="sxs-lookup"><span data-stu-id="afb66-139"><xref:System> (in C# code)</span></span>

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a><span data-ttu-id="afb66-140">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="afb66-140">See also</span></span>

<span data-ttu-id="afb66-141">[Tarih, saat ve saat dilimleri](../../../docs/standard/datetime/index.md)
[nasıl yapılır: saat dilimlerini katıştırılmış kaynağa kaydetme](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[nasıl yapılır: katıştırılmış bir kaynaktan saat dilimlerini geri yükleme](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span><span class="sxs-lookup"><span data-stu-id="afb66-141">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span></span>