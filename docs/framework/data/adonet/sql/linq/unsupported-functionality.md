---
title: "Desteklenmeyen işlevi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6dd8ccebd278fdc36c536c49f7f1d4262b2de8c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="unsupported-functionality"></a><span data-ttu-id="d1dd8-102">Desteklenmeyen işlevi</span><span class="sxs-lookup"><span data-stu-id="d1dd8-102">Unsupported Functionality</span></span>
<span data-ttu-id="d1dd8-103">LINQ-SQL, aşağıdaki SQL işlevselliği varolan ortak dil çalışma zamanı (CLR) çeviri görüntülenemeyen ve .NET Framework oluşturur:</span><span class="sxs-lookup"><span data-stu-id="d1dd8-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     <span data-ttu-id="d1dd8-104">Ancak `LIKE` desteklenmiyor benzer işlevselliği bulunmaktadır doğrudan çeviri <xref:System.Data.Linq.SqlClient.SqlMethods> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="d1dd8-105">Daha fazla bilgi için bkz. <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
-   `DATEDIFF`  
  
     <span data-ttu-id="d1dd8-106">LINQ-SQL desteği sınırlı `DATEDIFF`.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="d1dd8-107">Benzer işlevsellik mevcut <xref:System.Data.Linq.SqlClient.SqlMethods> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
-   `ROUND`  
  
     <span data-ttu-id="d1dd8-108">LINQ-SQL desteği sınırlı `ROUND`.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="d1dd8-109">Daha fazla bilgi için bkz: [System.Math yöntemleri](system-math-methods.md).</span><span class="sxs-lookup"><span data-stu-id="d1dd8-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1dd8-110">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-110">See Also</span></span>  
 [<span data-ttu-id="d1dd8-111">Veri türleri ve işlevleri</span><span class="sxs-lookup"><span data-stu-id="d1dd8-111">Data Types and Functions</span></span>](data-types-and-functions.md)