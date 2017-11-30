---
title: "SByte Veri Türü (Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2bcd00665ec5b8651089811a61212bfa302fe95d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="19692-102">SByte veri türü (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19692-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="19692-103">Ayrı tutma -128 değeri ile 127 arasında 8 bit (1-bayt) tamsayıları imzalanmış.</span><span class="sxs-lookup"><span data-stu-id="19692-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19692-104">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="19692-104">Remarks</span></span>

<span data-ttu-id="19692-105">Kullanım `SByte` veri türü tam veri genişliği gerektirmeyen tamsayı değerleri içeren `Integer` veya hatta yarım veri genişliği `Short`.</span><span class="sxs-lookup"><span data-stu-id="19692-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="19692-106">Bazı durumlarda, ortak dil çalışma zamanı paketi olabilir, `SByte` değişkenleri yakın işbirliği içinde ve bellek tüketimi.</span><span class="sxs-lookup"><span data-stu-id="19692-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="19692-107">Varsayılan değer olan `SByte` 0'dır.</span><span class="sxs-lookup"><span data-stu-id="19692-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="19692-108">Değişmez değer atamaları</span><span class="sxs-lookup"><span data-stu-id="19692-108">Literal assignments</span></span>
  
<span data-ttu-id="19692-109">Bildirme ve başlatma bir `SByte` değişken bir ondalık değişmez değeri, onaltılık değişmez değeri bir sekizlik değişmez değeri atama veya (Visual Basic 2017 ile ikili bir hazır değer başlayarak).</span><span class="sxs-lookup"><span data-stu-id="19692-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="19692-110">Aşağıdaki örnekte, ondalık sayı olarak, onaltılık temsil-102 tamsayılar eşit ve ikili değişmez değerler atanır `SByte` değerleri.</span><span class="sxs-lookup"><span data-stu-id="19692-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="19692-111">Bu örnek ile derleme gerektirir `/removeintchecks` derleyici anahtar.</span><span class="sxs-lookup"><span data-stu-id="19692-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> <span data-ttu-id="19692-112">Önek kullanması `&h` veya `&H` bir onaltılık değişmez değeri, öneki belirtmek için `&b` veya `&B` ikili bir hazır değer ve öneki belirtmek için `&o` veya `&O` sekizlik değişmez değeri belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="19692-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="19692-113">Ondalık değişmez değerler, önek vardır.</span><span class="sxs-lookup"><span data-stu-id="19692-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="19692-114">Visual Basic 2017 ile başlayarak, alt çizgi karakteri de kullanabilirsiniz `_`, okunabilirliğini artırmak için bir basamak ayırıcı olarak, aşağıdaki örnekte görüldüğü gibi.</span><span class="sxs-lookup"><span data-stu-id="19692-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

