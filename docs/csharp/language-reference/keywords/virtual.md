---
title: "virtual (C# Başvurusu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- virtual_CSharpKeyword
- virtual
helpviewer_keywords: virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
caps.latest.revision: "26"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dce3333646bca6f558e3760849b6cffdb34a6c0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="virtual-c-reference"></a><span data-ttu-id="ef9f6-102">virtual (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="ef9f6-102">virtual (C# Reference)</span></span>
<span data-ttu-id="ef9f6-103">`virtual` Anahtar sözcüğü bir yöntemi, özelliği, dizin oluşturucu veya olay bildiriminin değiştirebilir ve türetilen bir sınıfta geçersiz kılınmak üzere izin için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-103">The `virtual` keyword is used to modify a method, property, indexer, or event declaration and allow for it to be overridden in a derived class.</span></span> <span data-ttu-id="ef9f6-104">Örneğin, bu yöntem, devralınan herhangi bir sınıf tarafından geçersiz kılınabilir:</span><span class="sxs-lookup"><span data-stu-id="ef9f6-104">For example, this method can be overridden by any class that inherits it:</span></span>  
  
```  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 <span data-ttu-id="ef9f6-105">Uygulaması sanal bir üyesi tarafından değiştirilebilir bir [geçersiz kılma üye](../../../csharp/language-reference/keywords/override.md) türetilmiş bir sınıf içinde.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-105">The implementation of a virtual member can be changed by an [overriding member](../../../csharp/language-reference/keywords/override.md) in a derived class.</span></span> <span data-ttu-id="ef9f6-106">Nasıl kullanılacağı hakkında daha fazla bilgi için `virtual` anahtar sözcüğü, bkz: [geçersiz kılma ve yeni anahtar sözcüklerle sürüm oluşturma](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) ve [kullanmak geçersiz kılma ve yeni anahtar sözcüklerin için bilerek olduğunda](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="ef9f6-106">For more information about how to use the `virtual` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing When to Use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef9f6-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ef9f6-107">Remarks</span></span>  
 <span data-ttu-id="ef9f6-108">Sanal bir yöntem çağrıldığında, nesnenin çalışma zamanı türü için geçersiz kılma bir üye denetlenir.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-108">When a virtual method is invoked, the run-time type of the object is checked for an overriding member.</span></span> <span data-ttu-id="ef9f6-109">Türetilmiş bir sınıf üyesi kıldıysa, özgün üye olabilir en çok türetilen sınıfı geçersiz kılan üye denir.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-109">The overriding member in the most derived class is called, which might be the original member, if no derived class has overridden the member.</span></span>  
  
 <span data-ttu-id="ef9f6-110">Varsayılan olarak, sanal olmayan yöntemleridir.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-110">By default, methods are non-virtual.</span></span> <span data-ttu-id="ef9f6-111">Sanal olmayan bir yöntem geçersiz kılamaz.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-111">You cannot override a non-virtual method.</span></span>  
  
 <span data-ttu-id="ef9f6-112">Kullanamazsınız `virtual` değiştiricisi ile `static`, `abstract`, `private`, veya `override` değiştiricileri.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-112">You cannot use the `virtual` modifier with the `static`, `abstract`, `private`, or `override` modifiers.</span></span> <span data-ttu-id="ef9f6-113">Aşağıdaki örnek, bir sanal özelliği gösterir:</span><span class="sxs-lookup"><span data-stu-id="ef9f6-113">The following example shows a virtual property:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]  
  
 <span data-ttu-id="ef9f6-114">Sanal özellikler bildirim ve çağırma söz dizimi farklılıkları dışında soyut yöntemler gibi davranır.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-114">Virtual properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
-   <span data-ttu-id="ef9f6-115">Kullanmak için bir hata olduğunu `virtual` bir statik özelliğe değiştiricisi.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-115">It is an error to use the `virtual` modifier on a static property.</span></span>  
  
-   <span data-ttu-id="ef9f6-116">Sanal bir devralınan özelliği kullanan bir özellik bildirimi dahil ederek türetilen bir sınıfta kılınabilir `override` değiştiricisi.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-116">A virtual inherited property can be overridden in a derived class by including a property declaration that uses the `override` modifier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef9f6-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="ef9f6-117">Example</span></span>  
 <span data-ttu-id="ef9f6-118">Bu örnekte, `Shape` sınıfı içeren iki koordinat `x`, `y`ve `Area()` sanal yöntemi.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-118">In this example, the `Shape` class contains the two coordinates `x`, `y`, and the `Area()` virtual method.</span></span> <span data-ttu-id="ef9f6-119">Farklı şekil sınıfları gibi `Circle`, `Cylinder`, ve `Sphere` devral `Shape` sınıfı ve yüzey alanını her şekil için hesaplanır.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-119">Different shape classes such as `Circle`, `Cylinder`, and `Sphere` inherit the `Shape` class, and the surface area is calculated for each figure.</span></span> <span data-ttu-id="ef9f6-120">Her türetilmiş bir sınıf, geçersiz kılma uyarlamasını kendi sahip `Area()`.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-120">Each derived class has it own override implementation of `Area()`.</span></span>  
  
 <span data-ttu-id="ef9f6-121">Dikkat devralınan sınıfları `Circle`, `Sphere`, ve `Cylinder` tüm taban sınıf başlatmak oluşturucular aşağıdaki bildiriminde gösterildiği gibi kullanın.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-121">Notice that the inherited classes `Circle`, `Sphere`, and `Cylinder` all use constructors that initialize the base class, as shown in the following declaration.</span></span>  
  
```  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 <span data-ttu-id="ef9f6-122">Aşağıdaki programı hesaplar ve uygun uygulanması harekete geçirerek her şekil için uygun alanı görüntüler `Area()` yöntemiyle ilişkili nesne göre yöntemi.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-122">The following program calculates and displays the appropriate area for each figure by invoking the appropriate implementation of the `Area()` method, according to the object that is associated with the method.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="ef9f6-123">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="ef9f6-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ef9f6-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ef9f6-124">See Also</span></span>  
 [<span data-ttu-id="ef9f6-125">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="ef9f6-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ef9f6-126">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="ef9f6-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ef9f6-127">Değiştiriciler</span><span class="sxs-lookup"><span data-stu-id="ef9f6-127">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="ef9f6-128">C# anahtar sözcükleri</span><span class="sxs-lookup"><span data-stu-id="ef9f6-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ef9f6-129">Çok biçimlilik</span><span class="sxs-lookup"><span data-stu-id="ef9f6-129">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
 [<span data-ttu-id="ef9f6-130">Özet</span><span class="sxs-lookup"><span data-stu-id="ef9f6-130">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
 [<span data-ttu-id="ef9f6-131">geçersiz kılma</span><span class="sxs-lookup"><span data-stu-id="ef9f6-131">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
 [<span data-ttu-id="ef9f6-132">Yeni</span><span class="sxs-lookup"><span data-stu-id="ef9f6-132">new</span></span>](../../../csharp/language-reference/keywords/new.md)