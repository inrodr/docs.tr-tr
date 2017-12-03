---
title: "Standart sorgu işleçleri (Visual Basic) yürütme yöntemine göre sınıflandırılması"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f55b0be-9f6e-44f8-865c-6afbea50cc54
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 553a638cdaaebeaa5ab21850250b2d70536f557c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="classification-of-standard-query-operators-by-manner-of-execution-visual-basic"></a>Standart sorgu işleçleri (Visual Basic) yürütme yöntemine göre sınıflandırılması
Standart sorgu işleci yöntemleri nesneleri uygulamalarına LINQ iki ana yoldan biriyle yürütün: anlık veya ertelenmiş. Ertelenmiş yürütme kullanmak sorgu işleçleri Ayrıca iki kategoriye ayrılabilir: akış ve akış dışı. Farklı sorgu işleçleri nasıl yürütme biliyorsanız, belirli bir sorgudan Al sonuçları anlamanıza yardımcı olabilir. Bu veri kaynağı değiştiriyorsa veya başka bir sorgu en üstünde bir sorgu oluşturuyorsanız özellikle doğrudur. Bu konuda standart sorgu işleçleri kendi yürütme yöntemine göre sınıflandırır.  
  
## <a name="manners-of-execution"></a>Yolla yürütme  
  
### <a name="immediate"></a>Hemen  
 Hemen bir yürütme veri kaynağı okuyun ve işlem kodda bir noktada sorgu burada bildirilmiş gerçekleştirilir anlamına gelir. Numaralandırılabilir olmayan, tek bir sonuç tüm standart sorgu işleçleri hemen yürütün.  
  
### <a name="deferred"></a>Ertelenmiş  
 Ertelenmiş yürütme işlemi kodda bir noktada sorgu burada bildirilmiş gerçekleştirildiğini değil anlamına gelir. Yalnızca sorgu değişkeni, örneğin kullanarak numaralandırılır işlemi gerçekleştirilir bir `For Each` deyimi. Bu sorgu, sorgu zaman tanımlanan yerine yürütüldüğünde sorgu yürütülürken sonuçlarını'nın veri kaynağını içeriğine bağlı anlamına gelir. Sorgu değişkeni birden çok kez listelenebilir, sonuçları her zaman farklı olabilir. Dönüş türü olan neredeyse tüm standart sorgu işleçleri <xref:System.Collections.Generic.IEnumerable%601> veya <xref:System.Linq.IOrderedEnumerable%601> ertelenmiş bir biçimde yürütün.  
  
 Ertelenmiş yürütme kullanmak sorgu işleçleri ayrıca akış veya akış dışı olarak sınıflandırılabilir.  
  
#### <a name="streaming"></a>Akış  
 Akış işleçleri öğeleri verim önce tüm kaynak verileri okumak zorunda değildir. Salt okunur ve uygunsa öğesi verir yürütme zaman bir akış işleci her source öğesi kendi işlemi gerçekleştirir. Bir akış işleci bir sonuç öğesi üretilen kadar kaynak öğelerin okumaya devam eder. Başka bir deyişle, bir sonuç öğesi oluşturmak için birden fazla kaynak öğesi okuma.  
  
#### <a name="non-streaming"></a>Akış dışı  
 Bir sonuç öğesi sağlayabilen önce olmayan akış işleçler tüm kaynak verileri okumalısınız. Sıralama veya gruplama gibi işlemler bu kategoriye girer. Yürütme zaman, akış dışı sorgu işleçleri tüm kaynak verileri okumak, bir veri yapısında put, işlemi gerçekleştirmek ve sonuçta elde edilen öğeleri verim.  
  
## <a name="classification-table"></a>Sınıflandırma tablosu  
 Aşağıdaki tabloda her standart sorgu işleci yöntemi yürütme yönteminin göre sınıflandırır.  
  
> [!NOTE]
>  Bir işleç iki sütun olarak işaretlenmişse iki giriş dizilerini işlemde oynayan ve her sırası farklı değerlendirilir. Bu durumlarda, her zaman değerlendirileceğini parametre listesi ilk sırada olduğu şekilde ertelenmiş, akış.  
  
|Standart sorgu işleci|Dönüş Türü|Hemen Yürütme|Ertelenmiş akış yürütme|Akış dışı yürütme ertelenmiş|  
|-----------------------------|-----------------|-------------------------|----------------------------------|---------------------------------------|  
|<xref:System.Linq.Enumerable.Aggregate%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.All%2A>|<xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Any%2A>|<xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.AsEnumerable%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Average%2A>|Tek bir sayısal değer|X|||  
|<xref:System.Linq.Enumerable.Cast%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Concat%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Contains%2A>|<xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Count%2A>|<xref:System.Int32>|X|||  
|<xref:System.Linq.Enumerable.DefaultIfEmpty%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Distinct%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.ElementAt%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.Empty%2A>|<xref:System.Collections.Generic.IEnumerable%601>|X|||  
|<xref:System.Linq.Enumerable.Except%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X|X|  
|<xref:System.Linq.Enumerable.First%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.FirstOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.GroupBy%2A>|<xref:System.Collections.Generic.IEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.GroupJoin%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X|X|  
<xref:System.Linq.Enumerable.Intersect%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X|X|  
|<xref:System.Linq.Enumerable.Join%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X|X|  
|<xref:System.Linq.Enumerable.Last%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.LastOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.LongCount%2A>|<xref:System.Int64>|X|||  
|<xref:System.Linq.Enumerable.Max%2A>|Tek bir sayısal değer, TSource veya TResult|X|||  
|<xref:System.Linq.Enumerable.Min%2A>|Tek bir sayısal değer, TSource veya TResult|X|||  
|<xref:System.Linq.Enumerable.OfType%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.OrderBy%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.OrderByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.Range%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Repeat%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Reverse%2A>|<xref:System.Collections.Generic.IEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.Select%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.SelectMany%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.SequenceEqual%2A>|<xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Single%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.SingleOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.Skip%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.SkipWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Sum%2A>|Tek bir sayısal değer|X|||  
|<xref:System.Linq.Enumerable.Take%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
<xref:System.Linq.Enumerable.TakeWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.ThenBy%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.ThenByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.ToArray%2A>|TSource dizisi|X|||  
|<xref:System.Linq.Enumerable.ToDictionary%2A>|<xref:System.Collections.Generic.Dictionary%602>|X|||  
|<xref:System.Linq.Enumerable.ToList%2A>|<xref:System.Collections.Generic.IList%601>|X|||  
|<xref:System.Linq.Enumerable.ToLookup%2A>|<xref:System.Linq.ILookup%602>|X|||  
|<xref:System.Linq.Enumerable.Union%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Where%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Linq.Enumerable>  
 [Standart sorgu işleçlerine genel bakış (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [Standart sorgu işleçleri (Visual Basic) için sorgu ifade sözdizimi](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)  
 [LINQ to nesneler (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)