---
title: unsafe (C# Başvurusu)
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: f4fcff02166091ae5dbd83e7ddf7762373fd9836
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086459"
---
# <a name="unsafe-c-reference"></a>unsafe (C# Başvurusu)
`unsafe` Anahtar sözcüğü, işaretçileri içeren tüm işlemler için gerekli olan güvensiz bir bağlamı gösterir. Daha fazla bilgi için [güvenli olmayan kod ve işaretçiler](../../../csharp/programming-guide/unsafe-code-pointers/index.md).  
  
 Kullanabileceğiniz `unsafe` bildirimi bir tür veya üye değiştiricisi. Türe veya üyeye tüm metinsel kapsamını, bu nedenle güvenli olmayan bir bağlam kabul edilir. Örneğin, aşağıdaki ile bildirilen bir yöntemi olan `unsafe` değiştiricisi:  
  
```csharp  
unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 İşaretçiler, parametre listesinde kullanılabilmesi için güvenli olmayan bir bağlam kapsamını parametre listesinden, yöntemin sonuna kadar genişletir:  
  
```csharp  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 Güvenli olmayan bir blok, bu blok içinde bir güvenli olmayan kod kullanımını etkinleştirmek için de kullanabilirsiniz. Örneğin:  
  
```csharp  
unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 Güvenli olmayan kod olarak derlemek için belirtmelisiniz [/ unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) derleyici seçeneği. Güvenli olmayan kod ortak dil çalışma zamanı tarafından doğrulanabilir değil.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a>C# Dil Belirtimi  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.

- [C# başvurusu](../../../csharp/language-reference/index.md)  
- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
- [C# Anahtar Sözcükleri](../../../csharp/language-reference/keywords/index.md)  
- [fixed Deyimi](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [Güvenli Olmayan Kod ve İşaretçiler](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [Sabit Boyutlu Arabellekler](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
