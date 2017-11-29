---
title: "SQL CLR türüyle eşleşmiyor"
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
ms.assetid: 0a90c33f-7ed7-4501-ad5f-6224c5da8e9b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: cc1458996e70e8af05c4e2bc9e6c61a5d8a9f87d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="sql-clr-type-mismatches"></a><span data-ttu-id="29bd1-102">SQL CLR türüyle eşleşmiyor</span><span class="sxs-lookup"><span data-stu-id="29bd1-102">SQL-CLR Type Mismatches</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="29bd1-103">nesne modeli ve SQL Server arasında çeviri çoğunu otomatikleştirir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-103"> automates much of the translation between the object model and SQL Server.</span></span> <span data-ttu-id="29bd1-104">Bununla birlikte, bazı durumlarda tam çeviri engeller.</span><span class="sxs-lookup"><span data-stu-id="29bd1-104">Nevertheless, some situations prevent exact translation.</span></span> <span data-ttu-id="29bd1-105">Bu anahtar uyuşmazlıkları ortak dil çalışma zamanı (CLR) türleri ve SQL Server veritabanı türleri arasında aşağıdaki bölümlerde özetlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-105">These key mismatches between the common language runtime (CLR) types and the SQL Server database types are summarized in the following sections.</span></span> <span data-ttu-id="29bd1-106">Belirli tür eşlemeleri ve adresindeki işlevi çevirisi hakkında daha fazla ayrıntı bulabilirsiniz [SQL CLR türü eşleme](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md) ve [veri türler ve işlevler](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md).</span><span class="sxs-lookup"><span data-stu-id="29bd1-106">You can find more details about specific type mappings and function translation at [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md) and [Data Types and Functions](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md).</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="29bd1-107">Veri Türleri</span><span class="sxs-lookup"><span data-stu-id="29bd1-107">Data Types</span></span>  
 <span data-ttu-id="29bd1-108">Çeviri CLR SQL sunucusu arasındaki bir sorgu veritabanına gönderildiğinde ve sonuçları, nesne modelinde gönderildiğinde oluşur.</span><span class="sxs-lookup"><span data-stu-id="29bd1-108">Translation between the CLR and SQL Server occurs when a query is being sent to the database, and when the results are sent back to your object model.</span></span> <span data-ttu-id="29bd1-109">Örneğin, aşağıdaki Transact-SQL sorgusu iki değer dönüşümler gerektirir:</span><span class="sxs-lookup"><span data-stu-id="29bd1-109">For example, the following Transact-SQL query requires two value conversions:</span></span>  
  
```  
Select DateOfBirth From Customer Where CustomerId = @id     
```  
  
 <span data-ttu-id="29bd1-110">SQL Server'da sorgu yürütülebilmesi Transact-SQL parametresi için değer belirtilmelidir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-110">Before the query can be executed on SQL Server, the value for the Transact-SQL parameter must be specified.</span></span> <span data-ttu-id="29bd1-111">Bu örnekte, `id` parametre değeri gereken ilk dönüştürülür bir CLR <xref:System.Int32?displayProperty=nameWithType> türü SQL Server `INT` veritabanı değeri nedir anlamanız yazın.</span><span class="sxs-lookup"><span data-stu-id="29bd1-111">In this example, the `id` parameter value must first be translated from a CLR <xref:System.Int32?displayProperty=nameWithType> type to a SQL Server `INT` type so that the database can understand what the value is.</span></span> <span data-ttu-id="29bd1-112">SQL Server sonuçları almak için `DateOfBirth` SQL Server'dan sütun çevrilen `DATETIME` bir CLR türüne <xref:System.DateTime?displayProperty=nameWithType> nesne modelinde kullanılmak tür.</span><span class="sxs-lookup"><span data-stu-id="29bd1-112">Then to retrieve the results, the SQL Server `DateOfBirth` column must be translated from a SQL Server `DATETIME` type to a CLR <xref:System.DateTime?displayProperty=nameWithType> type for use in the object model.</span></span> <span data-ttu-id="29bd1-113">Bu örnekte, CLR nesne modeli ve SQL Server veritabanı türleri doğal eşlemeleri vardır.</span><span class="sxs-lookup"><span data-stu-id="29bd1-113">In this example, the types in the CLR object model and SQL Server database have natural mappings.</span></span> <span data-ttu-id="29bd1-114">Ancak, bu her zaman geçerli değildir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-114">But, this is not always the case.</span></span>  
  
### <a name="missing-counterparts"></a><span data-ttu-id="29bd1-115">Ortaklarınıza eksik</span><span class="sxs-lookup"><span data-stu-id="29bd1-115">Missing Counterparts</span></span>  
 <span data-ttu-id="29bd1-116">Aşağıdaki türlerden makul ortaklarınıza gerekmez.</span><span class="sxs-lookup"><span data-stu-id="29bd1-116">The following types do not have reasonable counterparts.</span></span>  
  
