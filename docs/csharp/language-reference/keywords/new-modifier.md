---
title: "new Değiştiricisi (C# Başvurusu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 28124c2f3ecef01fd4bc43fe7cfc975dd6466506
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="7f041-102">new Değiştiricisi (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="7f041-102">new Modifier (C# Reference)</span></span>
<span data-ttu-id="7f041-103">Bir bildirim değiştirici kullanıldığında `new` anahtar sözcüğü bir taban sınıftan devralınan üye açıkça gizler.</span><span class="sxs-lookup"><span data-stu-id="7f041-103">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="7f041-104">Devralınmış bir üyeyi gizleme, üye türetilmiş sürümünü temel sınıf sürümü değiştirir.</span><span class="sxs-lookup"><span data-stu-id="7f041-104">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="7f041-105">Kullanmadan üyeleri gizleyebilirsiniz rağmen `new` değiştiricisi, derleyici uyarısı alırsınız.</span><span class="sxs-lookup"><span data-stu-id="7f041-105">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="7f041-106">Kullanırsanız `new` açıkça üyesi gizlemek için bu uyarıyı bastırır.</span><span class="sxs-lookup"><span data-stu-id="7f041-106">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>  
  
 <span data-ttu-id="7f041-107">Devralınmış bir üyeyi gizlemek için aynı üye adı kullanarak türetilen sınıfta bildirme ve onunla değiştirmek `new` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="7f041-107">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="7f041-108">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="7f041-108">For example:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_1.cs)]  
  
 <span data-ttu-id="7f041-109">Bu örnekte, `BaseC.Invoke` tarafından gizli `DerivedC.Invoke`.</span><span class="sxs-lookup"><span data-stu-id="7f041-109">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="7f041-110">Alan `x` benzer ada göre değil gizlendiği etkilenmez.</span><span class="sxs-lookup"><span data-stu-id="7f041-110">The field `x` is not affected because it is not hidden by a similar name.</span></span>  
  
 <span data-ttu-id="7f041-111">Devralma yoluyla gizleme adı aşağıdaki biçimlerden birini alır:</span><span class="sxs-lookup"><span data-stu-id="7f041-111">Name hiding through inheritance takes one of the following forms:</span></span>  
  
