---
title: public anahtar sözcüğü (C# Başvurusu)
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: b2e09bdb16d6128d69a3eb33cf2cffd4cba60376
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2018
ms.locfileid: "43518192"
---
# <a name="public-c-reference"></a>public (C# Başvurusu)

`public` Anahtar sözcüğü, türler ve tür üyeleri için bir erişim değiştiricisidir. Genel erişim, en esnek erişim düzeyidir. Bu örnekte olduğu gibi public üyelere erişmede hiçbir kısıtlama vardır:

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

Bkz: [erişim değiştiricileri](../../programming-guide/classes-and-structs/access-modifiers.md) ve [erişilebilirlik düzeyleri](accessibility-levels.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, iki sınıf bildirilen, `PointTest` ve `MainClass`. Genel üyeleri `x` ve `y` , `PointTest` doğrudan erişilir `MainClass`.

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

Değiştirirseniz `public` erişim düzeyi için [özel](private.md) veya [korumalı](protected.md), hata iletisi alırsınız:

'PointTest.y' koruma düzeyi nedeniyle erişilemez durumda.

## <a name="c-language-specification"></a>C# dili belirtimi  

Daha fazla bilgi için [erişilebilirlik bildirilen](~/_csharplang/spec/basic-concepts.md#declared-accessibility) içinde [ C# dil belirtimi](../language-specification/index.md). Dil belirtimi, C# sözdizimi ve kullanımı için kesin bir kaynaktır.

## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../index.md)
- [C# Programlama Kılavuzu](../../programming-guide/index.md)
- [Erişim Değiştiricileri](../../programming-guide/classes-and-structs/access-modifiers.md)
- [C# Anahtar Sözcükleri](index.md)
- [Erişim Değiştiricileri](access-modifiers.md)
- [Erişilebilirlik Düzeyleri](accessibility-levels.md)
- [Değiştiriciler](modifiers.md)
- [private](private.md)
- [protected](protected.md)
- [internal](internal.md)