-   <span data-ttu-id="29bd1-117">CLR eşleşmiyor <xref:System> ad alanı:</span><span class="sxs-lookup"><span data-stu-id="29bd1-117">Mismatches in the CLR <xref:System> namespace:</span></span>  
  
    -   <span data-ttu-id="29bd1-118">**İmzasız tamsayılar**.</span><span class="sxs-lookup"><span data-stu-id="29bd1-118">**Unsigned integers**.</span></span> <span data-ttu-id="29bd1-119">Bu tür taşması önlemek için imzalanmış dekiler daha büyük boyutta için genellikle eşlenir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-119">These types are typically mapped to their signed counterparts of larger size to avoid overflow.</span></span> <span data-ttu-id="29bd1-120">Değişmez değerler, imzalı bir sayısal değere göre aynı veya daha küçük boyutu dönüştürülebilir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-120">Literals can be converted to a signed numeric of the same or smaller size, based on value.</span></span>  
  
    -   <span data-ttu-id="29bd1-121">**Boolean**.</span><span class="sxs-lookup"><span data-stu-id="29bd1-121">**Boolean**.</span></span> <span data-ttu-id="29bd1-122">Bu tür bir bit veya daha büyük sayısal veya dize için eşlenebilir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-122">These types can be mapped to a bit or larger numeric or string.</span></span> <span data-ttu-id="29bd1-123">Bir hazır değer aynı değer veren bir ifade eşlenebilir (örneğin, `1=1` için SQL'de `True` CLS içinde).</span><span class="sxs-lookup"><span data-stu-id="29bd1-123">A literal can be mapped to an expression that evaluates to the same value (for example, `1=1` in SQL for `True` in CLS).</span></span>  
  
    -   <span data-ttu-id="29bd1-124">**TimeSpan**.</span><span class="sxs-lookup"><span data-stu-id="29bd1-124">**TimeSpan**.</span></span> <span data-ttu-id="29bd1-125">Bu tür iki arasındaki farkı temsil eder `DateTime` değerleri ve karşılık gelmiyor `timestamp` SQL Server'ın.</span><span class="sxs-lookup"><span data-stu-id="29bd1-125">This type represents the difference between two `DateTime` values and does not correspond to the `timestamp` of SQL Server.</span></span> <span data-ttu-id="29bd1-126">CLR <xref:System.TimeSpan?displayProperty=nameWithType> SQL Server'a da eşleyebilir `TIME` bazı durumlarda türü.</span><span class="sxs-lookup"><span data-stu-id="29bd1-126">The CLR <xref:System.TimeSpan?displayProperty=nameWithType> may also map to the SQL Server `TIME` type in some cases.</span></span> <span data-ttu-id="29bd1-127">SQL Server `TIME` türü pozitif değer 24 saatten az temsil etmek için yalnızca tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="29bd1-127">The SQL Server `TIME` type was only intended to represent positive values less than 24 hours.</span></span> <span data-ttu-id="29bd1-128">CLR <xref:System.TimeSpan> kadar büyük aralığı yok.</span><span class="sxs-lookup"><span data-stu-id="29bd1-128">The CLR <xref:System.TimeSpan> has a much larger range.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="29bd1-129">SQL Server'a özgü [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] türlerini <xref:System.Data.SqlTypes> bu karşılaştırma dahil edilmez.</span><span class="sxs-lookup"><span data-stu-id="29bd1-129">SQL Server-specific [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] types in <xref:System.Data.SqlTypes> are not included in this comparison.</span></span>  
  
-   <span data-ttu-id="29bd1-130">SQL Server uyuşmazlıkları:</span><span class="sxs-lookup"><span data-stu-id="29bd1-130">Mismatches in SQL Server:</span></span>  
  
    -   <span data-ttu-id="29bd1-131">**Karakter türleri uzunluğu sabit**.</span><span class="sxs-lookup"><span data-stu-id="29bd1-131">**Fixed length character types**.</span></span> <span data-ttu-id="29bd1-132">Transact-SQL arasında Unicode ve Unicode olmayan kategorilere ayırır ve her kategoride birbirinden farklı üç sahiptir: uzunluğu sabit `nchar` / `char`, değişken uzunlukta `nvarchar` / `varchar`, ve büyük ölçekli `ntext` / `text`.</span><span class="sxs-lookup"><span data-stu-id="29bd1-132">Transact-SQL distinguishes between Unicode and non-Unicode categories and has three distinct types in each category: fixed length `nchar`/`char`, variable length `nvarchar`/`varchar`, and larger-sized `ntext`/`text`.</span></span> <span data-ttu-id="29bd1-133">Sabit uzunlukta karakter türleri için CLR eşleştirilebilir <xref:System.Char?displayProperty=nameWithType> alma türü karakterleri, ancak bunlar gerçekten dönüşümler ve davranış aynı türden karşılık değil.</span><span class="sxs-lookup"><span data-stu-id="29bd1-133">The fixed length character types could be mapped to the CLR <xref:System.Char?displayProperty=nameWithType> type for retrieving characters, but they do not really correspond to the same type in conversions and behavior.</span></span>  
  
    -   <span data-ttu-id="29bd1-134">**Bit**.</span><span class="sxs-lookup"><span data-stu-id="29bd1-134">**Bit**.</span></span> <span data-ttu-id="29bd1-135">Ancak `bit` etki alanına sahip değerleri olarak aynı sayıda `Nullable<Boolean>`, iki farklı türleridir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-135">Although the `bit` domain has the same number of values as `Nullable<Boolean>`, the two are different types.</span></span> <span data-ttu-id="29bd1-136">`Bit`değerleri alır `1` ve `0` yerine `true` / `false`ve bir Boole ifadeleri eşdeğer olarak kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="29bd1-136">`Bit` takes values `1` and `0` instead of `true`/`false`, and cannot be used as an equivalent to Boolean expressions.</span></span>  
  
    -   <span data-ttu-id="29bd1-137">**Zaman damgası**.</span><span class="sxs-lookup"><span data-stu-id="29bd1-137">**Timestamp**.</span></span> <span data-ttu-id="29bd1-138">CLR aksine <xref:System.TimeSpan?displayProperty=nameWithType> türü, SQL Server `TIMESTAMP` türünü temsil eder, her güncelleştirme için benzersiz olan ve arasındaki farkı dayanmıyor veritabanı tarafından oluşturulan bir 8 bayt <xref:System.DateTime> değerleri.</span><span class="sxs-lookup"><span data-stu-id="29bd1-138">Unlike the CLR <xref:System.TimeSpan?displayProperty=nameWithType> type, the SQL Server `TIMESTAMP` type represents an 8-byte number generated by the database that is unique for each update and is not based on the difference between <xref:System.DateTime> values.</span></span>  
  
    -   <span data-ttu-id="29bd1-139">**Para** ve **küçük para**.</span><span class="sxs-lookup"><span data-stu-id="29bd1-139">**Money** and **SmallMoney**.</span></span> <span data-ttu-id="29bd1-140">Bu tür eşlenebilir <xref:System.Decimal> ancak temel olarak farklı türleri ve bu nedenle sunucu tabanlı işlevleri ve dönüşümleri tarafından kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-140">These types can be mapped to <xref:System.Decimal> but are basically different types and are treated as such by server-based functions and conversions.</span></span>  
  