-   <span data-ttu-id="7f041-112">Genellikle, sabit, alan, özelliği veya bir sınıf veya yapı biriminde sunulan türü adını paylaşan tüm taban sınıfı üyeleri gizler.</span><span class="sxs-lookup"><span data-stu-id="7f041-112">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span>  <span data-ttu-id="7f041-113">Özel durumlar vardır.</span><span class="sxs-lookup"><span data-stu-id="7f041-113">There are special cases.</span></span>  <span data-ttu-id="7f041-114">Örneğin, yeni bir ad alanıyla bildirirseniz `N` invocable olmayan bir türü ve bir taban türü bildirir `N` bir yöntemi olması için yeni alan çağırma söz dizimi temel bildiriminde gizlemez.</span><span class="sxs-lookup"><span data-stu-id="7f041-114">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span>  <span data-ttu-id="7f041-115">Bkz: [5.0 C# dil belirtimi](http://go.microsoft.com/fwlink/?LinkId=199552) için ayrıntıları ("İfadeleri" bölümünde "Üye araması" bölümüne bakın).</span><span class="sxs-lookup"><span data-stu-id="7f041-115">See the [C# 5.0 language specification](http://go.microsoft.com/fwlink/?LinkId=199552) for details (see section "Member Lookup" in section "Expressions").</span></span>  
  
-   <span data-ttu-id="7f041-116">Sınıfta veya yapı biriminde sunulan bir yöntemi, özellikleri, alanları ve temel sınıfı ad paylaşmak türleri gizler.</span><span class="sxs-lookup"><span data-stu-id="7f041-116">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="7f041-117">Ayrıca, aynı imzaya sahip tüm taban sınıf yöntemlerini gizler.</span><span class="sxs-lookup"><span data-stu-id="7f041-117">It also hides all base class methods that have the same signature.</span></span>  
  
-   <span data-ttu-id="7f041-118">Bir sınıf veya yapı biriminde sunulan bir dizin oluşturucu aynı imzaya sahip tüm temel sınıf dizin oluşturucular gizler.</span><span class="sxs-lookup"><span data-stu-id="7f041-118">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>  
  
 <span data-ttu-id="7f041-119">Her ikisi de kullanmak için bir hata olduğunu `new` ve [geçersiz kılma](../../../csharp/language-reference/keywords/override.md) aynı üye üzerindeki iki değiştiricileri birbirini dışlayan anlamları olduğundan.</span><span class="sxs-lookup"><span data-stu-id="7f041-119">It is an error to use both `new` and [override](../../../csharp/language-reference/keywords/override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="7f041-120">`new` Değiştiricisi aynı ada sahip yeni bir üye oluşturur ve gizli hale özgün üye neden olur.</span><span class="sxs-lookup"><span data-stu-id="7f041-120">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="7f041-121">`override` Değiştiricisi devralınmış bir üyeyi uygulamasını genişletir.</span><span class="sxs-lookup"><span data-stu-id="7f041-121">The `override` modifier extends the implementation for an inherited member.</span></span>  
  
 <span data-ttu-id="7f041-122">Kullanarak `new` değiştiricisi devralınmış bir üyeyi gizlemez bildiriminde bir uyarı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="7f041-122">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f041-123">Örnek</span><span class="sxs-lookup"><span data-stu-id="7f041-123">Example</span></span>  
 <span data-ttu-id="7f041-124">Bu örnekte, bir taban sınıf `BaseC`ve türetilmiş bir sınıf `DerivedC`, aynı alan adını kullanmak `x`, devralınan alanın değerini gizler.</span><span class="sxs-lookup"><span data-stu-id="7f041-124">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="7f041-125">Örnek kullanımını gösteren `new` değiştiricisi.</span><span class="sxs-lookup"><span data-stu-id="7f041-125">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="7f041-126">Ayrıca, temel sınıfın gizli üyeleri tam adlarını kullanarak erişmek nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="7f041-126">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="7f041-127">Örnek</span><span class="sxs-lookup"><span data-stu-id="7f041-127">Example</span></span>  
 <span data-ttu-id="7f041-128">Bu örnekte, bir iç içe geçmiş sınıf taban sınıf içinde aynı ada sahip bir sınıf gizler.</span><span class="sxs-lookup"><span data-stu-id="7f041-128">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="7f041-129">Örnek nasıl kullanılacağı ortaya `new` uyarı iletisi ve gizli sınıf üyeleri tam adlarını kullanarak erişim ortadan kaldırmak için değiştiricisi.</span><span class="sxs-lookup"><span data-stu-id="7f041-129">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_3.cs)]  
  
 <span data-ttu-id="7f041-130">Kaldırırsanız `new` değiştiricisi, program hala derleyin ve çalıştırın, ancak aşağıdaki uyarı alırsınız:</span><span class="sxs-lookup"><span data-stu-id="7f041-130">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>  
  
```  
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="7f041-131">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="7f041-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7f041-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7f041-132">See Also</span></span>  
 [<span data-ttu-id="7f041-133">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="7f041-133">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7f041-134">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="7f041-134">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7f041-135">C# anahtar sözcükleri</span><span class="sxs-lookup"><span data-stu-id="7f041-135">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="7f041-136">İşleç anahtar sözcükleri</span><span class="sxs-lookup"><span data-stu-id="7f041-136">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="7f041-137">Değiştiriciler</span><span class="sxs-lookup"><span data-stu-id="7f041-137">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="7f041-138">Geçersiz kılma ve yeni anahtar sözcüklerle sürüm oluşturma</span><span class="sxs-lookup"><span data-stu-id="7f041-138">Versioning with the Override and New Keywords</span></span>](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)  
 [<span data-ttu-id="7f041-139">Geçersiz kılma ve yeni anahtar sözcüklerin ne zaman kullanılacağını bilme</span><span class="sxs-lookup"><span data-stu-id="7f041-139">Knowing When to Use Override and New Keywords</span></span>](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)