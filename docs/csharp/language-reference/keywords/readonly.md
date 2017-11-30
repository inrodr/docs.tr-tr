---
title: "readonly (C# Başvurusu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords: readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b499f9fc5121afe6c2e92bcf8c5d2ac593b4c06c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="readonly-c-reference"></a><span data-ttu-id="2f92d-102">readonly (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="2f92d-102">readonly (C# Reference)</span></span>
<span data-ttu-id="2f92d-103">`readonly` Alanları kullanabileceğiniz Değiştirici bir anahtar sözcüktür.</span><span class="sxs-lookup"><span data-stu-id="2f92d-103">The `readonly` keyword is a modifier that you can use on fields.</span></span> <span data-ttu-id="2f92d-104">Ne zaman alan bildirimini içeren bir `readonly` değiştiricisi, bildirimi tarafından sunulan alanlar atamalar yalnızca oluşabilir parçası olarak bildirimiyle veya oluşturucusu aynı sınıfta.</span><span class="sxs-lookup"><span data-stu-id="2f92d-104">When a field declaration includes a `readonly` modifier, assignments to the fields introduced by the declaration can only occur as part of the declaration or in a constructor in the same class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f92d-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="2f92d-105">Example</span></span>  
 <span data-ttu-id="2f92d-106">Bu örnekte, alanın değerini `year` yönteminde değiştirilemez `ChangeYear`rağmen sınıfı oluşturucusu değerinde atanır:</span><span class="sxs-lookup"><span data-stu-id="2f92d-106">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 <span data-ttu-id="2f92d-107">Bir değere atayabileceğiniz bir `readonly` yalnızca aşağıdaki bağlamlarda alan:</span><span class="sxs-lookup"><span data-stu-id="2f92d-107">You can assign a value to a `readonly` field only in the following contexts:</span></span>  
  
-   <span data-ttu-id="2f92d-108">Ne zaman değişkeni bildiriminde örneğin başlatılır:</span><span class="sxs-lookup"><span data-stu-id="2f92d-108">When the variable is initialized in the declaration, for example:</span></span>  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   <span data-ttu-id="2f92d-109">Bir örnek alanındaki için sınıfın örnek oluşturucuları alan bildirimini içeren veya statik bir alan için alan bildirimini içeren sınıfın statik Oluşturucusu.</span><span class="sxs-lookup"><span data-stu-id="2f92d-109">For an instance field, in the instance constructors of the class that contains the field declaration, or for a static field, in the static constructor of the class that contains the field declaration.</span></span> <span data-ttu-id="2f92d-110">Ayrıca olduğu geçirmek için geçerli tek bağlamları bunlar bir `readonly` olarak alan bir [çıkışı](../../../csharp/language-reference/keywords/out.md) veya [ref](../../../csharp/language-reference/keywords/ref.md) parametresi.</span><span class="sxs-lookup"><span data-stu-id="2f92d-110">These are also the only contexts in which it is valid to pass a `readonly` field as an [out](../../../csharp/language-reference/keywords/out.md) or [ref](../../../csharp/language-reference/keywords/ref.md) parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f92d-111">`readonly` Sözcüktür farklı [const](../../../csharp/language-reference/keywords/const.md) anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="2f92d-111">The `readonly` keyword is different from the [const](../../../csharp/language-reference/keywords/const.md) keyword.</span></span> <span data-ttu-id="2f92d-112">A `const` alan alan bildirimi sırasında yalnızca başlatılabilir.</span><span class="sxs-lookup"><span data-stu-id="2f92d-112">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="2f92d-113">A `readonly` bildirimi sırasında veya bir oluşturucuya alan başlatılabilir.</span><span class="sxs-lookup"><span data-stu-id="2f92d-113">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="2f92d-114">Bu nedenle, `readonly` alanları kullanılan Oluşturucusu bağlı olarak farklı değerlere sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="2f92d-114">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="2f92d-115">Ayrıca, ancak bir `const` alandır derleme zamanı sabiti `readonly` alan, aşağıdaki örnekte olduğu gibi çalışma zamanı sabitleri için kullanılabilir:</span><span class="sxs-lookup"><span data-stu-id="2f92d-115">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="example"></a><span data-ttu-id="2f92d-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="2f92d-116">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 <span data-ttu-id="2f92d-117">Önceki örnekte, bu gibi bir ifade kullanıyorsanız:</span><span class="sxs-lookup"><span data-stu-id="2f92d-117">In the preceding example, if you use a statement like this:</span></span>  
  
 `p2.y = 66;        // Error`  
  
 <span data-ttu-id="2f92d-118">derleyici hatası iletisi alırsınız:</span><span class="sxs-lookup"><span data-stu-id="2f92d-118">you will get the compiler error message:</span></span>  
  
 `The left-hand side of an assignment must be an l-value`  
  
 <span data-ttu-id="2f92d-119">bir sabit bir değer atamaya çalış edilirken aynı hata olduğu.</span><span class="sxs-lookup"><span data-stu-id="2f92d-119">which is the same error you get when you attempt to assign a value to a constant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="2f92d-120">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="2f92d-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2f92d-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2f92d-121">See Also</span></span>  
 [<span data-ttu-id="2f92d-122">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="2f92d-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2f92d-123">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="2f92d-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2f92d-124">C# anahtar sözcükleri</span><span class="sxs-lookup"><span data-stu-id="2f92d-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="2f92d-125">Değiştiriciler</span><span class="sxs-lookup"><span data-stu-id="2f92d-125">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="2f92d-126">const</span><span class="sxs-lookup"><span data-stu-id="2f92d-126">const</span></span>](../../../csharp/language-reference/keywords/const.md)  
 [<span data-ttu-id="2f92d-127">Alanları</span><span class="sxs-lookup"><span data-stu-id="2f92d-127">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)