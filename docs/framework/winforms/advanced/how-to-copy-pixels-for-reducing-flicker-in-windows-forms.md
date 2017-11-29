---
title: "Nasıl yapılır: Windows Formlarında Titreşimi Azaltmak için Piksel Kopyalama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ed463b41d3c2a51b0f9be3d4ddabfd2d54a3c07
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="3a260-102">Nasıl yapılır: Windows Formlarında Titreşimi Azaltmak için Piksel Kopyalama</span><span class="sxs-lookup"><span data-stu-id="3a260-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="3a260-103">Basit bir grafik animasyon yapıldığında, kullanıcılar bazen titreşimi veya istenmeyen diğer görsel efektler karşılaşırsınız.</span><span class="sxs-lookup"><span data-stu-id="3a260-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="3a260-104">Bu sorunu sınırlamak için bir yolu, grafiğin üzerinde bir "bitblt" işlem kullanmaktır.</span><span class="sxs-lookup"><span data-stu-id="3a260-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="3a260-105">BitBlt "bit bloğu aktarımı" renk verilerin kaynak dikdörtgen piksel hedef dikdörtgene piksel ' dir.</span><span class="sxs-lookup"><span data-stu-id="3a260-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="3a260-106">Windows Forms ile bitblt kullanılarak gerçekleştirilir <xref:System.Drawing.Graphics.CopyFromScreen%2A> yöntemi <xref:System.Drawing.Graphics> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="3a260-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="3a260-107">Yöntem parametreleri kaynak ve hedef (olarak noktaları), kopyalanacak alanının boyutunu ve yeni Şekli çizmek için kullanılan grafik nesnesi belirtin.</span><span class="sxs-lookup"><span data-stu-id="3a260-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="3a260-108">Aşağıdaki örnekte, bir şekli formunda çizilir kendi <xref:System.Windows.Forms.Control.Paint> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="3a260-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="3a260-109">Ardından, <xref:System.Drawing.Graphics.CopyFromScreen%2A> yöntemi şekli çoğaltmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="3a260-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a260-110">Formun ayarlama <xref:System.Windows.Forms.Control.DoubleBuffered%2A> özelliğine `true` grafik tabanlı kodda yapar <xref:System.Windows.Forms.Control.Paint> olay çift arabelleğe alındı.</span><span class="sxs-lookup"><span data-stu-id="3a260-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="3a260-111">Bu herhangi discernable performans artışı aşağıdaki kodu kullanırken olmaz olsa da, daha karmaşık grafik işleme kodu ile çalışırken göz önünde bulundurmanız bir şey durumdur.</span><span class="sxs-lookup"><span data-stu-id="3a260-111">While this will not have any discernable performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a260-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="3a260-112">Example</span></span>  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3a260-113">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="3a260-113">Compiling the Code</span></span>  
 <span data-ttu-id="3a260-114">Yukarıdaki kod formun Çalıştır <xref:System.Windows.Forms.Control.Paint> olay işleyicisi böylece form yeniden başlatıldığında grafik devam.</span><span class="sxs-lookup"><span data-stu-id="3a260-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="3a260-115">Bu nedenle, grafik ilgili yöntemleri çağırmayın <xref:System.Windows.Forms.Form.Load> olay işleyicisi, formu yeniden boyutlandırılmış veya başka bir form tarafından getirilmemeli çizilmiş içeriği yeniden değil çünkü.</span><span class="sxs-lookup"><span data-stu-id="3a260-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a260-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3a260-116">See Also</span></span>  
 <xref:System.Drawing.CopyPixelOperation>  
 <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="3a260-117">Grafikler ve Windows Forms'ta çizme</span><span class="sxs-lookup"><span data-stu-id="3a260-117">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="3a260-118">Çizgiler ve şekiller çizmek için kalem kullanma</span><span class="sxs-lookup"><span data-stu-id="3a260-118">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)