---
title: Declare Deyimi
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Declare
- vb.Lib
- vb.Any
helpviewer_keywords:
- Lib keyword [Visual Basic]
- declaring procedures [Visual Basic], Declare statement
- functions [Visual Basic], function procedures
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- procedures [Visual Basic], external
- Alias keyword [Visual Basic]
- external references [Visual Basic], Visual Basic
- DLLs, declaring procedures
- Declare statement [Visual Basic]
- declarations [Visual Basic], external
- Visual Basic code, Function procedures
- As keyword [Visual Basic], in Declare statement
- resources [Visual Basic], declaring
- Public keyword [Visual Basic], Declare statement
- platform invoke, Visual Basic external references
- Sub procedures [Visual Basic], declarations
- APIs, declaring API functions
- Visual Basic code, Sub procedures
- Function procedures [Visual Basic], declaring
ms.assetid: d3f21fb0-b804-4c99-97ed-583b23894cf1
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2560f34a5130ef7453b50ffb4495b67bf1dfa4c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="declare-statement"></a><span data-ttu-id="403a3-102">Declare Deyimi</span><span class="sxs-lookup"><span data-stu-id="403a3-102">Declare Statement</span></span>
<span data-ttu-id="403a3-103">Bir dış dosyada uygulanan bir yordam için bir başvuru bildirir.</span><span class="sxs-lookup"><span data-stu-id="403a3-103">Declares a reference to a procedure implemented in an external file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="403a3-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="403a3-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ]  
' -or-  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _  
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _  
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]  
```  
  
## <a name="parts"></a><span data-ttu-id="403a3-105">Bölümler</span><span class="sxs-lookup"><span data-stu-id="403a3-105">Parts</span></span>  
  
|<span data-ttu-id="403a3-106">Terim</span><span class="sxs-lookup"><span data-stu-id="403a3-106">Term</span></span>|<span data-ttu-id="403a3-107">Tanım</span><span class="sxs-lookup"><span data-stu-id="403a3-107">Definition</span></span>|  
|---|---|  
|`attributelist`|<span data-ttu-id="403a3-108">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="403a3-108">Optional.</span></span> <span data-ttu-id="403a3-109">Bkz: [öznitelik listesi](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="403a3-109">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>|  
|`accessmodifier`|<span data-ttu-id="403a3-110">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="403a3-110">Optional.</span></span> <span data-ttu-id="403a3-111">Aşağıdakilerden biri olabilir:</span><span class="sxs-lookup"><span data-stu-id="403a3-111">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="403a3-112">-   [Ortak](../../../visual-basic/language-reference/modifiers/public.md)</span><span class="sxs-lookup"><span data-stu-id="403a3-112">-   [Public](../../../visual-basic/language-reference/modifiers/public.md)</span></span><br /><span data-ttu-id="403a3-113">-   [Korumalı](../../../visual-basic/language-reference/modifiers/protected.md)</span><span class="sxs-lookup"><span data-stu-id="403a3-113">-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)</span></span><br /><span data-ttu-id="403a3-114">-   [Arkadaş](../../../visual-basic/language-reference/modifiers/friend.md)</span><span class="sxs-lookup"><span data-stu-id="403a3-114">-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)</span></span><br /><span data-ttu-id="403a3-115">-   [Özel](../../../visual-basic/language-reference/modifiers/private.md)</span><span class="sxs-lookup"><span data-stu-id="403a3-115">-   [Private](../../../visual-basic/language-reference/modifiers/private.md)</span></span><br />-   `Protected Friend`<br /><br /> <span data-ttu-id="403a3-116">Bkz: [erişim düzeyini Visual Basic'te](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="403a3-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`Shadows`|<span data-ttu-id="403a3-117">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="403a3-117">Optional.</span></span> <span data-ttu-id="403a3-118">Bkz: [gölgeleri](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="403a3-118">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>|  
|`charsetmodifier`|<span data-ttu-id="403a3-119">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="403a3-119">Optional.</span></span> <span data-ttu-id="403a3-120">Karakter kümesi ve dosya belirten bilgi arayın.</span><span class="sxs-lookup"><span data-stu-id="403a3-120">Specifies character set and file search information.</span></span> <span data-ttu-id="403a3-121">Aşağıdakilerden biri olabilir:</span><span class="sxs-lookup"><span data-stu-id="403a3-121">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="403a3-122">-   [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md) (varsayılan)</span><span class="sxs-lookup"><span data-stu-id="403a3-122">-   [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md) (default)</span></span><br /><span data-ttu-id="403a3-123">-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)</span><span class="sxs-lookup"><span data-stu-id="403a3-123">-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)</span></span><br /><span data-ttu-id="403a3-124">-   [Otomatik](../../../visual-basic/language-reference/modifiers/auto.md)</span><span class="sxs-lookup"><span data-stu-id="403a3-124">-   [Auto](../../../visual-basic/language-reference/modifiers/auto.md)</span></span>|  
|`Sub`|<span data-ttu-id="403a3-125">İsteğe bağlı, ancak ya da `Sub` veya `Function` görünmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="403a3-125">Optional, but either `Sub` or `Function` must appear.</span></span> <span data-ttu-id="403a3-126">Dış yordamı bir değer döndürmüyor gösterir.</span><span class="sxs-lookup"><span data-stu-id="403a3-126">Indicates that the external procedure does not return a value.</span></span>|  
|`Function`|<span data-ttu-id="403a3-127">İsteğe bağlı, ancak ya da `Sub` veya `Function` görünmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="403a3-127">Optional, but either `Sub` or `Function` must appear.</span></span> <span data-ttu-id="403a3-128">Dış yordamı bir değer döndürür gösterir.</span><span class="sxs-lookup"><span data-stu-id="403a3-128">Indicates that the external procedure returns a value.</span></span>|  
|`name`|<span data-ttu-id="403a3-129">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="403a3-129">Required.</span></span> <span data-ttu-id="403a3-130">Bu dış başvuru adı.</span><span class="sxs-lookup"><span data-stu-id="403a3-130">Name of this external reference.</span></span> <span data-ttu-id="403a3-131">Daha fazla bilgi için bkz: [bildirilen öğe adları](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="403a3-131">For more information, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`Lib`|<span data-ttu-id="403a3-132">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="403a3-132">Required.</span></span> <span data-ttu-id="403a3-133">Tanıtır bir `Lib` dış bir yordam içeren dış dosyası (DLL ya da kod kaynak) tanımlayan yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="403a3-133">Introduces a `Lib` clause, which identifies the external file (DLL or code resource) that contains an external procedure.</span></span>|  
|`libname`|<span data-ttu-id="403a3-134">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="403a3-134">Required.</span></span> <span data-ttu-id="403a3-135">Bildirilen yordamı içeren dosyanın adı.</span><span class="sxs-lookup"><span data-stu-id="403a3-135">Name of the file that contains the declared procedure.</span></span>|  
|`Alias`|<span data-ttu-id="403a3-136">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="403a3-136">Optional.</span></span> <span data-ttu-id="403a3-137">Bildirilen yordamı, dosyanın içinde belirtilen ada göre tanımlanamıyor gösterir `name`.</span><span class="sxs-lookup"><span data-stu-id="403a3-137">Indicates that the procedure being declared cannot be identified within its file by the name specified in `name`.</span></span> <span data-ttu-id="403a3-138">Kendi Kimliği'nde belirttiğiniz `aliasname`.</span><span class="sxs-lookup"><span data-stu-id="403a3-138">You specify its identification in `aliasname`.</span></span>|  
|`aliasname`|<span data-ttu-id="403a3-139">Kullanırsanız, gerekli `Alias` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="403a3-139">Required if you use the `Alias` keyword.</span></span> <span data-ttu-id="403a3-140">Yordamın iki yoldan biriyle tanımlayan dize:</span><span class="sxs-lookup"><span data-stu-id="403a3-140">String that identifies the procedure in one of two ways:</span></span><br /><br /> <span data-ttu-id="403a3-141">Tırnak işareti içinde kendi dosya içinde yordam giriş noktası adı (`""`)</span><span class="sxs-lookup"><span data-stu-id="403a3-141">The entry point name of the procedure within its file, within quotes (`""`)</span></span><br /><br /> <span data-ttu-id="403a3-142">veya</span><span class="sxs-lookup"><span data-stu-id="403a3-142">-or-</span></span><br /><br /> <span data-ttu-id="403a3-143">Sayı işareti (`#`) dosya içinde yordam giriş noktası sıra sayısını belirten bir tamsayı ve ardından</span><span class="sxs-lookup"><span data-stu-id="403a3-143">A number sign (`#`) followed by an integer specifying the ordinal number of the procedure's entry point within its file</span></span>|  
|`parameterlist`|<span data-ttu-id="403a3-144">Yordamın kullandığı parametreler gereklidir.</span><span class="sxs-lookup"><span data-stu-id="403a3-144">Required if the procedure takes parameters.</span></span> <span data-ttu-id="403a3-145">Bkz: [parametre listesi](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="403a3-145">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`returntype`|<span data-ttu-id="403a3-146">Gerekli olursa `Function` belirtilir ve `Option Strict` olan `On`.</span><span class="sxs-lookup"><span data-stu-id="403a3-146">Required if `Function` is specified and `Option Strict` is `On`.</span></span> <span data-ttu-id="403a3-147">Yordam tarafından döndürülen değerin veri türü.</span><span class="sxs-lookup"><span data-stu-id="403a3-147">Data type of the value returned by the procedure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="403a3-148">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="403a3-148">Remarks</span></span>  
 <span data-ttu-id="403a3-149">Bazen projenizi dışında bir dosyayla (örneğin, DLL veya kod kaynağı) tanımlı bir yordam çağırma gerekir.</span><span class="sxs-lookup"><span data-stu-id="403a3-149">Sometimes you need to call a procedure defined in a file (such as a DLL or code resource) outside your project.</span></span> <span data-ttu-id="403a3-150">Bunu yaparken, Visual Basic derleyici yordamı doğru çağırmak için gereken bilgileri için yordam bulunduğu, nasıl tanımlanır, kendi arama sırası ve dönüş türü ve kullandığı dizeyi karakter kümesi gibi erişimi yok.</span><span class="sxs-lookup"><span data-stu-id="403a3-150">When you do this, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly, such as where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="403a3-151">`Declare` Deyimi dış bir yordam için bir başvuru oluşturur ve bu gerekli bilgileri sağlar.</span><span class="sxs-lookup"><span data-stu-id="403a3-151">The `Declare` statement creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="403a3-152">Kullanabileceğiniz `Declare` yalnızca modülü düzeyinde.</span><span class="sxs-lookup"><span data-stu-id="403a3-152">You can use `Declare` only at module level.</span></span> <span data-ttu-id="403a3-153">Yani *bildirimi bağlam* bir dış başvuru sınıf, yapı veya modülü olmalı ve kaynak dosyasını, ad alanı, arabirim, yordam veya blok olamaz.</span><span class="sxs-lookup"><span data-stu-id="403a3-153">This means the *declaration context* for an external reference must be a class, structure, or module, and cannot be a source file, namespace, interface, procedure, or block.</span></span> <span data-ttu-id="403a3-154">Daha fazla bilgi için bkz: [bildirim bağlamları ve varsayılan erişim düzeyleri](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="403a3-154">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="403a3-155">Dış başvuran varsayılan [ortak](../../../visual-basic/language-reference/modifiers/public.md) erişim.</span><span class="sxs-lookup"><span data-stu-id="403a3-155">External references default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span> <span data-ttu-id="403a3-156">Erişim değiştiricileri ile erişim düzeylerine göre ayarlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="403a3-156">You can adjust their access levels with the access modifiers.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="403a3-157">Kurallar</span><span class="sxs-lookup"><span data-stu-id="403a3-157">Rules</span></span>  
  
-   <span data-ttu-id="403a3-158">**Öznitelikler.**</span><span class="sxs-lookup"><span data-stu-id="403a3-158">**Attributes.**</span></span> <span data-ttu-id="403a3-159">Bir dış başvuru öznitelikleri uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="403a3-159">You can apply attributes to an external reference.</span></span> <span data-ttu-id="403a3-160">Uyguladığınız herhangi bir öznitelik etkisi projenizdeki yalnızca, dış dosyasında değil.</span><span class="sxs-lookup"><span data-stu-id="403a3-160">Any attribute you apply has effect only in your project, not in the external file.</span></span>  
  
-   <span data-ttu-id="403a3-161">**Değiştirici.**</span><span class="sxs-lookup"><span data-stu-id="403a3-161">**Modifiers.**</span></span> <span data-ttu-id="403a3-162">Dış yordamları olan örtük olarak [paylaşılan](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="403a3-162">External procedures are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="403a3-163">Kullanamazsınız `Shared` bildirme bir dış başvuru ve paylaşılan durumu değiştirilemiyor, anahtar sözcük.</span><span class="sxs-lookup"><span data-stu-id="403a3-163">You cannot use the `Shared` keyword when declaring an external reference, and you cannot alter its shared status.</span></span>  
  
     <span data-ttu-id="403a3-164">Dış bir yordam geçersiz kılma içinde katılmak, arabirim üyeleri uygulayan veya olayları işlemek.</span><span class="sxs-lookup"><span data-stu-id="403a3-164">An external procedure cannot participate in overriding, implement interface members, or handle events.</span></span> <span data-ttu-id="403a3-165">Buna göre kullanamazsınız `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements`, veya `Handles` in anahtar sözcüğü bir `Declare` deyimi.</span><span class="sxs-lookup"><span data-stu-id="403a3-165">Accordingly, you cannot use the `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements`, or `Handles` keyword in a `Declare` statement.</span></span>  
  
-   <span data-ttu-id="403a3-166">**Dış yordamın adı.**</span><span class="sxs-lookup"><span data-stu-id="403a3-166">**External Procedure Name.**</span></span> <span data-ttu-id="403a3-167">Bu dış başvuru aynı adı vermek gerekmez (içinde `name`) dış dosya içinde yordam giriş noktası adı (`aliasname`).</span><span class="sxs-lookup"><span data-stu-id="403a3-167">You do not have to give this external reference the same name (in `name`) as the procedure's entry-point name within its external file (`aliasname`).</span></span> <span data-ttu-id="403a3-168">Kullanabileceğiniz bir `Alias` yan tümcesini giriş noktası adı belirtin.</span><span class="sxs-lookup"><span data-stu-id="403a3-168">You can use an `Alias` clause to specify the entry-point name.</span></span> <span data-ttu-id="403a3-169">Bu dış yordamı aynı kapsamda bir Visual Basic ayrılmış değiştirici veya bir değişkeni, yordam ya da herhangi bir programlama öğesi olarak aynı adı taşıyorsa yararlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="403a3-169">This can be useful if the external procedure has the same name as a Visual Basic reserved modifier or a variable, procedure, or any other programming element in the same scope.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="403a3-170">Çoğu DLL'leri giriş noktası adları büyük/küçük harfe duyarlıdır.</span><span class="sxs-lookup"><span data-stu-id="403a3-170">Entry-point names in most DLLs are case-sensitive.</span></span>  
  
-   <span data-ttu-id="403a3-171">**Dış yordam numarası.**</span><span class="sxs-lookup"><span data-stu-id="403a3-171">**External Procedure Number.**</span></span> <span data-ttu-id="403a3-172">Alternatif olarak, kullanabileceğiniz bir `Alias` dışarı aktarma tablosu içindeki giriş noktası dış dosyasının sıra sayısını belirtmek için yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="403a3-172">Alternatively, you can use an `Alias` clause to specify the ordinal number of the entry point within the export table of the external file.</span></span> <span data-ttu-id="403a3-173">Bunu yapmak için başlamadan `aliasname` sayı işaretiyle (`#`).</span><span class="sxs-lookup"><span data-stu-id="403a3-173">To do this, you begin `aliasname` with a number sign (`#`).</span></span> <span data-ttu-id="403a3-174">Visual Basic'te dış yordam adı herhangi bir karaktere izin verilmiyorsa veya dış dosya adı olmadan yordamı dışarı verirse bu yararlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="403a3-174">This can be useful if any character in the external procedure name is not allowed in Visual Basic, or if the external file exports the procedure without a name.</span></span>  
  
## <a name="data-type-rules"></a><span data-ttu-id="403a3-175">Veri türü kuralları</span><span class="sxs-lookup"><span data-stu-id="403a3-175">Data Type Rules</span></span>  
  
-   <span data-ttu-id="403a3-176">**Parametre veri türleri.**</span><span class="sxs-lookup"><span data-stu-id="403a3-176">**Parameter Data Types.**</span></span> <span data-ttu-id="403a3-177">Varsa `Option Strict` olan `On`, her bir parametreyi veri türünü belirtmeniz gerekir `parameterlist`.</span><span class="sxs-lookup"><span data-stu-id="403a3-177">If `Option Strict` is `On`, you must specify the data type of each parameter in `parameterlist`.</span></span> <span data-ttu-id="403a3-178">Bu, herhangi bir veri türü ya da bir numaralandırma, yapısı, sınıf veya arabirim adı olabilir.</span><span class="sxs-lookup"><span data-stu-id="403a3-178">This can be any data type or the name of an enumeration, structure, class, or interface.</span></span> <span data-ttu-id="403a3-179">İçinde `parameterlist`, kullandığınız bir `As` yan tümcesini her parametre için geçirilecek bağımsız değişkeninin veri türü belirtin.</span><span class="sxs-lookup"><span data-stu-id="403a3-179">Within `parameterlist`, you use an `As` clause to specify the data type of the argument to be passed to each parameter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="403a3-180">Dış yordamı için .NET Framework yazılmadı varsa, veri türleri karşılık gelen ilgilenebilmek gerekir.</span><span class="sxs-lookup"><span data-stu-id="403a3-180">If the external procedure was not written for the .NET Framework, you must take care that the data types correspond.</span></span> <span data-ttu-id="403a3-181">Örneğin, bir dış başvuru bir Visual Basic 6.0 yordama bildirirseniz bir `Integer` parametre (Visual Basic 6.0 16 bit) karşılık gelen bağımsız değişken olarak tanımlamalıdır `Short` içinde `Declare` deyimi, 16 - olduğundan Visual Basic bit tamsayı yazın.</span><span class="sxs-lookup"><span data-stu-id="403a3-181">For example, if you declare an external reference to a Visual Basic 6.0 procedure with an `Integer` parameter (16 bits in Visual Basic 6.0), you must identify the corresponding argument as `Short` in the `Declare` statement, because that is the 16-bit integer type in Visual Basic.</span></span> <span data-ttu-id="403a3-182">Benzer şekilde, `Long` farklı veri genişliği Visual Basic 6. 0'dır ve `Date` farklı uygulanır.</span><span class="sxs-lookup"><span data-stu-id="403a3-182">Similarly, `Long` has a different data width in Visual Basic 6.0, and `Date` is implemented differently.</span></span>  
  
-   <span data-ttu-id="403a3-183">**Veri türü döndürür.**</span><span class="sxs-lookup"><span data-stu-id="403a3-183">**Return Data Type.**</span></span> <span data-ttu-id="403a3-184">Dış yordam bir `Function` ve `Option Strict` olan `On`, çağrıyı yapan kod döndürülen değerin veri türünü belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="403a3-184">If the external procedure is a `Function` and `Option Strict` is `On`, you must specify the data type of the value returned to the calling code.</span></span> <span data-ttu-id="403a3-185">Bu, herhangi bir veri türü ya da bir numaralandırma, yapısı, sınıf veya arabirim adı olabilir.</span><span class="sxs-lookup"><span data-stu-id="403a3-185">This can be any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="403a3-186">Visual Basic derleyici veri türlerinizi olanlar dış yordam ile uyumlu olduğunu doğrulamaz.</span><span class="sxs-lookup"><span data-stu-id="403a3-186">The Visual Basic compiler does not verify that your data types are compatible with those of the external procedure.</span></span> <span data-ttu-id="403a3-187">Bir uyuşmazlık varsa, ortak dil çalışma zamanı oluşturan bir <xref:System.Runtime.InteropServices.MarshalDirectiveException> çalışma zamanında özel durum.</span><span class="sxs-lookup"><span data-stu-id="403a3-187">If there is a mismatch, the common language runtime generates a <xref:System.Runtime.InteropServices.MarshalDirectiveException> exception at run time.</span></span>  
  
-   <span data-ttu-id="403a3-188">**Varsayılan veri türleri.**</span><span class="sxs-lookup"><span data-stu-id="403a3-188">**Default Data Types.**</span></span> <span data-ttu-id="403a3-189">Varsa `Option Strict` olan `Off` ve bir parametre veri türü belirtmeyin `parameterlist`, karşılık gelen bağımsız değişkeni Visual Basic derleyici dönüştürür [nesne veri türü](../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="403a3-189">If `Option Strict` is `Off` and you do not specify the data type of a parameter in `parameterlist`, the Visual Basic compiler converts the corresponding argument to the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="403a3-190">Benzer şekilde, belirtmezseniz `returntype`, derleyici dönüş verisi türüne olması için geçen `Object`.</span><span class="sxs-lookup"><span data-stu-id="403a3-190">Similarly, if you do not specify `returntype`, the compiler takes the return data type to be `Object`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="403a3-191">Farklı bir platformda yazılmış dış bir yordam ile çalışıyorsanız, veri türleri hakkında varsayımlar yapmak veya bunları varsayılan olarak izin vermek için tehlikeli demektir.</span><span class="sxs-lookup"><span data-stu-id="403a3-191">Because you are dealing with an external procedure that might have been written on a different platform, it is dangerous to make any assumptions about data types or to allow them to default.</span></span> <span data-ttu-id="403a3-192">Bunu varsa her parametre ve dönüş değeri veri türünü belirtmek daha güvenlidir.</span><span class="sxs-lookup"><span data-stu-id="403a3-192">It is much safer to specify the data type of every parameter and of the return value, if any.</span></span> <span data-ttu-id="403a3-193">Bu da kodunuzun okunabilirliğini artırır.</span><span class="sxs-lookup"><span data-stu-id="403a3-193">This also improves the readability of your code.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="403a3-194">Davranış</span><span class="sxs-lookup"><span data-stu-id="403a3-194">Behavior</span></span>  
  
-   <span data-ttu-id="403a3-195">**Kapsamı.**</span><span class="sxs-lookup"><span data-stu-id="403a3-195">**Scope.**</span></span> <span data-ttu-id="403a3-196">Kapsam sınıfı, yapı veya modülü boyunca bir dış başvuru kullanılıyor.</span><span class="sxs-lookup"><span data-stu-id="403a3-196">An external reference is in scope throughout its class, structure, or module.</span></span>  
  
-   <span data-ttu-id="403a3-197">**Yaşam süresi.**</span><span class="sxs-lookup"><span data-stu-id="403a3-197">**Lifetime.**</span></span> <span data-ttu-id="403a3-198">Bir dış başvuru sınıf, yapı veya içinde bildirilmiş modülü olarak aynı yaşam süresi vardır.</span><span class="sxs-lookup"><span data-stu-id="403a3-198">An external reference has the same lifetime as the class, structure, or module in which it is declared.</span></span>  
  
-   <span data-ttu-id="403a3-199">**Dış bir yordam çağırma.**</span><span class="sxs-lookup"><span data-stu-id="403a3-199">**Calling an External Procedure.**</span></span> <span data-ttu-id="403a3-200">Çağırmanız aynı şekilde dış bir yordam çağrısı bir `Function` veya `Sub` yordamı — bir değer döndürürse kullanarak bunu bir ifadede veya içinde belirterek bir [Call deyimi](../../../visual-basic/language-reference/statements/call-statement.md) bir değer döndürmezse.</span><span class="sxs-lookup"><span data-stu-id="403a3-200">You call an external procedure the same way you call a `Function` or `Sub` procedure—by using it in an expression if it returns a value, or by specifying it in a [Call Statement](../../../visual-basic/language-reference/statements/call-statement.md) if it does not return a value.</span></span>  
  
     <span data-ttu-id="403a3-201">Tam olarak belirtildiği gibi dış yordama bağımsız değişkenler geçirmek `parameterlist` içinde `Declare` deyimi.</span><span class="sxs-lookup"><span data-stu-id="403a3-201">You pass arguments to the external procedure exactly as specified by `parameterlist` in the `Declare` statement.</span></span> <span data-ttu-id="403a3-202">Parametreleri dış dosyasında başlangıçta nasıl bildirilen dikkate değil.</span><span class="sxs-lookup"><span data-stu-id="403a3-202">Do not take into account how the parameters were originally declared in the external file.</span></span> <span data-ttu-id="403a3-203">Dönüş değeri varsa, benzer şekilde, tam olarak belirtildiği gibi kullanmak `returntype` içinde `Declare` deyimi.</span><span class="sxs-lookup"><span data-stu-id="403a3-203">Similarly, if there is a return value, use it exactly as specified by `returntype` in the `Declare` statement.</span></span>  
  
-   <span data-ttu-id="403a3-204">**Karakter kümeleri.**</span><span class="sxs-lookup"><span data-stu-id="403a3-204">**Character Sets.**</span></span> <span data-ttu-id="403a3-205">Belirleyebilirsiniz `charsetmodifier` dış yordamı çağırdığında Visual Basic dizeleri nasıl hazırlanacağını.</span><span class="sxs-lookup"><span data-stu-id="403a3-205">You can specify in `charsetmodifier` how Visual Basic should marshal strings when it calls the external procedure.</span></span> <span data-ttu-id="403a3-206">`Ansi` Değiştiricisi Visual Basic ANSI değerleri, tüm dizeleri sıralama yönlendirir ve `Unicode` değiştiricisi Unicode değerleri tüm dizeleri sıralama için yönlendirir.</span><span class="sxs-lookup"><span data-stu-id="403a3-206">The `Ansi` modifier directs Visual Basic to marshal all strings to ANSI values, and the `Unicode` modifier directs it to marshal all strings to Unicode values.</span></span> <span data-ttu-id="403a3-207">`Auto` Değiştiricisi yönlendirir Visual Basic .NET Framework göre dizelerini sıralama kuralları dayalı üzerinde dış başvuru `name`, veya `aliasname` belirtilmişse.</span><span class="sxs-lookup"><span data-stu-id="403a3-207">The `Auto` modifier directs Visual Basic to marshal strings according to .NET Framework rules based on the external reference `name`, or `aliasname` if specified.</span></span> <span data-ttu-id="403a3-208">Varsayılan değer `Ansi` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="403a3-208">The default value is `Ansi`.</span></span>  
  
     <span data-ttu-id="403a3-209">`charsetmodifier`Ayrıca nasıl Visual Basic dış yordam dış dosya içinde arama belirtir.</span><span class="sxs-lookup"><span data-stu-id="403a3-209">`charsetmodifier` also specifies how Visual Basic should look up the external procedure within its external file.</span></span> <span data-ttu-id="403a3-210">`Ansi`ve `Unicode` her ikisi de arama sırasında adını değiştirmeden aramak için Visual Basic doğrudan.</span><span class="sxs-lookup"><span data-stu-id="403a3-210">`Ansi` and `Unicode` both direct Visual Basic to look it up without modifying its name during the search.</span></span> <span data-ttu-id="403a3-211">`Auto`Visual Basic çalışma zamanı platform temel karakter belirlemek ve büyük olasılıkla dış yordam adı şu şekilde değiştirmek için yönlendirir:</span><span class="sxs-lookup"><span data-stu-id="403a3-211">`Auto` directs Visual Basic to determine the base character set of the run-time platform and possibly modify the external procedure name, as follows:</span></span>  
  
    -   <span data-ttu-id="403a3-212">Windows 95, Windows 98 veya Windows Millennium Edition gibi bir ANSI platformunda ilk ad değişikliğe dış yordamını arayın.</span><span class="sxs-lookup"><span data-stu-id="403a3-212">On an ANSI platform, such as Windows 95, Windows 98, or Windows Millennium Edition, first look up the external procedure with no name modification.</span></span> <span data-ttu-id="403a3-213">Başarısız olursa, "A" dış yordam adı sonuna ve arayın yeniden.</span><span class="sxs-lookup"><span data-stu-id="403a3-213">If that fails, append "A" to the end of the external procedure name and look it up again.</span></span>  
  
    -   <span data-ttu-id="403a3-214">Windows NT, Windows 2000 veya Windows XP gibi bir Unicode platformunda ilk adı değişikliğe dış yordama bakın.</span><span class="sxs-lookup"><span data-stu-id="403a3-214">On a Unicode platform, such as Windows NT, Windows 2000, or Windows XP, first look up the external procedure with no name modification.</span></span> <span data-ttu-id="403a3-215">Başarısız olursa, append dış yordamının sonuna "W" olarak adlandırın ve arayın yeniden.</span><span class="sxs-lookup"><span data-stu-id="403a3-215">If that fails, append "W" to the end of the external procedure name and look it up again.</span></span>  
  
-   <span data-ttu-id="403a3-216">**Mekanizması.**</span><span class="sxs-lookup"><span data-stu-id="403a3-216">**Mechanism.**</span></span> <span data-ttu-id="403a3-217">Visual Basic kullanan .NET Framework *platform çağırma* çözümlemek ve dış yordamları erişmek için (PInvoke) mekanizması.</span><span class="sxs-lookup"><span data-stu-id="403a3-217">Visual Basic uses the .NET Framework *platform invoke* (PInvoke) mechanism to resolve and access external procedures.</span></span> <span data-ttu-id="403a3-218">`Declare` Deyimi ve <xref:System.Runtime.InteropServices.DllImportAttribute> sınıfını hem bu düzenek otomatik olarak kullanın ve PInvoke bilgisi gerekmez.</span><span class="sxs-lookup"><span data-stu-id="403a3-218">The `Declare` statement and the <xref:System.Runtime.InteropServices.DllImportAttribute> class both use this mechanism automatically, and you do not need any knowledge of PInvoke.</span></span> <span data-ttu-id="403a3-219">Daha fazla bilgi için bkz: [izlenecek yol: Windows API'larını çağırma](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).</span><span class="sxs-lookup"><span data-stu-id="403a3-219">For more information, see [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="403a3-220">Dış yordamı ortak dil çalışma zamanı dışında (CLR) çalıştırıyorsa, olan *yönetilmeyen kod*.</span><span class="sxs-lookup"><span data-stu-id="403a3-220">If the external procedure runs outside the common language runtime (CLR), it is *unmanaged code*.</span></span> <span data-ttu-id="403a3-221">Bu tür bir yordam, örneğin bir Win32 API işlev veya bir COM yöntemi çağırdığınızda uygulamanız güvenlik risklerine doğurabilir.</span><span class="sxs-lookup"><span data-stu-id="403a3-221">When you call such a procedure, for example a Win32 API function or a COM method, you might expose your application to security risks.</span></span> <span data-ttu-id="403a3-222">Daha fazla bilgi için bkz: [güvenli kodlama yönergeleri yönetilmeyen kod için](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md).</span><span class="sxs-lookup"><span data-stu-id="403a3-222">For more information, see [Secure Coding Guidelines for Unmanaged Code](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="403a3-223">Örnek</span><span class="sxs-lookup"><span data-stu-id="403a3-223">Example</span></span>  
 <span data-ttu-id="403a3-224">Aşağıdaki örnek, bir dış başvuru bildirir bir `Function` yordamı geçerli kullanıcı adını döndürür.</span><span class="sxs-lookup"><span data-stu-id="403a3-224">The following example declares an external reference to a `Function` procedure that returns the current user name.</span></span> <span data-ttu-id="403a3-225">Ardından bir dış yordam çağrıları `GetUserNameA` parçası olarak `getUser` yordamı.</span><span class="sxs-lookup"><span data-stu-id="403a3-225">It then calls the external procedure `GetUserNameA` as part of the `getUser` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="403a3-226">Örnek</span><span class="sxs-lookup"><span data-stu-id="403a3-226">Example</span></span>  
 <span data-ttu-id="403a3-227"><xref:System.Runtime.InteropServices.DllImportAttribute> İşlevleri yönetilmeyen kod içinde kullanma, alternatif bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="403a3-227">The <xref:System.Runtime.InteropServices.DllImportAttribute> provides an alternative way of using functions in unmanaged code.</span></span> <span data-ttu-id="403a3-228">Aşağıdaki örnekte bir içe aktarılan işlevi kullanmadan bildirir bir `Declare` deyimi.</span><span class="sxs-lookup"><span data-stu-id="403a3-228">The following example declares an imported function without using a `Declare` statement.</span></span>  
  
 [!code-vb[VbVbalrStatements#16](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_2.vb)]  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/declare-statement_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="403a3-229">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="403a3-229">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>  
 [<span data-ttu-id="403a3-230">Imports deyimi (.NET Namespace ve türü)</span><span class="sxs-lookup"><span data-stu-id="403a3-230">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="403a3-231">AddressOf işleci</span><span class="sxs-lookup"><span data-stu-id="403a3-231">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="403a3-232">Function deyimi</span><span class="sxs-lookup"><span data-stu-id="403a3-232">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="403a3-233">Sub deyimi</span><span class="sxs-lookup"><span data-stu-id="403a3-233">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="403a3-234">Parametre listesi</span><span class="sxs-lookup"><span data-stu-id="403a3-234">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [<span data-ttu-id="403a3-235">Call deyimi</span><span class="sxs-lookup"><span data-stu-id="403a3-235">Call Statement</span></span>](../../../visual-basic/language-reference/statements/call-statement.md)  
 [<span data-ttu-id="403a3-236">İzlenecek yol: Windows API'larını çağırma</span><span class="sxs-lookup"><span data-stu-id="403a3-236">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)