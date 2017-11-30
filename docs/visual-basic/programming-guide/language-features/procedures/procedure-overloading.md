---
title: "Yordam Aşırı Yüklemesi (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65fd5a6763752c616f13891bfa5acabff6115d7c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="6a868-102">Yordam Aşırı Yüklemesi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a868-102">Procedure Overloading (Visual Basic)</span></span>
<span data-ttu-id="6a868-103">*Aşırı yükleme* bir yordam, aynı adlı ancak farklı parametre listeleri kullanarak birden çok sürümlerde tanımlama anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="6a868-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="6a868-104">Aşırı yükleme amacı, ada göre ayırt zorunda kalmadan bir yordamın birden fazla yakından ilgili sürümünü tanımlamaktır.</span><span class="sxs-lookup"><span data-stu-id="6a868-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="6a868-105">Parametre listesi değiştirerek bunu yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6a868-105">You do this by varying the parameter list.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="6a868-106">Kuralları aşırı yüklemesi</span><span class="sxs-lookup"><span data-stu-id="6a868-106">Overloading Rules</span></span>  
 <span data-ttu-id="6a868-107">Bir yordamı aşırı yükleme oluştuğunda aşağıdaki kurallar geçerli olur:</span><span class="sxs-lookup"><span data-stu-id="6a868-107">When you overload a procedure, the following rules apply:</span></span>  
  
-   <span data-ttu-id="6a868-108">**Aynı ada**.</span><span class="sxs-lookup"><span data-stu-id="6a868-108">**Same Name**.</span></span> <span data-ttu-id="6a868-109">Aşırı yüklenmiş her sürümü aynı yordam adı kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="6a868-109">Each overloaded version must use the same procedure name.</span></span>  
  