### <a name="multiple-mappings"></a><span data-ttu-id="29bd1-141">Birden çok eşleme</span><span class="sxs-lookup"><span data-stu-id="29bd1-141">Multiple Mappings</span></span>  
 <span data-ttu-id="29bd1-142">Bir veya daha fazla CLR veri türlerini eşleyebilirsiniz çok SQL Server veri türü vardır.</span><span class="sxs-lookup"><span data-stu-id="29bd1-142">There are many SQL Server data types that you can map to one or more CLR data types.</span></span> <span data-ttu-id="29bd1-143">Bir veya daha fazla SQL Server türlerine eşlenir birçok CLR türü vardır.</span><span class="sxs-lookup"><span data-stu-id="29bd1-143">There are also many CLR types that you can map to one or more SQL Server types.</span></span> <span data-ttu-id="29bd1-144">Bir eşleme LINQ-SQL tarafından desteklenebilir rağmen CLR ve SQL Server arasında eşlenen iki tür duyarlık, aralık ve semantiği mükemmel bir eşleşme olduğunu gelmez.</span><span class="sxs-lookup"><span data-stu-id="29bd1-144">Although a mapping may be supported by LINQ to SQL, it does not mean that the two types mapped between the CLR and SQL Server are a perfect match in precision, range, and semantics.</span></span> <span data-ttu-id="29bd1-145">Bazı eşlemeler, bu boyutlar bir bölümünü veya tamamını farklılıkları içerebilir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-145">Some mappings may include differences in any or all of these dimensions.</span></span> <span data-ttu-id="29bd1-146">Çeşitli eşleme olasılıklara bu olası farklılıklar ayrıntılarını bulabilirsiniz [SQL CLR türü eşlemesi](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="29bd1-146">You can find details about these potential differences for the various mapping possibilities at [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>  
  
### <a name="user-defined-types"></a><span data-ttu-id="29bd1-147">Kullanıcı tanımlı türler</span><span class="sxs-lookup"><span data-stu-id="29bd1-147">User-defined Types</span></span>  
 <span data-ttu-id="29bd1-148">Kullanıcı tanımlı CLR Türleri türü sistem boşluğunu yardımcı olmak için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="29bd1-148">User-defined CLR types are designed to help bridge the type system gap.</span></span> <span data-ttu-id="29bd1-149">Yine de ilginç sorunları türü sürüm oluşturma hakkında yüzey.</span><span class="sxs-lookup"><span data-stu-id="29bd1-149">Nevertheless they surface interesting issues about type versioning.</span></span> <span data-ttu-id="29bd1-150">İstemci sürümünde değişikliğe veritabanı sunucusunda depolanan türü değişikliği matched.</span><span class="sxs-lookup"><span data-stu-id="29bd1-150">A change in the version on the client might not be matched by a change in the type stored on the database server.</span></span> <span data-ttu-id="29bd1-151">Bu tür bir değişiklik burada türü anlamları eşleşmeyebilir ve sürüm boşluk görünür hale gelmiştir büyük olasılıkla başka bir tür uyuşmazlığı neden olur.</span><span class="sxs-lookup"><span data-stu-id="29bd1-151">Any such change causes another type mismatch where the type semantics might not match and the version gap is likely to become visible.</span></span> <span data-ttu-id="29bd1-152">Devralma hiyerarşileri birbirini izleyen sürümlerde bulunanad gibi başka zorluklar oluşur.</span><span class="sxs-lookup"><span data-stu-id="29bd1-152">Further complications occur as inheritance hierarchies are refactored in successive versions.</span></span>  
  
## <a name="expression-semantics"></a><span data-ttu-id="29bd1-153">İfade semantiği</span><span class="sxs-lookup"><span data-stu-id="29bd1-153">Expression Semantics</span></span>  
 <span data-ttu-id="29bd1-154">CLR ve veritabanı türleri arasında ikili uyuşmazlığı yanı sıra ifadeleri karmaşıklık uyuşmazlığı ekleyin.</span><span class="sxs-lookup"><span data-stu-id="29bd1-154">In addition to the pairwise mismatch between CLR and database types, expressions add complexity to the mismatch.</span></span> <span data-ttu-id="29bd1-155">İşleç semantiği, işlevi semantiği, örtük tür dönüştürmeleri ve öncelik kuralları uyuşmazlıkları dikkate alınmalıdır.</span><span class="sxs-lookup"><span data-stu-id="29bd1-155">Mismatches in operator semantics, function semantics, implicit type conversion, and precedence rules must be considered.</span></span>  
  
 <span data-ttu-id="29bd1-156">Aşağıdaki alt bölümleri görünüşe göre benzer ifadeleri arasındaki uyumsuzluk gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-156">The following subsections illustrate the mismatch between apparently similar expressions.</span></span> <span data-ttu-id="29bd1-157">Verilen bir CLR ifade anlam olarak eşdeğer SQL deyimlerini oluşturmak mümkün olabilir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-157">It might be possible to generate SQL expressions that are semantically equivalent to a given CLR expression.</span></span> <span data-ttu-id="29bd1-158">Ancak, bunu görünüşe göre benzer ifadeleri anlamsal farklarını CLR kullanıcıya korumalı olup olmadığı ve dolayısıyla anlamsal eşdeğer için gerekli olan değişiklikleri amacını taşımaktadır değil NET değil.</span><span class="sxs-lookup"><span data-stu-id="29bd1-158">However, it is not clear whether the semantic differences between apparently similar expressions are evident to a CLR user, and therefore whether the changes that are required for semantic equivalence are intended or not.</span></span> <span data-ttu-id="29bd1-159">Bir ifade için değer kümesini değerlendirildiğinde bu özellikle kritik bir sorundur.</span><span class="sxs-lookup"><span data-stu-id="29bd1-159">This is an especially critical issue when an expression is evaluated for a set of values.</span></span> <span data-ttu-id="29bd1-160">Fark görünürlüğünü verileri - üzerinde bağlı ve kodlama ve hata ayıklama sırasında belirlemek sabit.</span><span class="sxs-lookup"><span data-stu-id="29bd1-160">The visibility of the difference might depend on data- and be hard to identify during coding and debugging.</span></span>  
  
