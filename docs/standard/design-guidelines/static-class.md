---
title: "Statik sınıf tasarımı"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 28fe3756a2881e8f746616f8275b505b1a01eada
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="static-class-design"></a><span data-ttu-id="42a1b-102">Statik sınıf tasarımı</span><span class="sxs-lookup"><span data-stu-id="42a1b-102">Static Class Design</span></span>
<span data-ttu-id="42a1b-103">Statik sınıf yalnızca statik üyeleri içeren bir sınıf olarak tanımlanır (elbette devralınan örnek üyelerin yanı sıra <xref:System.Object?displayProperty=nameWithType> ve büyük olasılıkla özel Oluşturucu).</span><span class="sxs-lookup"><span data-stu-id="42a1b-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="42a1b-104">Bazı diller statik sınıflar için yerleşik destek sağlar.</span><span class="sxs-lookup"><span data-stu-id="42a1b-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="42a1b-105">C# 2.0 ve daha sonra bir sınıf statik olarak bildirilmişse, korumalı, soyut ve hiçbir örnek üyesinin geçersiz ya bildirilir.</span><span class="sxs-lookup"><span data-stu-id="42a1b-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="42a1b-106">Saf nesne odaklı tasarım ve Basitlik arasında bir seçim statik sınıflarıdır.</span><span class="sxs-lookup"><span data-stu-id="42a1b-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="42a1b-107">Bunlar genellikle diğer işlemleri kısayollar sağlamak için kullanılır (gibi <xref:System.IO.File?displayProperty=nameWithType>), uzantı yöntemleri ya da tam nesne yönelimli bir sarmalayıcı olduğu unwarranted işlevselliği sahiplerini (gibi <xref:System.Environment?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="42a1b-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="42a1b-108">**✓ YAPMAK** statik sınıflar tutumlu kullanın.</span><span class="sxs-lookup"><span data-stu-id="42a1b-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="42a1b-109">Statik sınıflar yalnızca framework nesne yönelimli çekirdek için destekleyici sınıflar olarak kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="42a1b-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="42a1b-110">**X yok** statik sınıflar çeşitli kova olarak ele alın.</span><span class="sxs-lookup"><span data-stu-id="42a1b-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="42a1b-111">**X yok** bildirme veya statik sınıflarda örnek üyeleri geçersiz kılın.</span><span class="sxs-lookup"><span data-stu-id="42a1b-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="42a1b-112">**✓ YAPMAK** statik sınıflar bildirmeniz korumalı, soyut olarak ve programlama diliniz statik sınıflar için yerleşik destek yoksa özel örnek oluşturucu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="42a1b-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="42a1b-113">*Bölümleri © 2005, 2009 Microsoft Corporation. Tüm hakları saklıdır.*</span><span class="sxs-lookup"><span data-stu-id="42a1b-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="42a1b-114">*Pearson eğitim, Inc. şirketinin izni tarafından yeniden yazdırılmaları [Framework tasarım yönergeleri: kuralları, deyimleri ve yeniden kullanılabilir .NET kitaplıkları, 2 sürümü için desenleri](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina ve Brad Abrams tarafından 22 Eki 2008 tarafından yayımlanan Microsoft Windows geliştirme serisi bir parçası olarak Addison-Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="42a1b-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a1b-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="42a1b-115">See Also</span></span>  
 [<span data-ttu-id="42a1b-116">Türü tasarım yönergeleri</span><span class="sxs-lookup"><span data-stu-id="42a1b-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="42a1b-117">Framework tasarım yönergeleri</span><span class="sxs-lookup"><span data-stu-id="42a1b-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)