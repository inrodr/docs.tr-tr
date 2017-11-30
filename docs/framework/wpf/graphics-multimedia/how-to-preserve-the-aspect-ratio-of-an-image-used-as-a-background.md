---
title: "Nasıl yapılır: Arka Plan Olarak Kullanılan bir Görüntünün En Boy Oranını Koruma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a34377403a55ba42d9d3f2946ef26ea48982f5d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a><span data-ttu-id="7d362-102">Nasıl yapılır: Arka Plan Olarak Kullanılan bir Görüntünün En Boy Oranını Koruma</span><span class="sxs-lookup"><span data-stu-id="7d362-102">How to: Preserve the Aspect Ratio of an Image Used as a Background</span></span>
<span data-ttu-id="7d362-103">Bu örnek nasıl kullanılacağını gösterir <xref:System.Windows.Media.TileBrush.Stretch%2A> özelliği bir <xref:System.Windows.Media.ImageBrush> resmin oranını korumak için.</span><span class="sxs-lookup"><span data-stu-id="7d362-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of an <xref:System.Windows.Media.ImageBrush> in order to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="7d362-104">Varsayılan olarak kullandığınızda, bir <xref:System.Windows.Media.ImageBrush> bir alanı boyamak için tamamen çıktı alanını doldurmak için içeriği uzatılır.</span><span class="sxs-lookup"><span data-stu-id="7d362-104">By default, when you use an <xref:System.Windows.Media.ImageBrush> to paint an area, its content stretches to completely fill the output area.</span></span> <span data-ttu-id="7d362-105">Çıkış alanı ve görüntünün farklı en boy oranlarına sahip olduğunda bu yayarak resmin bozuk.</span><span class="sxs-lookup"><span data-stu-id="7d362-105">When the output area and the image have different aspect ratios, the image is distorted by this stretching.</span></span>  
  
 <span data-ttu-id="7d362-106">Yapmak için bir <xref:System.Windows.Media.ImageBrush> görüntüsünü en boy oranını korumak, Ayarla <xref:System.Windows.Media.TileBrush.Stretch%2A> özelliğine <xref:System.Windows.Media.Stretch.Uniform> veya <xref:System.Windows.Media.Stretch.UniformToFill>.</span><span class="sxs-lookup"><span data-stu-id="7d362-106">To make an <xref:System.Windows.Media.ImageBrush> preserve the aspect ratio of its image, set the <xref:System.Windows.Media.TileBrush.Stretch%2A> property to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d362-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="7d362-107">Example</span></span>  
 <span data-ttu-id="7d362-108">Aşağıdaki örnekte iki kullanan <xref:System.Windows.Media.ImageBrush> iki dikdörtgen boyamak için nesneleri.</span><span class="sxs-lookup"><span data-stu-id="7d362-108">The following example uses two <xref:System.Windows.Media.ImageBrush> objects to paint two rectangles.</span></span> <span data-ttu-id="7d362-109">Her dikdörtgen 300 150 piksel ve her 300 tarafından 300 piksel resim içerir.</span><span class="sxs-lookup"><span data-stu-id="7d362-109">Each rectangle is 300 by 150 pixels and each contains a 300 by 300 pixel image.</span></span> <span data-ttu-id="7d362-110"><xref:System.Windows.Media.TileBrush.Stretch%2A> İlk fırça özelliği ayarlanmış <xref:System.Windows.Media.Stretch.Uniform>ve <xref:System.Windows.Media.TileBrush.Stretch%2A> ikinci fırça özelliği ayarlanmış <xref:System.Windows.Media.Stretch.UniformToFill>.</span><span class="sxs-lookup"><span data-stu-id="7d362-110">The <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the first brush is set to <xref:System.Windows.Media.Stretch.Uniform>, and the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the second brush is set to <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 <span data-ttu-id="7d362-111">Aşağıdaki çizimde sahip ilk fırça çıktısını gösterir bir <xref:System.Windows.Media.TileBrush.Stretch%2A> ayarıyla <xref:System.Windows.Media.Stretch.Uniform>.</span><span class="sxs-lookup"><span data-stu-id="7d362-111">The following illustration shows the output of the first brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.Uniform>.</span></span>  
  
 <span data-ttu-id="7d362-112">![Uniform uzatma içeren ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span><span class="sxs-lookup"><span data-stu-id="7d362-112">![ImageBrush with Uniform stretching](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span></span>  
  
 <span data-ttu-id="7d362-113">Sonraki şekilde sahip ikinci fırça çıktısı gösterilmektedir bir <xref:System.Windows.Media.TileBrush.Stretch%2A> ayarıyla <xref:System.Windows.Media.Stretch.UniformToFill>.</span><span class="sxs-lookup"><span data-stu-id="7d362-113">The next illustration shows the output of the second brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 <span data-ttu-id="7d362-114">![UniformToFill uzatma ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span><span class="sxs-lookup"><span data-stu-id="7d362-114">![ImageBrush with UniformToFill stretching](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span></span>  
  
 <span data-ttu-id="7d362-115">Unutmayın <xref:System.Windows.Media.TileBrush.Stretch%2A> özelliği aynı şekilde davrandığını diğer <xref:System.Windows.Media.TileBrush> , yani, nesne için <xref:System.Windows.Media.DrawingBrush> ve <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="7d362-115">Note that the <xref:System.Windows.Media.TileBrush.Stretch%2A> property behaves identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="7d362-116">Hakkında daha fazla bilgi için <xref:System.Windows.Media.ImageBrush> ve diğer <xref:System.Windows.Media.TileBrush> nesneleri bkz [görüntüleri, çizimler ve görsellerle boyama](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="7d362-116">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="7d362-117">Ancak ayrıca <xref:System.Windows.Media.TileBrush.Stretch%2A> özelliği görünür belirtmek için nasıl <xref:System.Windows.Media.TileBrush> içeriğini uzatır çıkış alanına uyacak şekilde gerçekte belirtir nasıl <xref:System.Windows.Media.TileBrush> içerik temel döşemesinin doldurmak için uzatır.</span><span class="sxs-lookup"><span data-stu-id="7d362-117">Note also that, although the <xref:System.Windows.Media.TileBrush.Stretch%2A> property appears to specify how the <xref:System.Windows.Media.TileBrush> content stretches to fit its output area, it actually specifies how the <xref:System.Windows.Media.TileBrush> content stretches to fill its base tile.</span></span> <span data-ttu-id="7d362-118">Daha fazla bilgi için bkz. <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="7d362-118">For more information, see <xref:System.Windows.Media.TileBrush>.</span></span>  
  
 <span data-ttu-id="7d362-119">Bu kod örneği için sağlanan daha büyük bir örneğin parçasıdır <xref:System.Windows.Media.ImageBrush> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="7d362-119">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="7d362-120">Tam bir örnek için bkz: [ImageBrush örneği](http://go.microsoft.com/fwlink/?LinkID=160005).</span><span class="sxs-lookup"><span data-stu-id="7d362-120">For the complete sample, see [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d362-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7d362-121">See Also</span></span>  
 <xref:System.Windows.Media.TileBrush>  
 [<span data-ttu-id="7d362-122">Görüntüleri, çizimler ve görsellerle boyama</span><span class="sxs-lookup"><span data-stu-id="7d362-122">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)