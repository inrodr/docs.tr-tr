---
title: volatile (C# Başvurusu)
ms.date: 10/24/2018
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: 9950bb0e32787306dc34e2c006099332c06bda2b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199974"
---
# <a name="volatile-c-reference"></a>volatile (C# Başvurusu)

`volatile` Anahtar sözcüğü gösteren bir alan, aynı anda yürütülen birden çok iş parçacığı tarafından değiştirilebilir. Derleyici, çalışma zamanı sistemi ve hatta donanım okuma ve bellek konumlara yazma işlemleri performans nedeniyle yeniden. Bildirilen alanları `volatile` bu iyileştirmeler tabi değildir. Ekleme `volatile` değiştiricisi, tüm iş parçacıklarının bunlar hedeflenerek gerçekleştirildi sırada başka bir iş parçacığı tarafından gerçekleştirilen geçici yazma dikkate almasını sağlar. Bir tek toplam geçici yazma olarak görülen yürütme tüm iş parçacıklarından sıralama garantisi yoktur.
  
`volatile` Anahtar sözcüğü, bu tür alanlar için uygulanabilir:  
  
- Başvuru türleri.  
- İşaretçi türleri (güvenli olmayan bir bağlamda). İşaretçi geçici olabilir, ancak işaret nesnesi dönüştürülemez unutmayın. Diğer bir deyişle, "işaretçisi geçici." bildiremezsiniz.  
- Basit türler gibi `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float`, ve `bool`.  
- Bir `enum` aşağıdaki temel türlerinden birini türüyle: `byte`, `sbyte`, `short`, `ushort`, `int`, veya `uint`.  
- Başvuru türleri olarak bilinen genel tür parametreleri.
- <xref:System.IntPtr> ve <xref:System.UIntPtr>.  

Diğer türleri dahil olmak üzere, `double` ve `long`, işaretlenemiyor `volatile` çünkü okuma ve yazma işlemleri bu türlerin alanları atomik olmasını garanti edilemez. Bu tür alanlar çok iş parçacıklı erişimi korumak için kullanmak <xref:System.Threading.Interlocked> sınıf üyeleri veya erişim kullanarak koruma [ `lock` ](lock-statement.md) deyimi.

Volatile anahtar sözcüğü yalnızca alanlarına uygulanabilir bir `class` veya `struct`. Yerel değişkenler bildirilemez `volatile`.
  
## <a name="example"></a>Örnek

Aşağıdaki örnek, bir ortak alan değişken olarak bildirmek gösterilmektedir `volatile`.  
  
[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Declaration)]

Aşağıdaki örnek nasıl yardımcı veya çalışan iş parçacığı oluşturulabilir ve birincil iş parçacığının ile paralel işleme gerçekleştirmek için kullanılan gösterir. Arka plan bilgileri için çoklu iş parçacığı hakkında bkz: [yönetilen iş parçacığı](../../../standard/threading/index.md) ve [parçacıkları (C#)](../../programming-guide/concepts/threading/index.md).  
  
[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Volatile)]

İle `volatile` bildirimi için eklenen değiştiricisi `_shouldStop` yerde, her zaman aynı sonuçları (yukarıdaki kodda gösterildiği alıntı benzer) elde edersiniz. Ancak, bu değiştirici olmadan `_shouldStop` üyesi, davranıştır tahmin edilemez. `DoWork` Yöntemi eski verilerin okunmasını kaynaklanan üye erişimi iyileştirin. Çok iş parçacıklı programlama yapısı nedeniyle eski okuma sayısını tahmin edilemez. Programın farklı çalışmalarında biraz farklı sonuçlar oluşturur.

## <a name="c-language-specification"></a>C# Dil Belirtimi

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [C#dil belirtimi: volatile anahtar sözcüğü](../../../../_csharplang/spec/classes.md#volatile-fields)
- [C# başvurusu](../index.md)
- [C# Programlama Kılavuzu](../../programming-guide/index.md)
- [C# Anahtar Sözcükleri](index.md)
- [Değiştiriciler](modifiers.md)
- [lock deyimi](lock-statement.md)
- <xref:System.Threading.Interlocked> Sınıfı
