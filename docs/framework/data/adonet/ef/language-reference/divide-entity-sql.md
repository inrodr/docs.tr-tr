---
title: "- (Bölme) (Varlık SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0f215e12f9f86ee08679bdb2e2638c0c8df35ea4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="56545-102">/ (Bölme (varlık SQL))</span><span class="sxs-lookup"><span data-stu-id="56545-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="56545-103">Bir sayıyı bir başkası tarafından böler.</span><span class="sxs-lookup"><span data-stu-id="56545-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56545-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="56545-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="56545-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="56545-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="56545-106">Bölmek için sayısal ifade.</span><span class="sxs-lookup"><span data-stu-id="56545-106">The numeric expression to divide.</span></span> <span data-ttu-id="56545-107">`dividend`sayısal veri türleri herhangi birinin geçerli bir ifade değil.</span><span class="sxs-lookup"><span data-stu-id="56545-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="56545-108">Tarafından bölünen bölmek için sayısal ifade.</span><span class="sxs-lookup"><span data-stu-id="56545-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="56545-109">`divisor`sayısal veri türleri herhangi birinin geçerli bir ifade değil.</span><span class="sxs-lookup"><span data-stu-id="56545-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="56545-110">Sonuç türleri</span><span class="sxs-lookup"><span data-stu-id="56545-110">Result Types</span></span>  
 <span data-ttu-id="56545-111">İki bağımsız değişken örtük tür yükseltme sonuçları veri türü.</span><span class="sxs-lookup"><span data-stu-id="56545-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="56545-112">Örtük tür yükseltme hakkında daha fazla bilgi için bkz: [tür sistemi](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="56545-112">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56545-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="56545-113">Example</span></span>  
 <span data-ttu-id="56545-114">Aşağıdaki varlık SQL sorgusu kullanır / aritmetik bir numarası bir başkası tarafından bölmek için işleci.</span><span class="sxs-lookup"><span data-stu-id="56545-114">The following Entity SQL query uses the / arithmetic operator to divide one numer by another.</span></span> <span data-ttu-id="56545-115">Sorgu AdventureWorks satış modelini temel alır.</span><span class="sxs-lookup"><span data-stu-id="56545-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="56545-116">Derlemek ve bu sorguyu çalıştırmak için aşağıdaki adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="56545-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="56545-117">Yordamı izleyin [nasıl yapılır: Sorgu döndürür StructuralType sonucu](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="56545-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="56545-118">Aşağıdaki sorgu bağımsız değişken olarak geçirmek `ExecuteStructuralTypeQuery` yöntemi:</span><span class="sxs-lookup"><span data-stu-id="56545-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="56545-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="56545-119">See Also</span></span>  
 [<span data-ttu-id="56545-120">Varlık SQL Başvurusu</span><span class="sxs-lookup"><span data-stu-id="56545-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)