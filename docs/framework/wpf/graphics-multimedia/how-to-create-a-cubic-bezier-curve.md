---
title: "Nasıl yapılır: Üçüncü Dereceden Bezier Eğrisi Oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35d4fad0634586d5d0c6ea85f276d6e76edb3f63
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-cubic-bezier-curve"></a><span data-ttu-id="2d519-102">Nasıl yapılır: Üçüncü Dereceden Bezier Eğrisi Oluşturma</span><span class="sxs-lookup"><span data-stu-id="2d519-102">How to: Create a Cubic Bezier Curve</span></span>
<span data-ttu-id="2d519-103">Bu örnek bir küp Bezier eğrisinin nasıl oluşturulacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="2d519-103">This example shows how to create a cubic Bezier curve.</span></span> <span data-ttu-id="2d519-104">Küp Bezier eğrisi oluşturmak için kullanmak <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, ve <xref:System.Windows.Media.BezierSegment> sınıfları.</span><span class="sxs-lookup"><span data-stu-id="2d519-104">To create a cubic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.BezierSegment> classes.</span></span>  <span data-ttu-id="2d519-105">Sonuçta elde edilen geometri görüntülemek için kullanın bir <xref:System.Windows.Shapes.Path> öğesi veya onunla kullanın bir <xref:System.Windows.Media.GeometryDrawing> veya <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="2d519-105">To display the resulting geometry, use a <xref:System.Windows.Shapes.Path> element, or use it with a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="2d519-106">Küp Bezier eğrisi çizilir aşağıdaki örneklerde, (10, 100) için (300, 100).</span><span class="sxs-lookup"><span data-stu-id="2d519-106">In the following examples, a cubic Bezier curve is drawn from (10, 100) to (300, 100).</span></span> <span data-ttu-id="2d519-107">Denetim noktaları eğri vardır (100, 0) ve (200, 200).</span><span class="sxs-lookup"><span data-stu-id="2d519-107">The curve has control points of (100, 0) and (200, 200).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d519-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="2d519-108">Example</span></span>  
 <span data-ttu-id="2d519-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="2d519-109">[xaml]</span></span>  
  
 <span data-ttu-id="2d519-110">İçinde [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], bir yolu açıklamak için kısaltılmış biçimlendirme sözdizimini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2d519-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use abbreviated markup syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 <span data-ttu-id="2d519-111">[xaml]</span><span class="sxs-lookup"><span data-stu-id="2d519-111">[xaml]</span></span>  
  
 <span data-ttu-id="2d519-112">İçinde [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], ayrıca nesne etiketleri kullanılarak küp bir Bezier eğrisi çizebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2d519-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw a cubic Bezier curve using object tags.</span></span> <span data-ttu-id="2d519-113">Aşağıdaki önceki eşdeğerdir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] örnek.</span><span class="sxs-lookup"><span data-stu-id="2d519-113">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 <span data-ttu-id="2d519-114">Bu örnek daha büyük bir parçasıdır; tam bir örnek için bkz: [geometri örneği](http://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="2d519-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d519-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2d519-115">See Also</span></span>  
 [<span data-ttu-id="2d519-116">Elips yay oluşturma</span><span class="sxs-lookup"><span data-stu-id="2d519-116">Create an Elliptical Arc</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)  
 [<span data-ttu-id="2d519-117">İçinde bir LineSegment oluşturulacağını</span><span class="sxs-lookup"><span data-stu-id="2d519-117">Create a LineSegment in a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)  
 [<span data-ttu-id="2d519-118">Küp Bezier eğrisi oluşturma</span><span class="sxs-lookup"><span data-stu-id="2d519-118">Create a Cubic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)  
 [<span data-ttu-id="2d519-119">İkinci dereceden Bezier eğrisi oluşturma</span><span class="sxs-lookup"><span data-stu-id="2d519-119">Create a Quadratic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)