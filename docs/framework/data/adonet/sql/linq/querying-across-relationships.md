---
title: "İlişkiler arasında sorgulama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 297878d0-685b-4c01-b2e0-9d731b7322bc
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a347818818fe7c6e15535fd0c2c24548c52e57d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="querying-across-relationships"></a><span data-ttu-id="39af5-102">İlişkiler arasında sorgulama</span><span class="sxs-lookup"><span data-stu-id="39af5-102">Querying Across Relationships</span></span>
<span data-ttu-id="39af5-103">Diğer nesne veya koleksiyonlar, sınıf tanımları diğer nesnelerin başvurular doğrudan veritabanında yabancı anahtar ilişkileri karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="39af5-103">References to other objects or collections of other objects in your class definitions directly correspond to foreign-key relationships in the database.</span></span> <span data-ttu-id="39af5-104">İlişki özelliklerine erişmek ve başka bir nesneden gezinmek için noktalı gösterim kullanarak sorguladığınızda, bu ilişkileri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="39af5-104">You can use these relationships when you query by using dot notation to access the relationship properties and navigate from one object to another.</span></span> <span data-ttu-id="39af5-105">Daha karmaşık birleştirmeler ya da eşdeğer SQL bağlantılı sorgularda erişim işlemlerini çevir.</span><span class="sxs-lookup"><span data-stu-id="39af5-105">These access operations translate to more complex joins or correlated subqueries in the equivalent SQL.</span></span>  
  
 <span data-ttu-id="39af5-106">Örneğin, aşağıdaki sorgu sonuçları yalnızca Londra'da bulunan müşteriler için siparişleri sınırlamak için bir yol olarak müşterilere siparişleri gider.</span><span class="sxs-lookup"><span data-stu-id="39af5-106">For example, the following query navigates from orders to customers as a way to restrict the results to only those orders for customers located in London.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#3)]
 [!code-vb[DLinqQueryConcepts#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#3)]  
  
 <span data-ttu-id="39af5-107">İlişki özellikleri mevcut değilse bunları yazmanız gerekir el ile olarak *birleştirmeler*, aşağıdaki kod olduğu gibi SQL sorguda yaptığınız gibi:</span><span class="sxs-lookup"><span data-stu-id="39af5-107">If relationship properties did not exist you would have to write them manually as *joins*, just as you would do in a SQL query, as in the following code:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#4)]
 [!code-vb[DLinqQueryConcepts#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#4)]  
  
 <span data-ttu-id="39af5-108">Kullanabileceğiniz *ilişki* bir kez bu belirli ilişki tanımlamak için özellik.</span><span class="sxs-lookup"><span data-stu-id="39af5-108">You can use the *relationship* property to define this particular relationship one time.</span></span> <span data-ttu-id="39af5-109">Ardından, daha kullanışlı nokta sözdizimini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="39af5-109">You can then use the more convenient dot syntax.</span></span> <span data-ttu-id="39af5-110">Ancak etki alanına özgü nesne modelleri genellikle hiyerarşileri veya grafikleri tanımlandığından ilişki özellikleri daha da önemlisi yok.</span><span class="sxs-lookup"><span data-stu-id="39af5-110">But relationship properties exist more importantly because domain-specific object models are typically defined as hierarchies or graphs.</span></span> <span data-ttu-id="39af5-111">Karşı program nesneleri diğer nesnelerin referansları sahiptir.</span><span class="sxs-lookup"><span data-stu-id="39af5-111">The objects that you program against have references to other objects.</span></span> <span data-ttu-id="39af5-112">Nesne nesnesi ilişkileri veritabanları yabancı anahtar stilde ilişkilerde karşılık gelen bir mutluluk rastlantı olur.</span><span class="sxs-lookup"><span data-stu-id="39af5-112">It is only a happy coincidence that object-to-object relationships correspond to foreign-key-styled relationships in databases.</span></span> <span data-ttu-id="39af5-113">Özellik erişim sonra birleştirmeler yazmak için kolay bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="39af5-113">Property access then provides a convenient way to write joins.</span></span>  
  
 <span data-ttu-id="39af5-114">Bu açısından ilişki sorgu sorgu parçası olarak sonuçları tarafındaki daha önemli özelliklerdir.</span><span class="sxs-lookup"><span data-stu-id="39af5-114">With regard to this, relationship properties are more important on the results side of a query than as part of the query itself.</span></span> <span data-ttu-id="39af5-115">Sorgu belirli bir müşteri hakkında veri aldığı sonra müşterilerin siparişleri sahip sınıf tanımını gösterir.</span><span class="sxs-lookup"><span data-stu-id="39af5-115">After the query has retrieved data about a particular customer, the class definition indicates that customers have orders.</span></span> <span data-ttu-id="39af5-116">Diğer bir deyişle, beklediğiniz `Orders` bu müşteriden emirleriyle doldurulmuş bir koleksiyonu olması için belirli bir müşteri özelliği.</span><span class="sxs-lookup"><span data-stu-id="39af5-116">In other words, you expect the `Orders` property of a particular customer to be a collection that is populated with all the orders from that customer.</span></span> <span data-ttu-id="39af5-117">Bu şekilde sınıfları tanımlama tarafından bildirilen sözleşme aslında olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="39af5-117">That is in fact the contract you declared by defining the classes in this manner.</span></span> <span data-ttu-id="39af5-118">Sorgu siparişleri istememiş olsa bile siparişleri var. görmeyi bekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="39af5-118">You expect to see the orders there even if the query did not request orders.</span></span> <span data-ttu-id="39af5-119">Veritabanı ile ilgili nesneleri hemen kullanılabilir bellek içi uzantısı olan bir görünümü korumak için nesne modeli bekler.</span><span class="sxs-lookup"><span data-stu-id="39af5-119">You expect your object model to maintain an illusion that it is an in-memory extension of the database with related objects immediately available.</span></span>  
  
 <span data-ttu-id="39af5-120">İlişkileri sahip olduğunuza göre sorguları, sınıflarda tanımlanan ilişki özelliklerini başvurarak yazabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="39af5-120">Now that you have relationships, you can write queries by referring to the relationship properties defined in your classes.</span></span> <span data-ttu-id="39af5-121">Bu ilişki başvuruları veritabanında yabancı anahtar ilişkileri karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="39af5-121">These relationship references correspond to foreign-key relationships in the database.</span></span> <span data-ttu-id="39af5-122">Bu ilişkileri kullanan işlemler eşdeğer SQL daha karmaşık birleşimlerde çevir.</span><span class="sxs-lookup"><span data-stu-id="39af5-122">Operations that use these relationships translate to more complex joins in the equivalent SQL.</span></span> <span data-ttu-id="39af5-123">Tanımlanmış bir ilişkisi sürece (kullanarak <xref:System.Data.Linq.Mapping.AssociationAttribute> özniteliği), açık bir birleştirme kod gerekmez [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39af5-123">As long as you have defined a relationship (using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute), you do not have to code an explicit join in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 <span data-ttu-id="39af5-124">Bu görünümü sağlanmasına yardımcı olmak için [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] adında bir teknik uygulayan *yüklenirken ertelenmiş*.</span><span class="sxs-lookup"><span data-stu-id="39af5-124">To help maintain this illusion, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implements a technique called *deferred loading*.</span></span> <span data-ttu-id="39af5-125">Daha fazla bilgi için bkz: [hemen yüklenirken karşı ertelenmiş](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="39af5-125">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
 <span data-ttu-id="39af5-126">Proje listesi için aşağıdaki SQL sorgusunu göz önünde bulundurun `CustomerID` - `OrderID` çiftleri:</span><span class="sxs-lookup"><span data-stu-id="39af5-126">Consider the following SQL query to project a list of `CustomerID`-`OrderID` pairs:</span></span>  
  
```  
SELECT t0.CustomerID, t1.OrderID  
FROM   Customers AS t0 INNER JOIN  
          Orders AS t1 ON t0.CustomerID = t1.CustomerID  
WHERE  (t0.City = @p0)  
```  
  
 <span data-ttu-id="39af5-127">Kullanarak aynı sonuçları elde etmek için [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], kullandığınız `Orders` özelliği başvuru zaten mevcut `Customer` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="39af5-127">To obtain the same results by using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you use the `Orders` property reference already existing in the `Customer` class.</span></span> <span data-ttu-id="39af5-128">`Orders` Başvuru sağlar sorgu ve proje yürütmek için gerekli bilgileri `CustomerID` - `OrderID` aşağıdaki kodu olduğu gibi çiftleri:</span><span class="sxs-lookup"><span data-stu-id="39af5-128">The `Orders` reference provides the necessary information to execute the query and project the `CustomerID`-`OrderID` pairs, as in the following code:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#5)]
 [!code-vb[DLinqQueryConcepts#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#5)]  
  
 <span data-ttu-id="39af5-129">Bu durumun tersi de yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="39af5-129">You can also do the reverse.</span></span> <span data-ttu-id="39af5-130">Diğer bir deyişle, sorgu `Orders` ve kendi `Customer` ilişki başvuru ilişkili ilgili bilgilere erişmek üzere `Customer` nesnesi.</span><span class="sxs-lookup"><span data-stu-id="39af5-130">That is, you can query `Orders` and use its `Customer` relationship reference to access information about the associated `Customer` object.</span></span> <span data-ttu-id="39af5-131">Aşağıdaki kodu aynı projeleri `CustomerID` - `OrderID` önceki gibi ancak bu kez sorgulayarak çiftleri `Orders` yerine `Customers`.</span><span class="sxs-lookup"><span data-stu-id="39af5-131">The following code projects the same `CustomerID`-`OrderID` pairs as before, but this time by querying `Orders` instead of `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#6)]
 [!code-vb[DLinqQueryConcepts#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="39af5-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="39af5-132">See Also</span></span>  
 [<span data-ttu-id="39af5-133">Sorgu kavramları</span><span class="sxs-lookup"><span data-stu-id="39af5-133">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)