<span data-ttu-id="19692-115">Değişmez değer tamsayı aralığı dışında ise `SByte` (diğer bir deyişle, bu ise değerinden <xref:System.SByte.MinValue?displayProperty=nameWithType> veya daha büyük <xref:System.SByte.MaxValue?displayProperty=nameWithType>, derleme hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="19692-115">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="19692-116">Hiçbir soneki değişmez değer bir tamsayı sahip olduğunda bir [tamsayı](integer-data-type.md) algılanır.</span><span class="sxs-lookup"><span data-stu-id="19692-116">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="19692-117">Değişmez değer tamsayı aralığı dışında ise `Integer` türü, bir [uzun](long-data-type.md) algılanır.</span><span class="sxs-lookup"><span data-stu-id="19692-117">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="19692-118">Bu, önceki örneklerde, sayısal değişmez değerleri anlamına `0x9A` ve `0b10011010` 32 bit imzalı tamsayılar aşıyor 156, değerini olarak yorumlanır <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="19692-118">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="19692-119">Başarıyla bir ondalık olmayan tamsayıya atayan şöyle Kodu derlemek için bir `SByte`, aşağıdakilerden birini yapabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="19692-119">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="19692-120">Tamsayı sınırları denetimleri ile derleme tarafından devre dışı `/removeintchecks` derleyici anahtar.</span><span class="sxs-lookup"><span data-stu-id="19692-120">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="19692-121">Kullanım bir [türü karakteri](../../programming-guide\language-features\data-types/type-characters.md) atamak istediğiniz hazır değeri açıkça tanımlamak için `SByte`.</span><span class="sxs-lookup"><span data-stu-id="19692-121">Use a [type character](../../programming-guide\language-features\data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="19692-122">Aşağıdaki örnek negatif bir hazır değer atar `Short` değeri bir `SByte`.</span><span class="sxs-lookup"><span data-stu-id="19692-122">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="19692-123">Negatif sayılar için dikkat edin, yüksek sıralı bit yüksek düzey Word nümerik sabit değer olarak ayarlanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="19692-123">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="19692-124">Bizim örneğimizde söz konusu olduğunda, bu bit değişmez değeri 15 `Short` değeri.</span><span class="sxs-lookup"><span data-stu-id="19692-124">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="19692-125">Programlama ipuçları</span><span class="sxs-lookup"><span data-stu-id="19692-125">Programming tips</span></span>
  
-   <span data-ttu-id="19692-126">**CLS uyumluluğu.**</span><span class="sxs-lookup"><span data-stu-id="19692-126">**CLS Compliance.**</span></span> <span data-ttu-id="19692-127">`SByte` Veri türü değil parçası [ortak dil belirtimi](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), CLS uyumlu kod kullandığı bir bileşen kullanamayacaklarını şekilde.</span><span class="sxs-lookup"><span data-stu-id="19692-127">The `SByte` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

-   <span data-ttu-id="19692-128">**Genişletme.**</span><span class="sxs-lookup"><span data-stu-id="19692-128">**Widening.**</span></span> <span data-ttu-id="19692-129">`SByte` Veri türü widens için `Short`, `Integer`, `Long`, `Decimal`, `Single`, ve `Double`.</span><span class="sxs-lookup"><span data-stu-id="19692-129">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="19692-130">Bu dönüştürebilirsiniz anlamına gelir `SByte` karşılaşmadan olmadan bu türdeki herhangi bir <xref:System.OverflowException?displayProperty=nameWithType> hata.</span><span class="sxs-lookup"><span data-stu-id="19692-130">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="19692-131">**Karakterleri yazın.**</span><span class="sxs-lookup"><span data-stu-id="19692-131">**Type Characters.**</span></span> <span data-ttu-id="19692-132">`SByte`değişmez değer türü karakteri ya da tanımlayıcı türü karakteri içeriyor.</span><span class="sxs-lookup"><span data-stu-id="19692-132">`SByte` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="19692-133">**Framework türü.**</span><span class="sxs-lookup"><span data-stu-id="19692-133">**Framework Type.**</span></span> <span data-ttu-id="19692-134">.NET Framework'teki karşılık gelen tür <xref:System.SByte?displayProperty=nameWithType> yapısı.</span><span class="sxs-lookup"><span data-stu-id="19692-134">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="19692-135">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="19692-135">See also</span></span>

 <xref:System.SByte?displayProperty=nameWithType>  
 [<span data-ttu-id="19692-136">Veri türleri</span><span class="sxs-lookup"><span data-stu-id="19692-136">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="19692-137">Tür dönüşüm işlevleri</span><span class="sxs-lookup"><span data-stu-id="19692-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="19692-138">Dönüştürme özeti</span><span class="sxs-lookup"><span data-stu-id="19692-138">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="19692-139">Short veri türü</span><span class="sxs-lookup"><span data-stu-id="19692-139">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [<span data-ttu-id="19692-140">Integer veri türü</span><span class="sxs-lookup"><span data-stu-id="19692-140">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="19692-141">Long veri türü</span><span class="sxs-lookup"><span data-stu-id="19692-141">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [<span data-ttu-id="19692-142">Veri türlerinin etkili kullanımı</span><span class="sxs-lookup"><span data-stu-id="19692-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)