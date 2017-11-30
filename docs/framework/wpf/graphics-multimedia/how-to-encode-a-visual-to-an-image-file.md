---
title: "Nasıl yapılır: Görüntü Dosyası İçine Bir Görseli Kodlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0a1ff9de1f5ddfdabbf7af7fef5f78046c14f8ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="787c8-102">Nasıl yapılır: Görüntü Dosyası İçine Bir Görseli Kodlama</span><span class="sxs-lookup"><span data-stu-id="787c8-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="787c8-103">Bu örnek nasıl kodlanacağını gösterir bir <xref:System.Windows.Media.Visual> kullanarak bir görüntü dosyası içine nesne bir <xref:System.Windows.Media.Imaging.RenderTargetBitmap> ve <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="787c8-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="787c8-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="787c8-104">Example</span></span>  
 <span data-ttu-id="787c8-105"><xref:System.Windows.Media.DrawingVisual> Kullanılarak oluşturulan bir <xref:System.Windows.Media.Imaging.BitmapImage> ve <xref:System.Windows.Media.FormattedText> için işlenen bir <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span><span class="sxs-lookup"><span data-stu-id="787c8-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="787c8-106">İşlenen bit eşlem sonra oluşturmak için kullanılan bir <xref:System.Windows.Media.Imaging.BitmapFrame> için eklenen <xref:System.Windows.Media.Imaging.PngBitmapEncoder> yeni [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] dosya.</span><span class="sxs-lookup"><span data-stu-id="787c8-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="787c8-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> Bu örnek ancak herhangi bir türetilmiş kullanılan <xref:System.Windows.Media.Imaging.BitmapEncoder> nesneleri kullanılabilirdi görüntü dosyası oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="787c8-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="787c8-108">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="787c8-108">See Also</span></span>  
 <xref:System.Windows.Media.DrawingContext>  
 [<span data-ttu-id="787c8-109">Görüntü oluşturmaya genel bakış</span><span class="sxs-lookup"><span data-stu-id="787c8-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [<span data-ttu-id="787c8-110">Çizim nesnelerine genel bakış</span><span class="sxs-lookup"><span data-stu-id="787c8-110">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="787c8-111">DrawingVisual nesnelerini kullanma</span><span class="sxs-lookup"><span data-stu-id="787c8-111">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)