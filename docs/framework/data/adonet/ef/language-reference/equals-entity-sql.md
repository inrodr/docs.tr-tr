---
title: "= (Eşittir) (varlık SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 12de808403ee6714d2bcfd15da4e67a8596e1ff1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="9cfce-102">= (Eşittir) (varlık SQL)</span><span class="sxs-lookup"><span data-stu-id="9cfce-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="9cfce-103">İki ifadeye eşitliğini karşılaştırır.</span><span class="sxs-lookup"><span data-stu-id="9cfce-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cfce-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="9cfce-104">Syntax</span></span>  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="9cfce-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="9cfce-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="9cfce-106">Herhangi bir geçerli ifade.</span><span class="sxs-lookup"><span data-stu-id="9cfce-106">Any valid expression.</span></span> <span data-ttu-id="9cfce-107">Her iki ifadeleri örtük olarak dönüştürülebilir veri türlerine sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="9cfce-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="9cfce-108">Sonuç türleri</span><span class="sxs-lookup"><span data-stu-id="9cfce-108">Result Types</span></span>  
 <span data-ttu-id="9cfce-109">`true`Sol ifade sağ ifade eşitse; Aksi takdirde `false`.</span><span class="sxs-lookup"><span data-stu-id="9cfce-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cfce-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9cfce-110">Remarks</span></span>  
 <span data-ttu-id="9cfce-111">== İşleci eşdeğerdir =.</span><span class="sxs-lookup"><span data-stu-id="9cfce-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cfce-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="9cfce-112">Example</span></span>  
 <span data-ttu-id="9cfce-113">Aşağıdaki varlık SQL sorgusu kullanır = iki ifadeye eşitlik karşılaştırmak için karşılaştırma işleci.</span><span class="sxs-lookup"><span data-stu-id="9cfce-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="9cfce-114">Sorgu AdventureWorks satış modelini temel alır.</span><span class="sxs-lookup"><span data-stu-id="9cfce-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9cfce-115">Derlemek ve bu sorguyu çalıştırmak için aşağıdaki adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="9cfce-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="9cfce-116">Yordamı izleyin [nasıl yapılır: Sorgu döndürür StructuralType sonucu](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="9cfce-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="9cfce-117">Aşağıdaki sorgu bağımsız değişken olarak geçirmek `ExecuteStructuralTypeQuery` yöntemi:</span><span class="sxs-lookup"><span data-stu-id="9cfce-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="9cfce-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9cfce-118">See Also</span></span>  
 [<span data-ttu-id="9cfce-119">Varlık SQL Başvurusu</span><span class="sxs-lookup"><span data-stu-id="9cfce-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)