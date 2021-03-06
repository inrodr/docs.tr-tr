---
title: Ara gerçekleştirme (C#)
ms.date: 07/20/2015
ms.assetid: 7922d38f-5044-41cf-8e17-7173d6553a5e
ms.openlocfilehash: 56c4bb57a931362b3e14f6a8da917ae6907565d6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516549"
---
# <a name="intermediate-materialization-c"></a>Ara gerçekleştirme (C#)
Dikkatli emin değilseniz, bazı durumlarda, önemli ölçüde, uygulamanızın bellek ve performans profili sorgularınızdaki koleksiyonların erken materialization neden olarak değiştirebilirsiniz. Bazı standart sorgu işleçleri, tek bir öğe oluşturan önce kaynak koleksiyonu materialization neden. Örneğin, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> önce tüm kaynak toplulukta tekrarlanan sonra tüm öğeleri sıralar ve son olarak ilk öğeyi verir. Bu, ilk öğesinde, sıralı bir koleksiyonu almak pahalı olduğunu gösterir; her öğe bundan sonra pahalı değil. Bu mantıklı: yapmak bu sorgu işleci için mümkün olacaktır.  
  
## <a name="example"></a>Örnek  
 Bu örnek önceki örnekle değiştirir. `AppendString` Yöntem çağrılarını <xref:System.Linq.Enumerable.ToList%2A> kaynağı aracılığıyla yineleme önce. Bu, materialization yol açar.  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        // the following statement materializes the source collection in a List<T>  
        // before iterating through it  
        foreach (string str in source.ToList())  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 Bu örnek aşağıdaki çıktıyı üretir:  
  
```  
ToUpper: source >abc<  
ToUpper: source >def<  
ToUpper: source >ghi<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 Bu örnekte, gördüğünüz gibi çağrısı <xref:System.Linq.Enumerable.ToList%2A> neden `AppendString` ilk öğeyi oluşturan önce tüm kaynak numaralandırılamadı. Kaynak uzun bir diziye varsa, bu uygulamanın bellek profili önemli ölçüde alter.  
  
 Ayrıca standart sorgu işleçlerini birbirine zincirlenebilir. Bu öğreticideki son konu bunu göstermektedir.  
  
-   [Zincirleme standart sorgu işleçleri (C#)](../../../../csharp/programming-guide/concepts/linq/chaining-standard-query-operators-together.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [Öğretici: Sorguları birbirine (C#) zincirleme](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
