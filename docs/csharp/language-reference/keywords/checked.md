---
title: checked anahtar sözcüğü (C# Başvurusu)
ms.date: 07/20/2015
f1_keywords:
- checked_CSharpKeyword
- checked
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
ms.openlocfilehash: 892b24b0283314f5aded0405df55a93069cf91e2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505261"
---
# <a name="checked-c-reference"></a>checked (C# Başvurusu)

`checked` Anahtar sözcüğü, Tamsayı türünde aritmetik işlemler ve dönüştürmeler için denetleme taşma açıkça etkinleştirmek için kullanılır.

Hedef türün aralığı dışında bir değer ifade oluşturursa, varsayılan olarak, yalnızca sabit değerleri içeren ifade bir derleyici hatasına neden olur. İfade, bir veya daha fazla sabit olmayan değerler içeriyorsa, derleyici taşma algılamaz. Atanan ifade değerlendirme `i2` aşağıdaki örnekte, bir derleyici hatasına neden olmaz.

[!code-csharp[csrefKeywordsChecked#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#3)]

Varsayılan olarak, bu sabit ifadeler taşma için çalışma zamanında ya da denetlenmez ve taşma özel geçirmeyin. Önceki örnekte, iki pozitif tam sayının toplamını-2,147,483,639 görüntüler.

Taşma denetimi etkinleştirilebilir derleyici seçenekleri, ortamı yapılandırması veya kullanımı `checked` anahtar sözcüğü. Aşağıdaki örnek nasıl kullanılacağını gösteren bir `checked` ifade veya `checked` çalışma zamanında önceki toplamı tarafından üretilen taşma algılamak için blok. Örneklerin her ikisi de bir taşma özel durumu oluşturun.

[!code-csharp[csrefKeywordsChecked#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#4)]

[Denetlenmeyen](../../../csharp/language-reference/keywords/unchecked.md) anahtar sözcüğü, taşma denetimi önlemek için kullanılabilir.

## <a name="example"></a>Örnek

Bu örnek nasıl kullanılacağını gösterir `checked` taşma çalışma zamanında denetimini etkinleştirmek için.

[!code-csharp[csrefKeywordsChecked#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#1)]

## <a name="c-language-specification"></a>C# dili belirtimi

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../../../csharp/language-reference/index.md)  
- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
- [C# Anahtar Sözcükleri](../../../csharp/language-reference/keywords/index.md)  
- [İşaretli ve İşaretsiz](../../../csharp/language-reference/keywords/checked-and-unchecked.md)  
- [unchecked](../../../csharp/language-reference/keywords/unchecked.md)
