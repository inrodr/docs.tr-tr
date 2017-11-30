---
title: "Çeşitli Veri Türleri (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6bb86bb6d203aa4e6bdded27a4cb78a8155ddec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="dc5d3-102">Çeşitli Veri Türleri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc5d3-102">Miscellaneous Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="dc5d3-103">rakam veya karakter doğru odaklı olmayan birkaç veri türlerini sağlar.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-103"> supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="dc5d3-104">Bunun yerine, bunlar özel verilerle gibi Evet/Hayır değerleri, tarih/saat değerleri ve nesne adresleri ilgilenir.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="dc5d3-105">Yan yana karşılaştırmasını gösteren bir tablo için [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] veri türlerini görmek [veri türleri](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="dc5d3-105">For a table showing a side-by-side comparison of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="dc5d3-106">Boolean türü</span><span class="sxs-lookup"><span data-stu-id="dc5d3-106">Boolean Type</span></span>  
 <span data-ttu-id="dc5d3-107">[Boole veri türü](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) olarak yorumlanır imzasız bir değer `True` veya `False`.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="dc5d3-108">Veri genişliği uygulama platformuna bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="dc5d3-109">Bir değişken true/false gibi yalnızca iki durumlu değerler içerebilir, Evet/Hayır, veya açık/kapalı olarak bildirme `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="dc5d3-110">Tarih türü</span><span class="sxs-lookup"><span data-stu-id="dc5d3-110">Date Type</span></span>  
 <span data-ttu-id="dc5d3-111">[Tarih veri türü](../../../../visual-basic/language-reference/data-types/date-data-type.md) tarih ve saat bilgilerini tutan bir 64-bit değeridir.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="dc5d3-112">Her artış 100 nanosaniye geçen süre (12:00 AM) başına itibaren Gregoryen takvim 1 yılının 1 Ocak, temsil eder.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="dc5d3-113">Bir değişkenin bir tarih değeri, bir saat değeri veya her ikisini içerebilir, olarak bildirme `Date`.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="dc5d3-114">Nesne türü</span><span class="sxs-lookup"><span data-stu-id="dc5d3-114">Object Type</span></span>  
 <span data-ttu-id="dc5d3-115">[Nesne veri türü](../../../../visual-basic/language-reference/data-types/object-data-type.md) noktalarını bir nesne örneği, uygulamanızda veya başka bir uygulama için bir 32 bit adresidir.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="dc5d3-116">Bir `Object` değişkeni uygulamanızın tanıdığı herhangi bir nesne ya da herhangi bir veri türünde başvurabilir.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="dc5d3-117">Bu, her ikisi de içerir *değer türleri*, gibi `Integer`, `Boolean`ve yapısı örnekleri ve *başvuru türleri*, sınıflardan gibi oluşturulan nesneler örnekleriolan`String`ve <xref:System.Windows.Forms.Form>ve dizi örnekleri.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="dc5d3-118">Derleme zamanında bilmiyorsanız sınıfının bir örneği için bir işaretçi bir değişkeni depolar veya çeşitli veri türlerinin veri gösterebilir, olarak bildirme `Object`.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="dc5d3-119">Avantajı `Object` veri türü olan, bunu herhangi bir veri türü, verileri depolamak için kullanabileceğiniz.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="dc5d3-120">Olumsuz daha fazla yürütme süresi almak ve uygulamanızı daha yavaş gerçekleştirmek yapan ek işlemleri neden olur.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="dc5d3-121">Kullanırsanız, bir `Object` değişken değer türleri için tabi *kutulama* ve *kutudan çıkarma*.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="dc5d3-122">Referans türleri için kullanırsanız, tabi *geç bağlama*.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc5d3-123">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="dc5d3-123">See Also</span></span>  
 [<span data-ttu-id="dc5d3-124">Tür karakterleri</span><span class="sxs-lookup"><span data-stu-id="dc5d3-124">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [<span data-ttu-id="dc5d3-125">Başlangıç veri türleri</span><span class="sxs-lookup"><span data-stu-id="dc5d3-125">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="dc5d3-126">Sayısal veri türleri</span><span class="sxs-lookup"><span data-stu-id="dc5d3-126">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [<span data-ttu-id="dc5d3-127">Karakter veri türleri</span><span class="sxs-lookup"><span data-stu-id="dc5d3-127">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [<span data-ttu-id="dc5d3-128">Veri türleri sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="dc5d3-128">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="dc5d3-129">Erken ve geç bağlama</span><span class="sxs-lookup"><span data-stu-id="dc5d3-129">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)