### <a name="null-semantics"></a><span data-ttu-id="29bd1-161">Null semantiği</span><span class="sxs-lookup"><span data-stu-id="29bd1-161">Null Semantics</span></span>  
 <span data-ttu-id="29bd1-162">SQL deyimleri Boole ifadeleri için üç değerli mantığı sağlar.</span><span class="sxs-lookup"><span data-stu-id="29bd1-162">SQL expressions provide three-valued logic for Boolean expressions.</span></span> <span data-ttu-id="29bd1-163">Sonucu true, false ve null olabilir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-163">The result can be true, false, or null.</span></span> <span data-ttu-id="29bd1-164">Bunun aksine, CLR iki değerli Boole sonucu null değerler içeren karşılaştırmaları için belirtir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-164">By contrast, CLR specifies two-valued Boolean result for comparisons involving null values.</span></span> <span data-ttu-id="29bd1-165">Aşağıdaki kod göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="29bd1-165">Consider the following code:</span></span>  
  
 [!code-csharp[DLinqMismatch#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#2)]
 [!code-vb[DLinqMismatch#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#2)]  
  
```  
-- Assume col1 and col2 are integer columns with null values.   
-- Assume that ANSI null behavior has not been explicitly  
--    turned off.  
Select …  
From …  
Where col1 = col2  
-- Evaluates to null, not true and the corresponding row is not  
--     selected.  
-- To obtain matching behavior (i -> col1, j -> col2) change  
--     the query to the following:  
Select …  
From …  
Where  
    col1 = col2   
or (col1 is null and col2 is null)  
-- (Visual Basic 'Nothing'.)  
```  
  
 <span data-ttu-id="29bd1-166">İki değerli sonuçlarıyla ilgili varsayımına ile benzer bir sorun oluşur.</span><span class="sxs-lookup"><span data-stu-id="29bd1-166">A similar problem occurs with the assumption about two-valued results.</span></span>  
  
 [!code-csharp[DLinqMismatch#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#3)]
 [!code-vb[DLinqMismatch#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#3)]  
  
```  
-- Assume col1 and col2 are nullable columns.  
-- Assume that ANSI null behavior has not been explicitly  
--     turned off.  
Select …  
From …  
Where  
    col1 = col2        
or col1 != col2  
-- Visual Basic: col1 <> col2.  
  
-- Excludes the case where the boolean expression evaluates  
--     to null. Therefore the where clause does not always  
--     evaluate to true.  
```  
  
 <span data-ttu-id="29bd1-167">Önceki örnekte SQL oluşturma, eşdeğer davranışını elde edebilirsiniz, ancak çeviri doğru şekilde amacınız gösterebilir değil.</span><span class="sxs-lookup"><span data-stu-id="29bd1-167">In the previous case, you can get equivalent behavior in generating SQL, but the translation might not accurately reflect your intention.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="29bd1-168">C# getirmez `null` veya [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `nothing` karşılaştırma semantiği SQL'de.</span><span class="sxs-lookup"><span data-stu-id="29bd1-168"> does not impose C# `null` or [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `nothing` comparison semantics on SQL.</span></span> <span data-ttu-id="29bd1-169">Karşılaştırma işleçleri sözdizimsel olarak SQL eşdeğerlerine çevrilir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-169">Comparison operators are syntactically translated to their SQL equivalents.</span></span> <span data-ttu-id="29bd1-170">Sunucu veya bağlantı ayarları tarafından tanımlanan semantiğini SQL semantiği yansıtır.</span><span class="sxs-lookup"><span data-stu-id="29bd1-170">The semantics reflect SQL semantics as defined by server or connection settings.</span></span> <span data-ttu-id="29bd1-171">(Semantiğini değiştirmek için ayarları değiştirebilirsiniz, ancak) iki null değerler varsayılan SQL Server Ayarları altında eşit olarak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-171">Two null values are considered unequal under default SQL Server settings (although you can change the settings to change the semantics).</span></span> <span data-ttu-id="29bd1-172">Ne olursa olsun, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sorgusu çevirisi sunucu ayarlarını dikkate almaz.</span><span class="sxs-lookup"><span data-stu-id="29bd1-172">Regardless, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not consider server settings in query translation.</span></span>  
  
 <span data-ttu-id="29bd1-173">Değişmez değeri ile bir karşılaştırma `null` (`nothing`) uygun SQL sürümü çevrilir (`is null` veya `is not null`).</span><span class="sxs-lookup"><span data-stu-id="29bd1-173">A comparison with the literal `null` (`nothing`) is translated to the appropriate SQL version (`is null` or `is not null`).</span></span>  
  
 <span data-ttu-id="29bd1-174">Değeri `null` (`nothing`) harmanlamasında SQL Server tarafından; tanımlanır [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] harmanlama değiştirmez.</span><span class="sxs-lookup"><span data-stu-id="29bd1-174">The value of `null` (`nothing`) in collation is defined by SQL Server; [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not change the collation.</span></span>  
  
### <a name="type-conversion-and-promotion"></a><span data-ttu-id="29bd1-175">Tür dönüştürmeleri ve yükseltme</span><span class="sxs-lookup"><span data-stu-id="29bd1-175">Type Conversion and Promotion</span></span>  
 <span data-ttu-id="29bd1-176">SQL deyimlerinde örtük dönüşümler zengin bir kümesini destekler.</span><span class="sxs-lookup"><span data-stu-id="29bd1-176">SQL supports a rich set of implicit conversions in expressions.</span></span> <span data-ttu-id="29bd1-177">C# benzer ifadeleri açık atama gerektirir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-177">Similar expressions in C# would require an explicit cast.</span></span> <span data-ttu-id="29bd1-178">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="29bd1-178">For example:</span></span>  
  
-   <span data-ttu-id="29bd1-179">`Nvarchar`ve `DateTime` türleri karşılaştırılabilir SQL'de tüm açık atamaları; C# açık dönüşüm gerektirir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-179">`Nvarchar` and `DateTime` types can be compared in SQL without any explicit casts; C# requires explicit conversion.</span></span>  
  
-   <span data-ttu-id="29bd1-180">`Decimal`örtük olarak dönüştürülür `DateTime` SQL.</span><span class="sxs-lookup"><span data-stu-id="29bd1-180">`Decimal` is implicitly converted to `DateTime` in SQL.</span></span> <span data-ttu-id="29bd1-181">C# için örtük bir dönüştürme izin vermiyor.</span><span class="sxs-lookup"><span data-stu-id="29bd1-181">C# does not allow for an implicit conversion.</span></span>  
  
 <span data-ttu-id="29bd1-182">Benzer şekilde, temel türleri kümesi farklı olduğundan türü öncelik Transact-SQL C# türü öncelik farklıdır.</span><span class="sxs-lookup"><span data-stu-id="29bd1-182">Likewise, type precedence in Transact-SQL differs from type precedence in C# because the underlying set of types is different.</span></span> <span data-ttu-id="29bd1-183">Aslında, öncelik listeleri arasındaki Temizle alt/üst ilişkisi yoktur.</span><span class="sxs-lookup"><span data-stu-id="29bd1-183">In fact, there is no clear subset/superset relationship between the precedence lists.</span></span> <span data-ttu-id="29bd1-184">Örneğin, karşılaştırma bir `nvarchar` ile bir `varchar` örtük dönüştürme neden `varchar` ifade `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="29bd1-184">For example, comparing an `nvarchar` with a `varchar` causes the implicit conversion of the `varchar` expression to `nvarchar`.</span></span> <span data-ttu-id="29bd1-185">CLR eşdeğer bir yükseltme sağlar.</span><span class="sxs-lookup"><span data-stu-id="29bd1-185">The CLR provides no equivalent promotion.</span></span>  
  
 <span data-ttu-id="29bd1-186">Basit durumda, bu farklılıklar CLR ifadeleri yayınları için karşılık gelen bir SQL ifadesi gereksiz olmasına neden.</span><span class="sxs-lookup"><span data-stu-id="29bd1-186">In simple cases, these differences cause CLR expressions with casts to be redundant for a corresponding SQL expression.</span></span> <span data-ttu-id="29bd1-187">Daha da önemlisi, bir SQL ifadesi Ara sonuçlarını örtük olarak hiçbir doğru karşılık gelen C# ' ta sahip bir türü yükseltilmesi ve bunun tam tersi.</span><span class="sxs-lookup"><span data-stu-id="29bd1-187">More importantly, the intermediate results of a SQL expression might be implicitly promoted to a type that has no accurate counterpart in C#, and vice versa.</span></span> <span data-ttu-id="29bd1-188">Genel olarak, test, hata ayıklama ve bu tür bir ifade doğrulama ekler önemli yük kullanıcı.</span><span class="sxs-lookup"><span data-stu-id="29bd1-188">Overall, the testing, debugging, and validation of such expressions adds significant burden on the user.</span></span>  
  
### <a name="collation"></a><span data-ttu-id="29bd1-189">Harmanlama</span><span class="sxs-lookup"><span data-stu-id="29bd1-189">Collation</span></span>  
 <span data-ttu-id="29bd1-190">Transact-SQL açık harmanlamaları karakter dizesi türleri için ek açıklamaları olarak destekler.</span><span class="sxs-lookup"><span data-stu-id="29bd1-190">Transact-SQL supports explicit collations as annotations to character string types.</span></span> <span data-ttu-id="29bd1-191">Bu harmanlamaları belirli karşılaştırmaları geçerliliğini belirler.</span><span class="sxs-lookup"><span data-stu-id="29bd1-191">These collations determine the validity of certain comparisons.</span></span> <span data-ttu-id="29bd1-192">Örneğin, iki sütun farklı açık harmanlamaları ile karşılaştıran bir hatadır.</span><span class="sxs-lookup"><span data-stu-id="29bd1-192">For example, comparing two columns with different explicit collations is an error.</span></span> <span data-ttu-id="29bd1-193">Çok Basitleştirilmiş CTS dize türünün kullanımı gibi hataları neden olmaz.</span><span class="sxs-lookup"><span data-stu-id="29bd1-193">The use of much simplified CTS string type does not cause such errors.</span></span> <span data-ttu-id="29bd1-194">Aşağıdaki örnek göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="29bd1-194">Consider the following example:</span></span>  
  
```  
create table T2 (  
    Col1 nvarchar(10),  
    Col2      nvarchar(10) collate Latin_general_ci_as  
)  
```  
  
 [!code-csharp[DLinqMismatch#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#4)]
 [!code-vb[DLinqMismatch#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#4)]  
  
```  
Select …  
From …  
Where Col1 = Col2  
-- Error, collation conflict.  
```  
  
 <span data-ttu-id="29bd1-195">Sonuç harmanlama alt yan tümcesi oluşturur bir *kısıtlanmış türü* değiştirilebilir değil.</span><span class="sxs-lookup"><span data-stu-id="29bd1-195">In effect, the collation subclause creates a *restricted type* that is not substitutable.</span></span>  
  
 <span data-ttu-id="29bd1-196">Benzer şekilde, sıralama düzeni türü sistemlerden önemli ölçüde farklı olabilir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-196">Similarly, the sort order can be significantly different across the type systems.</span></span> <span data-ttu-id="29bd1-197">Bu farkı sonuçlarını sıralama etkiler.</span><span class="sxs-lookup"><span data-stu-id="29bd1-197">This difference affects the sorting of results.</span></span> <span data-ttu-id="29bd1-198"><xref:System.Guid>tüm 16 bayt lexicographic sıraya göre sıralanır (`IComparable()`), T-SQL GUID'lerini aşağıdaki sırayla karşılaştırır ise: node(10-15), clock-seq(8-9), time-high(6-7), time-mid(4-5), time-low(0-3).</span><span class="sxs-lookup"><span data-stu-id="29bd1-198"><xref:System.Guid> is sorted on all 16 bytes by lexicographic order (`IComparable()`), whereas T-SQL compares GUIDs in the following order: node(10-15), clock-seq(8-9), time-high(6-7), time-mid(4-5), time-low(0-3).</span></span> <span data-ttu-id="29bd1-199">NT tarafından üretilen GUID böyle bir sekizli sipariş varken bu sıralama SQL 7. 0 ' gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-199">This ordering was done in SQL 7.0 when NT-generated GUIDs had such an octet order.</span></span> <span data-ttu-id="29bd1-200">Yaklaşım aynı düğüm kümesine oluşturulan GUID'ler zaman damgası göre sıralı gelen güvence altına.</span><span class="sxs-lookup"><span data-stu-id="29bd1-200">The approach ensured that GUIDs generated at the same node cluster came together in sequential order according to timestamp.</span></span> <span data-ttu-id="29bd1-201">Yaklaşım da (hale eklemeleri ekler yerine rastgele IOs) dizin oluşturma için yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="29bd1-201">The approach was also useful for building indexes (inserts become appends instead of random IOs).</span></span> <span data-ttu-id="29bd1-202">Daha sonra Windows sırasını Gizlilik sorunları nedeniyle karıştırılmış, ancak SQL uyumluluğu korumak gerekir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-202">The order was scrambled later in Windows because of privacy concerns, but SQL must maintain compatibility.</span></span> <span data-ttu-id="29bd1-203">Geçici bir çözüm kullanmaktır <xref:System.Data.SqlTypes.SqlGuid> yerine <xref:System.Guid>.</span><span class="sxs-lookup"><span data-stu-id="29bd1-203">A workaround is to use <xref:System.Data.SqlTypes.SqlGuid> instead of <xref:System.Guid>.</span></span>  
  
### <a name="operator-and-function-differences"></a><span data-ttu-id="29bd1-204">İşleç ve işlev farklılıkları</span><span class="sxs-lookup"><span data-stu-id="29bd1-204">Operator and Function Differences</span></span>  
 <span data-ttu-id="29bd1-205">İşleçler ve temelde karşılaştırılabilir işlevleri farklý semantiklerine sahip.</span><span class="sxs-lookup"><span data-stu-id="29bd1-205">Operators and functions that are essentially comparable have subtly different semantics.</span></span> <span data-ttu-id="29bd1-206">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="29bd1-206">For example:</span></span>  
  
-   <span data-ttu-id="29bd1-207">C# için mantıksal işleçler işlenenler sözcük sırasını dayalı kısa devre semantiği belirtir `&&` ve `||`.</span><span class="sxs-lookup"><span data-stu-id="29bd1-207">C# specifies short circuit semantics based on lexical order of operands for logical operators `&&` and `||`.</span></span> <span data-ttu-id="29bd1-208">SQL kümesini temel alan sorgular için diğer yandan hedeflenen ve bu nedenle yürütme sırasını karar vermek en iyi hale getirme için özgürlüğü sağlar.</span><span class="sxs-lookup"><span data-stu-id="29bd1-208">SQL on the other hand is targeted for set-based queries and therefore provides more freedom for the optimizer to decide the order of execution.</span></span> <span data-ttu-id="29bd1-209">Etkileri bazıları şunlardır:</span><span class="sxs-lookup"><span data-stu-id="29bd1-209">Some of the implications include the following:</span></span>  
  
    -   <span data-ttu-id="29bd1-210">Anlam olarak eşdeğer çeviri duyar "`CASE` ...</span><span class="sxs-lookup"><span data-stu-id="29bd1-210">Semantically equivalent translation would require "`CASE` …</span></span> <span data-ttu-id="29bd1-211">`WHEN` …</span><span class="sxs-lookup"><span data-stu-id="29bd1-211">`WHEN` …</span></span> <span data-ttu-id="29bd1-212">`THEN`"işlenen yürütülmesi yeniden sıralama önlemek için SQL oluşturun.</span><span class="sxs-lookup"><span data-stu-id="29bd1-212">`THEN`" construct in SQL to avoid reordering of operand execution.</span></span>  
  
    -   <span data-ttu-id="29bd1-213">Gevşek bir çeviri `AND` / `OR` C# ifade ilk işlenen değerlendirme sonuca bağlı ikinci işlenen değerlendirmeye dayalıysa, işleçler beklenmeyen hatalara neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-213">A loose translation to `AND`/`OR` operators could cause unexpected errors if the C# expression relies on evaluation the second operand being based on the result of the evaluation of the first operand.</span></span>  
  
-   <span data-ttu-id="29bd1-214">`Round()`işlevi farklı semantiklerine sahip [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] ve T-SQL.</span><span class="sxs-lookup"><span data-stu-id="29bd1-214">`Round()` function has different semantics in [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] and in T-SQL.</span></span>  
  
-   <span data-ttu-id="29bd1-215">Dizeler için başlangıç dizini CLR 0 ancak SQL 1 ' dir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-215">Starting index for strings is 0 in the CLR but 1 in SQL.</span></span> <span data-ttu-id="29bd1-216">Bu nedenle, dizini içeren herhangi bir işlev dizin çeviri gerekir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-216">Therefore, any function that has index needs index translation.</span></span>  
  
-   <span data-ttu-id="29bd1-217">CLR ('%') modulus işleci kayan nokta numaraları destekler, ancak SQL desteklemez.</span><span class="sxs-lookup"><span data-stu-id="29bd1-217">The CLR supports modulus (‘%’) operator for floating point numbers but SQL does not.</span></span>  
  
-   <span data-ttu-id="29bd1-218">`Like` İşleci etkili bir şekilde otomatik aşırı örtük dönüşümler üzerinde temel alır.</span><span class="sxs-lookup"><span data-stu-id="29bd1-218">The `Like` operator effectively acquires automatic overloads based on implicit conversions.</span></span> <span data-ttu-id="29bd1-219">Rağmen `Like` işleci karakter dizesi türleri, sayısal türler arasında örtük dönüşüm üzerinde çalışılacak tanımlanır veya `DateTime` türlerine izin verir ile kullanılmak üzere bu dize olmayan türlerde için `Like` da.</span><span class="sxs-lookup"><span data-stu-id="29bd1-219">Although the `Like` operator is defined to operate on character string types, implicit conversion from numeric types or `DateTime` types allows for those non-string types to be used with `Like` just as well.</span></span> <span data-ttu-id="29bd1-220">CTS, karşılaştırılabilir örtük dönüşümler yok.</span><span class="sxs-lookup"><span data-stu-id="29bd1-220">In CTS, comparable implicit conversions do not exist.</span></span> <span data-ttu-id="29bd1-221">Bu nedenle, ek aşırı gereklidir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-221">Therefore, additional overloads are needed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="29bd1-222">Bu `Like` işleci davranış uygulanır C# Yalnızca; Visual Basic `Like` sözcüktür değişmez.</span><span class="sxs-lookup"><span data-stu-id="29bd1-222">This `Like` operator behavior applies to C# only; the Visual Basic `Like` keyword is unchanged.</span></span>  
  
-   <span data-ttu-id="29bd1-223">Taşma SQL'de her zaman işaretli ancak C# ' ta açıkça belirtilmesi gerekir (değil, [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) wraparound önlemek için.</span><span class="sxs-lookup"><span data-stu-id="29bd1-223">Overflow is always checked in SQL but it has to be explicitly specified in C# (not in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) to avoid wraparound.</span></span> <span data-ttu-id="29bd1-224">C1 + C2 C3 içinde depolanıyorsa tamsayı sütunları C1, C2 ve C3, verilen (güncelleştirme T ayarlamak C3 = C1 + C2).</span><span class="sxs-lookup"><span data-stu-id="29bd1-224">Given integer columns C1, C2 and C3, if C1+C2 is stored in C3 (Update T Set C3 = C1 + C2).</span></span>  
  
    ```  
    create table T3 (  
        Col1      integer,  
        Col2      integer  
    )  
    insert into T3 (col1, col2) values (2147483647, 5)  
    -- Valid values: max integer value and 5.  
    select * from T3 where col1 + col2 < 0  
    -- Produces arithmetic overflow error.  
    ```  
  
 [!code-csharp[DLinqMismatch#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#5)]
 [!code-vb[DLinqMismatch#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#5)]  
  
-   <span data-ttu-id="29bd1-225">SQL gerçekleştirir simetrik aritmetik sırasında yuvarlama [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] kullandığı banker yuvarlaması.</span><span class="sxs-lookup"><span data-stu-id="29bd1-225">SQL performs symmetric arithmetic rounding while [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] uses banker’s rounding.</span></span> <span data-ttu-id="29bd1-226">Bilgi Bankası makalesi 196652 ek ayrıntılar için bkz.</span><span class="sxs-lookup"><span data-stu-id="29bd1-226">See Knowledgebase article 196652 for additional details.</span></span>  
  
-   <span data-ttu-id="29bd1-227">Ortak yerel ayarlar için varsayılan olarak SQL'de karakter dizesi karşılaştırmaları duyarsızdır.</span><span class="sxs-lookup"><span data-stu-id="29bd1-227">By default, for common locales, character-string comparisons are case-insensitive in SQL.</span></span> <span data-ttu-id="29bd1-228">Visual Basic ve C# büyük küçük harfe duyarlıdır.</span><span class="sxs-lookup"><span data-stu-id="29bd1-228">In Visual Basic and in C#, they are case-sensitive.</span></span> <span data-ttu-id="29bd1-229">Örneğin, `s == "Food"` (`s = "Food"` içinde [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) ve `s == "Food"` farklı sonuçlar varsa sağlayabilen `s` olan `food`.</span><span class="sxs-lookup"><span data-stu-id="29bd1-229">For example, `s == "Food"` (`s = "Food"` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) and `s == "Food"` can yield different results if `s` is `food`.</span></span>  
  
    ```  
    -- Assume default US-English locale (case insensitive).  
    create table T4 (  
        Col1      nvarchar (256)  
    )  
    insert into T4 values (‘Food’)   
    insert into T4 values (‘FOOD’)  
    select * from T4 where Col1 = ‘food’  
    -- Both the rows are returned because of case-insensitive matching.  
    ```  
  
 [!code-csharp[DLinqMismatch#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#6)]
 [!code-vb[DLinqMismatch#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#6)]  
  
-   <span data-ttu-id="29bd1-230">İşleçler / sabit uzunlukta karakter türü SQL değişkenlerinde uygulanan işlevleri sahip aynı işleçleri / CLR uygulanan işlevleri daha önemli ölçüde farklı semantiği <xref:System.String?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="29bd1-230">Operators/ functions applied to fixed length character type arguments in SQL have significantly different semantics than the same operators/functions applied to the CLR <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="29bd1-231">Bu ayrıca türleri hakkında bölümde açıklanan eksik karşılık gelen sorun uzantısı olarak görüntülenmesine.</span><span class="sxs-lookup"><span data-stu-id="29bd1-231">This could also be viewed as an extension of the missing counterpart problem discussed in the section about types.</span></span>  
  
    ```  
    create table T4 (  
        Col1      nchar(4)  
    )  
    Insert into T5(Col1) values ('21');  
    Insert into T5(Col1) values ('1021');  
    Select * from T5 where Col1 like '%1'  
    -- Only the second row with Col1 = '1021' is returned.  
    -- Not the first row!  
    ```  
  
     [!code-csharp[DLinqMismatch#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#7)]
     [!code-vb[DLinqMismatch#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#7)]  
  
     <span data-ttu-id="29bd1-232">Dize birleştirme ile benzer bir sorun oluşur.</span><span class="sxs-lookup"><span data-stu-id="29bd1-232">A similar problem occurs with string concatenation.</span></span>  
  
    ```  
    create table T6 (  
        Col1      nchar(4)  
        Col2       nchar(4)  
    )  
    Insert into T6 values ('a', 'b');  
    Select Col1+Col2 from T6  
    -- Returns concatenation of padded strings "a   b   " and not "ab".  
    ```  
  
 <span data-ttu-id="29bd1-233">Özet olarak, karışık bir çeviri CLR ifadeler için gerekli olabilir ve ek işleçleri/işlevler SQL işlevselliği kullanıma sunmak gerekli olabilir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-233">In summary, a convoluted translation might be required for CLR expressions and additional operators/functions may be necessary to expose SQL functionality.</span></span>  
  
### <a name="type-casting"></a><span data-ttu-id="29bd1-234">Tür atama</span><span class="sxs-lookup"><span data-stu-id="29bd1-234">Type Casting</span></span>  
 <span data-ttu-id="29bd1-235">C# ve SQL, kullanıcılar ifade varsayılan semantikleri açık tür atamaları kullanarak değiştirebilirsiniz (`Cast` ve `Convert`).</span><span class="sxs-lookup"><span data-stu-id="29bd1-235">In C# and in SQL, users can override the default semantics of expressions by using explicit type casts (`Cast` and `Convert`).</span></span> <span data-ttu-id="29bd1-236">Ancak, bu özellik türü sistem sınırından gösterme bir ikilemini doğurur.</span><span class="sxs-lookup"><span data-stu-id="29bd1-236">However, exposing this capability across the type system boundary poses a dilemma.</span></span> <span data-ttu-id="29bd1-237">İstenen semantiği sağlar SQL cast kolayca bir karşılık gelen C cast # çevrilemiyor.</span><span class="sxs-lookup"><span data-stu-id="29bd1-237">A SQL cast that provides the desired semantics cannot be easily translated to a corresponding C# cast.</span></span> <span data-ttu-id="29bd1-238">Öte yandan, bir C# cast doğrudan Tür uyuşmazlıkları, eksik ortaklarınıza ve farklı türe öncelik hiyerarşileri nedeniyle cast bir eşdeğer SQL çevrilemez.</span><span class="sxs-lookup"><span data-stu-id="29bd1-238">On the other hand, a C# cast cannot be directly translated into an equivalent SQL cast because of type mismatches, missing counterparts, and different type precedence hierarchies.</span></span> <span data-ttu-id="29bd1-239">Tür sistemi uyuşmazlığı gösterme ve ifadesinin önemli güç kaybı arasında bir denge yoktur.</span><span class="sxs-lookup"><span data-stu-id="29bd1-239">There is a trade-off between exposing the type system mismatch and losing significant power of expression.</span></span>  
  
 <span data-ttu-id="29bd1-240">Diğer durumlarda, tür atama ya da etki alanında bir ifade doğrulanması için gerekli değil ancak varsayılan olmayan eşleme ifade doğru uygulandığından emin olmak için gerekli olabilir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-240">In other cases, type casting might not be needed in either domain for validation of an expression but might be required to make sure that a non-default mapping is correctly applied to the expression.</span></span>  
  
```  
-- Example from "Non-default Mapping" section extended  
create table T5 (  
    Col1      nvarchar(10),  
    Col2      nvarchar(10)  
)  
Insert into T5(col1, col2) values (‘3’, ‘2’);  
```  
  
 [!code-csharp[DLinqMismatch#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#8)]
 [!code-vb[DLinqMismatch#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#8)]  
  
```  
Select *  
From T5  
Where Col1 + Col2 > 4     
-- "Col1 + Col2" expr evaluates to '32'   
```  
  
## <a name="performance-issues"></a><span data-ttu-id="29bd1-241">Performans sorunları</span><span class="sxs-lookup"><span data-stu-id="29bd1-241">Performance Issues</span></span>  
 <span data-ttu-id="29bd1-242">Bazı SQL Server CLR için hesap türü farkları performans düşüklüğü resut türü sistemleri CLR ve SQL Server arasında çapraz zaman olabilir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-242">Accounting for some SQL Server-CLR type differences may resut in a decrease in performance when crossing between the CLR and SQL Server type systems.</span></span> <span data-ttu-id="29bd1-243">Performansı etkileyen senaryoları örnekleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="29bd1-243">Examples of scenarios impacting performance include the following:</span></span>  
  
-   <span data-ttu-id="29bd1-244">İçin değerlendirme sırası zorlandı mantıksal ve/veya işleçleri</span><span class="sxs-lookup"><span data-stu-id="29bd1-244">Forced order of evaluation for logical and/or operators</span></span>  
  
-   <span data-ttu-id="29bd1-245">Koşul değerlendirme sırası zorlamak için SQL oluşturma SQL iyileştirici'nin yeteneğini kısıtlar.</span><span class="sxs-lookup"><span data-stu-id="29bd1-245">Generating SQL to enforce order of predicate evaluation restricts the SQL optimizer’s ability.</span></span>  
  
-   <span data-ttu-id="29bd1-246">Tür dönüştürmeleri bir CLR derleyici veya nesne ilişkisel bir sorgu uygulaması tarafından sunulan olup olmadığını dizin kullanım curtail.</span><span class="sxs-lookup"><span data-stu-id="29bd1-246">Type conversions, whether introduced by a CLR compiler or by an Object-Relational query implementation, may curtail index usage.</span></span>  
  
     <span data-ttu-id="29bd1-247">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="29bd1-247">For example,</span></span>  
  
    ```  
    -- Table DDL  
    create table T5 (  
        Col1      varchar(100)  
    )  
    ```  
  
     [!code-csharp[DLinqMismatch#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#9)]
     [!code-vb[DLinqMismatch#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#9)]  
  
     <span data-ttu-id="29bd1-248">İfade çevirisi göz önünde bulundurun `(s = SOME_STRING_CONSTANT)`.</span><span class="sxs-lookup"><span data-stu-id="29bd1-248">Consider the translation of expression `(s = SOME_STRING_CONSTANT)`.</span></span>  
  
    ```  
    -- Corresponding part of SQL where clause  
    Where …  
    Col1 = SOME_STRING_CONSTANT  
    -- This expression is of the form <varchar> = <nvarchar>.  
    -- Hence SQL introduces a conversion from varchar to nvarchar,  
    --     resulting in  
    Where …  
    Convert(nvarchar(100), Col1) = SOME_STRING_CONSTANT  
    -- Cannot use the index for column Col1 for some implementations.  
    ```  
  
 <span data-ttu-id="29bd1-249">Anlam farklar ek olarak, performans etkileri CLR türü sistemleri ve SQL Server arasında çapraz yaparken göz önünde bulundurmanız önemlidir.</span><span class="sxs-lookup"><span data-stu-id="29bd1-249">In addition to semantic differences, it is important to consider impacts to performance when crossing between the SQL Server and CLR type systems.</span></span> <span data-ttu-id="29bd1-250">Büyük veri kümeleri için bu tür performans sorunlarını uygulama dağıtılabilir olup olmadığını belirleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="29bd1-250">For large data sets, such performance issues can determine whether an application is deployable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29bd1-251">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="29bd1-251">See Also</span></span>  
 [<span data-ttu-id="29bd1-252">Arka plan bilgileri</span><span class="sxs-lookup"><span data-stu-id="29bd1-252">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)