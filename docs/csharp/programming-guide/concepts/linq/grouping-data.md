---
title: Verileri gruplandırma (C#)
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: 42e93bf291b0921d7aafa07265d1193387d46aa6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500321"
---
# <a name="grouping-data-c"></a>Verileri gruplandırma (C#)
Gruplandırma, böylece ortak bir özniteliği her gruptaki öğe paylaştırmak gruplar halinde veri yerleştirme işlemi için ifade eder.  
  
 Aşağıdaki çizimde, bir karakter dizisi gruplandırma sonuçlarını gösterir. Her grup için anahtar karakterdir.  
  
 ![LINQ gruplandırma işlemlerinin](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")  
  
 Veri öğeleri gruplayın standart sorgu işleci yöntemleri aşağıdaki bölümünde listelenir.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem adı|Açıklama|C# sorgu ifade sözdizimi|Daha fazla bilgi|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Gruplandırma ölçütü|Sık kullanılan bir özniteliği paylaşan öğeleri gruplandırır. Her grubu tarafından temsil edilen bir <xref:System.Linq.IGrouping%602> nesne.|`group … by`<br /><br /> veya<br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|ToLookup|İçine bir öğe ekler; bir <xref:System.Linq.Lookup%602> (bire çok bir sözlük) tabanlı bir anahtar Seçici işlevdir.|Yok.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a>Sorgu ifade sözdizimi örneği  
 Aşağıdaki kod örneğinde `group by` yan tümcesi bir liste çift veya tek sayı olup olmadıkları göre grup dizisidir.  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.

- <xref:System.Linq>  
- [Standart sorgu işleçlerine genel bakış (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
- [group yan tümcesi](../../../../csharp/language-reference/keywords/group-clause.md)  
- [Nasıl yapılır: iç içe geçmiş grup oluşturma](../../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)  
- [Nasıl yapılır: dosyaları uzantıya (LINQ) (C#) göre gruplama](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
- [Nasıl yapılır: sorgu sonuçlarını gruplandırma](../../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)  
- [Nasıl yapılır: gruplandırma işleminde alt sorgu gerçekleştirme](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)  
- [Nasıl yapılır: gruplar (LINQ) (C#) kullanarak bir dosyayı birden çok dosyaya bölme](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