-   <span data-ttu-id="6a868-110">**Farklı imza**.</span><span class="sxs-lookup"><span data-stu-id="6a868-110">**Different Signature**.</span></span> <span data-ttu-id="6a868-111">Aşırı yüklenmiş her sürümü diğer aşırı yüklenmiş sürümleri aşağıdaki bakımlardan en az birinde farklı gerekir:</span><span class="sxs-lookup"><span data-stu-id="6a868-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>  
  
    -   <span data-ttu-id="6a868-112">Parametre sayısı</span><span class="sxs-lookup"><span data-stu-id="6a868-112">Number of parameters</span></span>  
  
    -   <span data-ttu-id="6a868-113">Parametreler sırası</span><span class="sxs-lookup"><span data-stu-id="6a868-113">Order of the parameters</span></span>  
  
    -   <span data-ttu-id="6a868-114">Parametre veri türleri</span><span class="sxs-lookup"><span data-stu-id="6a868-114">Data types of the parameters</span></span>  
  
    -   <span data-ttu-id="6a868-115">Tür parametreleri (için genel bir yordam) sayısı</span><span class="sxs-lookup"><span data-stu-id="6a868-115">Number of type parameters (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="6a868-116">Dönüş türü (yalnızca için bir dönüşüm işleci)</span><span class="sxs-lookup"><span data-stu-id="6a868-116">Return type (only for a conversion operator)</span></span>  
  
     <span data-ttu-id="6a868-117">Yordam adı ile birlikte önceki öğeler toplu olarak adlandırılır *imza* yordamın.</span><span class="sxs-lookup"><span data-stu-id="6a868-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="6a868-118">Aşırı yüklenmiş bir yordamı çağırdığınızda derleyici imza çağrı düzgün tanımını eşleşip eşleşmediğini kontrol için kullanır.</span><span class="sxs-lookup"><span data-stu-id="6a868-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>  
  
-   <span data-ttu-id="6a868-119">**İmza parçası olmayan öğeler**.</span><span class="sxs-lookup"><span data-stu-id="6a868-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="6a868-120">İmza değişen olmadan bir yordamı aşırı yükleme yapılamıyor.</span><span class="sxs-lookup"><span data-stu-id="6a868-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="6a868-121">Özellikle, yalnızca bir veya daha fazla aşağıdaki öğelerden birini değiştirerek bir yordamı aşırı olamaz:</span><span class="sxs-lookup"><span data-stu-id="6a868-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>  
  
    -   <span data-ttu-id="6a868-122">Yordam değiştiricisi anahtar sözcükler gibi `Public`, `Shared`, ve`Static`</span><span class="sxs-lookup"><span data-stu-id="6a868-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>  
  
    -   <span data-ttu-id="6a868-123">Parametresi veya parametre adlarını yazın</span><span class="sxs-lookup"><span data-stu-id="6a868-123">Parameter or type parameter names</span></span>  
  
    -   <span data-ttu-id="6a868-124">Tür parametresi kısıtlamaları (için genel bir yordam)</span><span class="sxs-lookup"><span data-stu-id="6a868-124">Type parameter constraints (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="6a868-125">Parametresi değiştiricisi anahtar sözcükler gibi `ByRef` ve`Optional`</span><span class="sxs-lookup"><span data-stu-id="6a868-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>  
  
    -   <span data-ttu-id="6a868-126">Olup bir değer döndürür</span><span class="sxs-lookup"><span data-stu-id="6a868-126">Whether it returns a value</span></span>  
  
    -   <span data-ttu-id="6a868-127">Dönüş değeri (dışında bir dönüşüm işleci) veri türü</span><span class="sxs-lookup"><span data-stu-id="6a868-127">The data type of the return value (except for a conversion operator)</span></span>  
  
     <span data-ttu-id="6a868-128">Önceki listedeki öğeler imza parçası değildir.</span><span class="sxs-lookup"><span data-stu-id="6a868-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="6a868-129">Aşırı yüklenmiş sürümler arasında ayırt etmek için kullanamazsınız rağmen düzgün şekilde kendi imzaları göre ayırt edilen aşırı yüklenmiş sürümleri arasında farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="6a868-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>  
  
-   <span data-ttu-id="6a868-130">**Geç bağlama bağımsız değişkenleri**.</span><span class="sxs-lookup"><span data-stu-id="6a868-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="6a868-131">Geç bağlama nesne değişkeni aşırı yüklenmiş bir sürüme geçirmek istiyorsanız, uygun parametre olarak bildirilmelidir <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="6a868-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>  
  
## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="6a868-132">Bir yordamın birden fazla sürümünü</span><span class="sxs-lookup"><span data-stu-id="6a868-132">Multiple Versions of a Procedure</span></span>  
 <span data-ttu-id="6a868-133">Yazmakta olduğunuz varsayalım bir `Sub` adıyla veya hesap numarası müşteriye başvurabileceğiniz istediğiniz bir müşterinin bakiyesini ve karşı bir işlem sonrası için yordamı.</span><span class="sxs-lookup"><span data-stu-id="6a868-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="6a868-134">Bunu yapabilmek için iki farklı tanımlayabilirsiniz `Sub` aşağıdaki örnekteki gibi yordamlar:</span><span class="sxs-lookup"><span data-stu-id="6a868-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#73](./codesnippet/VisualBasic/procedure-overloading_1.vb)]  
  
### <a name="overloaded-versions"></a><span data-ttu-id="6a868-135">Aşırı yüklenmiş sürümleri</span><span class="sxs-lookup"><span data-stu-id="6a868-135">Overloaded Versions</span></span>  
 <span data-ttu-id="6a868-136">Tek bir yordam adı aşırı yüklemeyi alternatiftir.</span><span class="sxs-lookup"><span data-stu-id="6a868-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="6a868-137">Kullanabileceğiniz [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) anahtar bir sürümünü yordamı her parametre listesi için aşağıdaki gibi tanımlayın:</span><span class="sxs-lookup"><span data-stu-id="6a868-137">You can use the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/procedure-overloading_2.vb)]  
  
#### <a name="additional-overloads"></a><span data-ttu-id="6a868-138">Ek aşırı yüklemeleri</span><span class="sxs-lookup"><span data-stu-id="6a868-138">Additional Overloads</span></span>  
 <span data-ttu-id="6a868-139">Ayrıca bir işlem tutarı ya da kabul etmek istiyorsanız `Decimal` veya `Single`, daha fazla aşırı `post` bu değişim için izin vermek için.</span><span class="sxs-lookup"><span data-stu-id="6a868-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="6a868-140">Bu olmanızın her bir önceki örnekte aşırı yüklemeleri için dört olurdu `Sub` yordamları, aynı ada sahip tüm ancak dört farklı imzalar.</span><span class="sxs-lookup"><span data-stu-id="6a868-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>  
  
## <a name="advantages-of-overloading"></a><span data-ttu-id="6a868-141">Aşırı yükleme avantajları</span><span class="sxs-lookup"><span data-stu-id="6a868-141">Advantages of Overloading</span></span>  
 <span data-ttu-id="6a868-142">Bir yordamı aşırı yükleme avantajı çağrının esneklik olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="6a868-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="6a868-143">Kullanmak için `post` yordamı çağıran kodu olarak ya da müşteri kimliği elde edebilirsiniz önceki örnekte bildirilen bir `String` veya bir `Integer`ve ardından her iki durumda da aynı yordamı çağırın.</span><span class="sxs-lookup"><span data-stu-id="6a868-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="6a868-144">Aşağıdaki örnekte bu gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="6a868-144">The following example illustrates this:</span></span>  
  
 [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/procedure-overloading_3.vb)]  
  
 [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/procedure-overloading_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6a868-145">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6a868-145">See Also</span></span>  
 [<span data-ttu-id="6a868-146">Yordamları</span><span class="sxs-lookup"><span data-stu-id="6a868-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="6a868-147">Nasıl yapılır: bir yordamın birden fazla sürümünü tanımlama</span><span class="sxs-lookup"><span data-stu-id="6a868-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="6a868-148">Nasıl yapılır: aşırı yüklenmiş bir yordamı çağırma</span><span class="sxs-lookup"><span data-stu-id="6a868-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="6a868-149">Nasıl yapılır: isteğe bağlı parametreler isteyen bir yordamı aşırı yükleme</span><span class="sxs-lookup"><span data-stu-id="6a868-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="6a868-150">Nasıl yapılır: belirsiz sayıda parametre isteyen bir yordamı aşırı yükleme</span><span class="sxs-lookup"><span data-stu-id="6a868-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="6a868-151">Yordamları aşırı yüklemeye ilişkin düşünceler</span><span class="sxs-lookup"><span data-stu-id="6a868-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="6a868-152">Aşırı yükleme çözümü</span><span class="sxs-lookup"><span data-stu-id="6a868-152">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="6a868-153">Aşırı yüklemeler</span><span class="sxs-lookup"><span data-stu-id="6a868-153">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="6a868-154">Visual Basic'de genel türler</span><span class="sxs-lookup"><span data-stu-id="6a868-154">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)