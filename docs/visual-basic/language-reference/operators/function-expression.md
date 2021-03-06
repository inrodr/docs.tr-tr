---
title: İşlev İfadesi (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: cfdd17f6f4ee6c4ddb3fa73ab3ec9c5ce46a162f
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2018
ms.locfileid: "46703004"
---
# <a name="function-expression-visual-basic"></a>İşlev İfadesi (Visual Basic)
Parametreleri işlevi lambda ifadesi tanımlayan ve kodu bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a>Bölümler  
  
|Terim|Tanım|  
|---|---|  
|`parameterlist`|İsteğe bağlı. Bu yordamı parametrelerini temsil eden yerel değişken adlarının listesi. Liste boş olduğunda bile parantezler bulunmalıdır. Bkz: [parametre listesi](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`expression`|Gerekli. Tek bir ifade. İşlevin dönüş türü ifade türüdür.|  
|`statements`|Gerekli. Kullanarak bir değer döndüren deyimlerin listesini `Return` deyimi. (Bkz [dönüş deyimi](../../../visual-basic/language-reference/statements/return-statement.md).) İşlevin dönüş türünü döndürülen değer türüdür.|  
  
## <a name="remarks"></a>Açıklamalar  
 A *lambda ifadesi* hesaplar ve bir değer döndüren bir adı olmayan bir işlevdir. Bir lambda ifadesi kullandığınız her yerde bir temsilci türü dışında bir bağımsız değişken olarak kullanabilirsiniz `RemoveHandler`. Temsilciler ve lambda ifadeleri temsilciler ile kullanımı hakkında daha fazla bilgi için bkz. [temsilci bildirimi](../../../visual-basic/language-reference/statements/delegate-statement.md) ve [gevşek temsilci dönüşümü](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Lambda İfadesi Sözdizimi  
 Bir lambda ifadesi söz dizimi, standart bir işlev benzer. Farklar aşağıdaki gibidir:  
  
-   Bir lambda ifadesi, bir adı yok.  
  
-   Lambda ifadeleri içeremez değiştiriciler, gibi `Overloads` veya `Overrides`.  
  
-   Lambda ifadeleri kullanma bir `As` işlevin dönüş türünü belirlemek için yan tümcesi. Bunun yerine, tek satırlı lambda ifadesinin gövdesinin değerlendiren değer veya çok satırlı lambda ifadesinin dönüş değeri türüne algılanır. Örneğin, tek satırlı lambda ifadesinin gövdesinin ise `Where cust.City = "London"`, kendi dönüş türü `Boolean`.  
  
-   Tek satırlı lambda ifadesinin gövdesinin deyim olmayan bir ifade olmalıdır. Gövdesi bir işlev yordam çağrısı, ancak bir alt yordam çağrısı değil oluşabilir.  
  
-   Tüm parametre ya da veri türleri veya tüm anlaşılmalıdır belirtilmelidir.  
  
-   İsteğe bağlı ve Paramarray parametrelerine izin verilmez.  
  
-   Genel Parametreler izin verilmez.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler, basit bir lambda ifadeleri oluşturmanın iki yolunu gösterir. İlk kullandığı bir `Dim` işlevi için bir ad sağlamak için. İşlev çağrısı için parametre için bir değer gönderin.  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a>Örnek  
 Alternatif olarak, bildirebilir ve aynı anda işlevi çalıştırın.  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a>Örnek  
 Bağımsız değişkeni artırır ve değer döndüren bir lambda ifadesi örneği verilmiştir. Bu örnek, hem tek satır ve çok satırlı lambda ifadesi söz dizimi işlevi için gösterir. Daha fazla örnek için bkz. [Lambda ifadeleri](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a>Örnek  
 Lambda ifadeleri sorgu işleçlerinin çoğu temelini oluşturan [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]ve metot tabanlı sorgu açıkça kullanılabilir. Aşağıdaki örnekte gösterilmektedir [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] yöntemi biçime sorgu çevirisi tarafından izlenen sorgu.  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Sorgu yöntemleri hakkında daha fazla bilgi için bkz. [sorguları](../../../visual-basic/language-reference/queries/index.md). Standart sorgu işleçleri hakkında daha fazla bilgi için bkz. [standart sorgu işleçlerine genel bakış](../../programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Function Deyimi](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Lambda İfadeleri](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [İşleçler ve İfadeler](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Deyimler](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Değer Karşılaştırmaları](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Boole İfadeleri](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [If İşleci](../../../visual-basic/language-reference/operators/if-operator.md)  
 [Gevşek Temsilci Dönüştürme](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
