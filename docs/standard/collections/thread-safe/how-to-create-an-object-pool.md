---
title: "Nasıl yapılır: ConcurrentBag Kullanarak Nesne Havuzu Oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f7cb18157122d8bc053f34b21f623f3ab1e14305
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a><span data-ttu-id="42fcb-102">Nasıl yapılır: ConcurrentBag Kullanarak Nesne Havuzu Oluşturma</span><span class="sxs-lookup"><span data-stu-id="42fcb-102">How to: Create an Object Pool by Using a ConcurrentBag</span></span>
<span data-ttu-id="42fcb-103">Bu örnek bir eş zamanlı paketi nesne havuzu uygulamak için nasıl kullanılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="42fcb-103">This example shows how to use a concurrent bag to implement an object pool.</span></span> <span data-ttu-id="42fcb-104">Nesne havuzları bir sınıfın birden çok örneği gerektirir ve sınıfı oluşturmak veya silmek pahalıdır durumlarda uygulama performansını iyileştirebilir.</span><span class="sxs-lookup"><span data-stu-id="42fcb-104">Object pools can improve application performance in situations where you require multiple instances of a class and the class is expensive to create or destroy.</span></span> <span data-ttu-id="42fcb-105">Bir istemci programı yeni bir nesne istediğinde, nesne havuzu ilk zaten oluşturulduğundan ve havuza geri döner bir sağlamaya çalışır.</span><span class="sxs-lookup"><span data-stu-id="42fcb-105">When a client program requests a new object, the object pool first attempts to provide one that has already been created and returned to the pool.</span></span> <span data-ttu-id="42fcb-106">Ancak bundan sonra yeni bir nesne yoksa, oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="42fcb-106">If none is available, only then is a new object created.</span></span>  
  
 <span data-ttu-id="42fcb-107"><xref:System.Collections.Concurrent.ConcurrentBag%601>özellikle iş parçacığı hem öğeler ekleme ve kaldırma zaman hızlı ekleme ve kaldırma, desteklediğinden, nesneleri depolamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="42fcb-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> is used to store the objects because it supports fast insertion and removal, especially when the same thread is both adding and removing items.</span></span> <span data-ttu-id="42fcb-108">Bu örnek daha fazla geçici oluşturulacak engagement'ta bir <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, yaptığınız gibi paketi veri yapısı uygulayan <xref:System.Collections.Concurrent.ConcurrentQueue%601> ve <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="42fcb-108">This example could be further augmented to be built around a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, which the bag data structure implements, as do <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42fcb-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="42fcb-109">Example</span></span>  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="42fcb-110">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="42fcb-110">See Also</span></span>  
 [<span data-ttu-id="42fcb-111">İş parçacığı koleksiyonları</span><span class="sxs-lookup"><span data-stu-id="42fcb-111">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)