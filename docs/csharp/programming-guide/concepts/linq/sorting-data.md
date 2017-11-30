---
title: "Veri sıralama (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f5756c87f50e759542d0d1ccbb71710ad9eb6e27
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="sorting-data-c"></a><span data-ttu-id="4ebbd-102">Veri sıralama (C#)</span><span class="sxs-lookup"><span data-stu-id="4ebbd-102">Sorting Data (C#)</span></span>
<span data-ttu-id="4ebbd-103">Sıralama işlemi bir veya daha fazla özniteliklerini temel alarak bir sıradaki sıralar.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="4ebbd-104">İlk sıralama ölçütü birincil sıralama öğeleri gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="4ebbd-105">İkinci bir sıralama ölçütü belirterek, her birincil sıralama grup içindeki öğeleri sıralama yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="4ebbd-106">Aşağıdaki çizimde bir dizi karakterden oluşan bir alfabetik sıralama işlemi sonuçlarını gösterir.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="4ebbd-107">![Sıralama işlemi LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="4ebbd-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="4ebbd-108">Verileri sıralama standart sorgu işleci yöntemler aşağıdaki bölümde listelenmektedir.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4ebbd-109">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="4ebbd-109">Methods</span></span>  
  
|<span data-ttu-id="4ebbd-110">Yöntem adı</span><span class="sxs-lookup"><span data-stu-id="4ebbd-110">Method Name</span></span>|<span data-ttu-id="4ebbd-111">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4ebbd-111">Description</span></span>|<span data-ttu-id="4ebbd-112">C# sorgu ifade sözdizimi</span><span class="sxs-lookup"><span data-stu-id="4ebbd-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="4ebbd-113">Daha Fazla Bilgi</span><span class="sxs-lookup"><span data-stu-id="4ebbd-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="4ebbd-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="4ebbd-114">OrderBy</span></span>|<span data-ttu-id="4ebbd-115">Artan düzende değerlerini sıralar.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4ebbd-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="4ebbd-116">OrderByDescending</span></span>|<span data-ttu-id="4ebbd-117">Azalan düzende değerlerini sıralar.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4ebbd-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="4ebbd-118">ThenBy</span></span>|<span data-ttu-id="4ebbd-119">İkincil bir sıralama artan düzende gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4ebbd-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="4ebbd-120">ThenByDescending</span></span>|<span data-ttu-id="4ebbd-121">İkincil bir sıralamayı azalan sırada gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4ebbd-122">Ters Çevir</span><span class="sxs-lookup"><span data-stu-id="4ebbd-122">Reverse</span></span>|<span data-ttu-id="4ebbd-123">Bir koleksiyondaki öğelerin sırasını tersine çevirir.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="4ebbd-124">Yok.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="4ebbd-125">Sorgu ifade sözdizimi örnekleri</span><span class="sxs-lookup"><span data-stu-id="4ebbd-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="4ebbd-126">Birincil sıralama örnekleri</span><span class="sxs-lookup"><span data-stu-id="4ebbd-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="4ebbd-127">Birincil artan sıralama</span><span class="sxs-lookup"><span data-stu-id="4ebbd-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="4ebbd-128">Aşağıdaki örnekte nasıl kullanılacağı ortaya `orderby` dize uzunluğu, artan bir dizi dizelerde sıralamak için bir LINQ sorgu yan tümcesinde.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    brown  
    jumps  
*/  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="4ebbd-129">Birincil azalan sıralama</span><span class="sxs-lookup"><span data-stu-id="4ebbd-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="4ebbd-130">Sonraki örnek nasıl kullanılacağı ortaya `orderby``descending` azalan sırada kendi ilk harfi dizeleri sıralamak için bir LINQ sorgu yan tümcesinde.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-130">The next example demonstrates how to use the `orderby``descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    quick  
    jumps  
    fox  
    brown  
*/  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="4ebbd-131">İkincil sıralama örnekleri</span><span class="sxs-lookup"><span data-stu-id="4ebbd-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="4ebbd-132">İkincil artan sıralama</span><span class="sxs-lookup"><span data-stu-id="4ebbd-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="4ebbd-133">Aşağıdaki örnekte nasıl kullanılacağı ortaya `orderby` dizeleri birincil ve ikincil bir tür bir dizide gerçekleştirmek için bir LINQ sorgu yan tümcesinde.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="4ebbd-134">Dizeleri öncelikle uzunluğu ve ürüne ilk harfini dizesinin hem artan düzende sıralanır.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1)  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    fox  
    the  
    brown  
    jumps  
    quick  
*/  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="4ebbd-135">İkincil azalan sıralama</span><span class="sxs-lookup"><span data-stu-id="4ebbd-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="4ebbd-136">Sonraki örnek nasıl kullanılacağı ortaya `orderby``descending` birincil bir sıralama düzeni ve azalan bir ikincil sıralama artan düzende gerçekleştirmek için bir LINQ sorgu yan tümcesinde.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-136">The next example demonstrates how to use the `orderby``descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="4ebbd-137">Dizeleri öncelikle uzunluğu ve ürüne dizenin ilk harfini sıralanır.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    jumps  
    brown  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ebbd-138">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4ebbd-138">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="4ebbd-139">Standart sorgu işleçlerine genel bakış (C#)</span><span class="sxs-lookup"><span data-stu-id="4ebbd-139">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="4ebbd-140">OrderBy yan tümcesi</span><span class="sxs-lookup"><span data-stu-id="4ebbd-140">orderby clause</span></span>](../../../../csharp/language-reference/keywords/orderby-clause.md)  
 [<span data-ttu-id="4ebbd-141">Nasıl yapılır: Join tümcesinin sonuçlarını sıralama</span><span class="sxs-lookup"><span data-stu-id="4ebbd-141">How to: Order the Results of a Join Clause</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)  
 [<span data-ttu-id="4ebbd-142">Nasıl yapılır: sıralama veya filtre metni verilerle herhangi bir sözcük veya alana (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4ebbd-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)