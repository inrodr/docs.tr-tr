---
title: 'Nasıl yapılır: Bileşik Şekil Oluşturma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: 9892120d13a067586dbf6472a6873b6a52c2d8b4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515170"
---
# <a name="how-to-create-a-composite-shape"></a>Nasıl yapılır: Bileşik Şekil Oluşturma
Bu örnekte kullanarak bileşik şekil oluşturma işlemi gösterilmektedir <xref:System.Windows.Media.Geometry> nesneleri ve bunları görüntülemek kullanarak bir <xref:System.Windows.Shapes.Path> öğesi. Aşağıdaki örnekte, bir <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>ve <xref:System.Windows.Media.RectangleGeometry> ile kullanılan bir <xref:System.Windows.Media.GeometryGroup> bileşik şekil oluşturma. Geometriler kullanılarak çizilir bir <xref:System.Windows.Shapes.Path> öğesi.  
  
## <a name="example"></a>Örnek  
 [!code-xaml[GeometrySample#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 Önceki örnekte oluşturulan şekli aşağıda gösterilmiştir.  
  
 ![GeometryGroup kullanılarak oluşturulan bir Birleşik Geometri](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")  
Birleşik Geometri  
  
 Çokgen ve şekiller eğri kesimli gibi daha karmaşık şekiller kullanarak oluşturulabilir bir <xref:System.Windows.Media.PathGeometry>. Kullanma şekli oluşturmayı gösteren bir örnek için bir <xref:System.Windows.Media.PathGeometry>, bkz: [PathGeometry kullanarak şekil oluşturma](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).  Bu örnek ekran kullanarak bir şekil çizer rağmen bir <xref:System.Windows.Shapes.Path> öğesi <xref:System.Windows.Media.Geometry> nesneleri ayrıca içeriğini açıklamak için kullanılabilir bir <xref:System.Windows.Media.GeometryDrawing> veya <xref:System.Windows.Media.DrawingContext>. Bunlar, kırpma ve isabet sınaması için de kullanılabilir.  
  
 Bu örnek, daha büyük örnek bir parçasıdır; tam bir örnek için bkz. [geometri örneği](https://go.microsoft.com/fwlink/?LinkID=159989).
