---
title: C# 7.2 yenilikler nelerdir?
description: "C# 7.2 yeni özellikleri genel bakış."
keywords: "C# dil tasarımında, 7.2, Visual Studio 2017,"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: a580a4a3a0a49e97ea8fb96699d1d978a9bc0a64
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2017
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="7c9ab-104">C# 7.2 yenilikler nelerdir?</span><span class="sxs-lookup"><span data-stu-id="7c9ab-104">What's new in C# 7.2</span></span>

<span data-ttu-id="7c9ab-105">C# 7.2 çok sayıda kullanışlı özelliği ekleyen başka bir nokta sürümüdür.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-105">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="7c9ab-106">Bu sürüm için bir tema, gereksiz kopya veya ayırmaları kaçınarak değer türleri ile daha verimli bir şekilde çalışıyor.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-106">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span> 

<span data-ttu-id="7c9ab-107">Kalan özellikler küçük, olması iyi özelliklerdir.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-107">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="7c9ab-108">C# 7.2 kullanan [dil sürümü seçimi](csharp-7-1.md#language-version-selection) yapılandırma öğesi derleyici dil sürümünü seçin.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-108">C# 7.2 uses the [language version selection](csharp-7-1.md#language-version-selection) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="7c9ab-109">Bu sürümdeki yeni diz özellikleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="7c9ab-109">The new language features in this release are:</span></span>

* [<span data-ttu-id="7c9ab-110">Başvuru semantiği ile değer türleri</span><span class="sxs-lookup"><span data-stu-id="7c9ab-110">Reference semantics with value types</span></span>](#reference-semantics-with-value-types)
  - <span data-ttu-id="7c9ab-111">Başvuru anlamsallarını kullanarak değer türleri ile çalışmayı etkinleştirmek sözdizimi geliştirmeleri birleşimi.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-111">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="7c9ab-112">Olmayan sondaki-adlandırılmış bağımsız değişkenler</span><span class="sxs-lookup"><span data-stu-id="7c9ab-112">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="7c9ab-113">Adlandırılmış bağımsız değişkenler konumsal değişkenleriyle izlenebilir.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-113">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="7c9ab-114">Sayısal değişmez değerlerinde başında alt çizgiler</span><span class="sxs-lookup"><span data-stu-id="7c9ab-114">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="7c9ab-115">Sayısal değişmez değerler artık yazdırılan herhangi bir rakam önce başında alt çizgi olabilir.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-115">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="7c9ab-116">`private protected`erişim değiştiricisi</span><span class="sxs-lookup"><span data-stu-id="7c9ab-116">`private protected` access modifier</span></span>](#private-protected)
  - <span data-ttu-id="7c9ab-117">`private protected` Erişim değiştiricisi aynı bütünleştirilmiş kodda türetilmiş sınıfları için erişim sağlar.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-117">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>

## <a name="reference-semantics-with-value-types"></a><span data-ttu-id="7c9ab-118">Başvuru semantiği ile değer türleri</span><span class="sxs-lookup"><span data-stu-id="7c9ab-118">Reference semantics with value types</span></span>

<span data-ttu-id="7c9ab-119">7.2 içinde sunulan dil özellikleri başvurusu semantiği kullanırken değer türleri ile çalışmanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-119">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="7c9ab-120">Başvuru türleri kullanımıyla ilişkili bellek ayırmaları yansıtılmasını olmadan kopyalama değer türleri en aza performansı artırmak için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-120">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="7c9ab-121">Özellikleri içerir:</span><span class="sxs-lookup"><span data-stu-id="7c9ab-121">The features include:</span></span>

 - <span data-ttu-id="7c9ab-122">`in` Bağımsız değişken başvuruyla geçirildi ancak çağrılan yöntemi tarafından değiştirilmeyen belirtmek üzere parametreler, değiştiricisi.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-122">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span>
 - <span data-ttu-id="7c9ab-123">`ref readonly` Değiştiricisi bir yöntem başvuruya göre değerini döndürür ancak o nesnenin yazmaları izin vermeyen belirtmek için yöntemi döndürür.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-123">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span>
 - <span data-ttu-id="7c9ab-124">`readonly struct` Yapı sabittir ve olarak iletilmesi gereken göstermek için bildirim, bir `in` üye yöntemlerinden parametresi.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-124">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span>
 - <span data-ttu-id="7c9ab-125">`ref struct` Bir yapı türü yönetilen bellek doğrudan erişir ve her zaman ayrılmış yığın göstermek için bildirim.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-125">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span>

<span data-ttu-id="7c9ab-126">Tüm bunlar hakkında daha fazla bilgi için değişiklikler okuyabilirsiniz [başvuru semantiği ile değer türleri kullanarak](../reference-semantics-with-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="7c9ab-126">You can read more about all these changes in [Using value types with reference semantics](../reference-semantics-with-value-types.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="7c9ab-127">Olmayan sondaki-adlandırılmış bağımsız değişkenler</span><span class="sxs-lookup"><span data-stu-id="7c9ab-127">Non-trailing named arguments</span></span>

<span data-ttu-id="7c9ab-128">Yöntem çağrıları şimdi bu bağımsız değişken adlı doğru konumda olduğunda, konumsal bağımsız değişkenleri koyun adlandırılmış bağımsız değişkenler kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-128">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="7c9ab-129">Daha fazla bilgi için bkz: [adlandırılmış ve isteğe bağlı bağımsız değişkenler](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="7c9ab-129">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="7c9ab-130">Sayısal değişmez değerlerinde başında alt çizgiler</span><span class="sxs-lookup"><span data-stu-id="7c9ab-130">Leading underscores in numeric literals</span></span>

<span data-ttu-id="7c9ab-131">C# 7.0 basamak ayırıcıları desteği uyarlamasını izin kaydetmedi `_` ilk karakter değişmez değeri olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-131">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="7c9ab-132">Onaltılık ve ikili sayısal değişmez değerleri şimdi başlamak ile bir `_`.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-132">Hex and binary numeric literals may now begin with an `_`.</span></span> 

<span data-ttu-id="7c9ab-133">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="7c9ab-133">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## `private protected`

<span data-ttu-id="7c9ab-134">Son olarak, yeni bir bileşik erişim değiştiricisi: `private protected` üyesi aynı bütünleştirilmiş kodda bildirilen türetilmiş sınıflar tarafından erişilebileceği gösterir.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-134">Finally, a new compound access modifier: `private protected` indicates that a member may be accessed by derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="7c9ab-135">Sırada `protected internal` türetilen sınıflar ya da aynı bütünleştirilmiş kodda olan sınıfları tarafından erişime izin veren `private protected` aynı bütünleştirilmiş kodda bildirilen türetilmiş türler erişimi sınırlar.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-135">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="7c9ab-136">Daha fazla bilgi için bkz: [erişim değiştiricileri](../language-reference/keywords/access-modifiers.md) dil başvurusu.</span><span class="sxs-lookup"><span data-stu-id="7c9ab-136">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>