---
title: "Özel korumalı (C# Başvurusu)"
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: 5f7abd2569d5bad5af64161042e4e5d21e741c8c
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2017
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="d8753-102">Özel korumalı (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="d8753-102">private protected (C# Reference)</span></span>
<span data-ttu-id="d8753-103">`private protected` Anahtar sözcüğü birleşimi olan bir üye erişim değiştiricisi.</span><span class="sxs-lookup"><span data-stu-id="d8753-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="d8753-104">Özel bir korumalı üye içeren sınıfından ancak kendi içeren derleme içinde yalnızca türetilmiş türler tarafından erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="d8753-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="d8753-105">Bir karşılaştırması `private protected` diğer erişim değiştiricileri ile bkz [erişilebilirlik düzeyleri](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d8753-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="d8753-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="d8753-106">Example</span></span>  
 <span data-ttu-id="d8753-107">Yalnızca statik değişkeni türetilmiş sınıf türü türündeyse bir taban sınıf, özel korumalı üyesi içeren derleme türetilmiş türlerde erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="d8753-107">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="d8753-108">Örneğin, aşağıdaki kod kesimi göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="d8753-108">For example, consider the following code segment:</span></span>  
  
 ```
 // Assembly1.cs  
 // Compile with: /target:library  
 public class BaseClass
 {
     private protected int myValue = 0;
 }
 
 public class DerivedClass1 : BaseClass
 {
     void Access()
     {
         BaseClass baseObject = new BaseClass();
 
         // Error CS1540, because myValue can only be accessed by
         // classes derived from BaseClass.
         // baseObject.myValue = 5;  
 
         // OK, accessed through the current derived class instance
         myValue = 5;
     }
 }
```  
  
```  
 // Assembly2.cs  
 // Compile with: /reference:Assembly1.dll  
 class DerivedClass2 : BaseClass
 {
     void Access()
     {
         // Error CS0122, because myValue can only be
         // accessed by types in Assembly1
         // myValue = 10;
     }
 }
```  
 <span data-ttu-id="d8753-109">Bu örnek iki dosya içerir `Assembly1.cs` ve `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="d8753-109">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="d8753-110">İlk dosya ortak bir taban sınıf içeren `BaseClass`ve bu sınıftan türetilen tür `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="d8753-110">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="d8753-111">`BaseClass`özel bir korumalı üye sahibi `myValue`, hangi `DerivedClass1` iki yolla erişmeyi dener.</span><span class="sxs-lookup"><span data-stu-id="d8753-111">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="d8753-112">İlk erişim girişiminde `myValue` örneği üzerinden `BaseClass` hataya neden olur.</span><span class="sxs-lookup"><span data-stu-id="d8753-112">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="d8753-113">Ancak, devralınan bir üyesi olarak kullanmayı denerseniz `DerivedClass1` başarılı olur.</span><span class="sxs-lookup"><span data-stu-id="d8753-113">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="d8753-114">İkinci dosyasında, erişme denemesi `myValue` devralınan bir üyesi olarak `DerivedClass2` yalnızca Assembly1 türetilmiş türlerde tarafından erişilebilir durumda olduğu gibi bir hata oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d8753-114">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span> 

 <span data-ttu-id="d8753-115">Yapı üyeleri olamaz `private protected` yapısı devraldığından.</span><span class="sxs-lookup"><span data-stu-id="d8753-115">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d8753-116">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="d8753-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d8753-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d8753-117">See Also</span></span>  
 <span data-ttu-id="d8753-118">[C# başvurusu](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d8753-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d8753-119">[C# programlama kılavuzu](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d8753-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d8753-120">[C# anahtar sözcükleri](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d8753-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d8753-121">[Erişim değiştiricileri](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="d8753-121">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="d8753-122">[Erişilebilirlik düzeyleri](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="d8753-122">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="d8753-123">[Değiştiriciler](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="d8753-123">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="d8753-124">[Ortak](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="d8753-124">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="d8753-125">[Özel](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="d8753-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="d8753-126">[İç](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="d8753-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="d8753-127">[İç sanal anahtar ile ilgili güvenlik konuları](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="d8753-127">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>