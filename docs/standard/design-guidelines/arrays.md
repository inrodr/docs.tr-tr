---
title: Diziler
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c957d4336527de8c11b763c31c1fdf0015b675b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="arrays"></a><span data-ttu-id="6dd87-102">Diziler</span><span class="sxs-lookup"><span data-stu-id="6dd87-102">Arrays</span></span>
<span data-ttu-id="6dd87-103">**✓ YAPMAK** ortak API'ler dizilerde üzerinden koleksiyonları kullanmayı tercih.</span><span class="sxs-lookup"><span data-stu-id="6dd87-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="6dd87-104">[Koleksiyonları](../../../docs/standard/design-guidelines/guidelines-for-collections.md) bölüm koleksiyonları ve diziler arasında seçim yapma hakkında ayrıntılı bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="6dd87-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="6dd87-105">**X yok** salt okunur dizi alanları kullanın.</span><span class="sxs-lookup"><span data-stu-id="6dd87-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="6dd87-106">Alan salt okunurdur ve değiştirilemez, ancak dizideki öğeler değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="6dd87-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="6dd87-107">**✓ DÜŞÜNÜN** basit dizileri çok boyutlu diziler yerine kullanma.</span><span class="sxs-lookup"><span data-stu-id="6dd87-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="6dd87-108">Basit dizi de diziler öğeleri ile bir dizidir.</span><span class="sxs-lookup"><span data-stu-id="6dd87-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="6dd87-109">Öğeleri olun dizileri çok boyutlu diziler kıyasla daha az harcanan alan bazı (örn., seyrek matris) veri kümeleri için önde gelen farklı boyutlarda olabilir.</span><span class="sxs-lookup"><span data-stu-id="6dd87-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="6dd87-110">Ayrıca, bazı senaryolarda daha iyi çalışma zamanı performans sergiler şekilde CLR basit diziler üzerinde dizin işlemleri iyileştirir.</span><span class="sxs-lookup"><span data-stu-id="6dd87-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="6dd87-111">*Bölümleri © 2005, 2009 Microsoft Corporation. Tüm hakları saklıdır.*</span><span class="sxs-lookup"><span data-stu-id="6dd87-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6dd87-112">*Pearson eğitim, Inc. şirketinin izni tarafından yeniden yazdırılmaları [Framework tasarım yönergeleri: kuralları, deyimleri ve yeniden kullanılabilir .NET kitaplıkları, 2 sürümü için desenleri](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina ve Brad Abrams tarafından 22 Eki 2008 tarafından yayımlanan Microsoft Windows geliştirme serisi bir parçası olarak Addison-Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="6dd87-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd87-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6dd87-113">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="6dd87-114">Framework tasarım yönergeleri</span><span class="sxs-lookup"><span data-stu-id="6dd87-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="6dd87-115">Kullanım yönergeleri</span><span class="sxs-lookup"><span data-stu-id="6dd87-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)