---
title: "Nasıl yapılır: Kullanıcıların Windows Forms DataGridView Denetiminden Panoya Birden Fazla Hücre Kopyalamasına Olanak Tanıma"
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
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 703284572005ab262a7e9379b601d8144d8e9af1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a><span data-ttu-id="334b3-102">Nasıl yapılır: Kullanıcıların Windows Forms DataGridView Denetiminden Panoya Birden Fazla Hücre Kopyalamasına Olanak Tanıma</span><span class="sxs-lookup"><span data-stu-id="334b3-102">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="334b3-103">Hücre kopyalama etkinleştirdiğinizde, verileri olun, <xref:System.Windows.Forms.DataGridView> denetim diğer uygulamalara kolayca erişilebilir <xref:System.Windows.Forms.Clipboard>.</span><span class="sxs-lookup"><span data-stu-id="334b3-103">When you enable cell copying, you make the data in your <xref:System.Windows.Forms.DataGridView> control easily accessible to other applications through the <xref:System.Windows.Forms.Clipboard>.</span></span> <span data-ttu-id="334b3-104">Seçili hücreleri değerlerini dizelere dönüştürülür ve panoya not defteri ve Excel gibi uygulamaları yapıştırma sekmeyle ayrılmış metin değerleri ve Word gibi uygulamalar yapıştırma HTML biçimli bir tablo olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="334b3-104">The values of the selected cells are converted to strings and added to the Clipboard as tab-delimited text values for pasting into applications like Notepad and Excel, and as an HTML-formatted table for pasting into applications like Word.</span></span>  
  
 <span data-ttu-id="334b3-105">Hücre değerlerini yalnızca kopyalama, satır ve sütun başlık metni panoya verilere dahil etmek veya yalnızca kullanıcıların tüm satır veya sütun seçtiğinizde üstbilgi metni içeren hücre kopyalama yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="334b3-105">You can configure cell copying to copy cell values only, to include row and column header text in the Clipboard data, or to include header text only when users select entire rows or columns.</span></span>  
  
 <span data-ttu-id="334b3-106">Seçim modu bağlı olarak, kullanıcılar hücre birden çok bağlantısı kesilmiş grupları seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="334b3-106">Depending on the selection mode, users can select multiple disconnected groups of cells.</span></span> <span data-ttu-id="334b3-107">Bir kullanıcı panoya hücreleri kopyaladığında, satırları ve sütunları yok seçili hücreler içeren kopyalanmaz.</span><span class="sxs-lookup"><span data-stu-id="334b3-107">When a user copies cells to the Clipboard, rows and columns with no selected cells are not copied.</span></span> <span data-ttu-id="334b3-108">Diğer tüm satır veya sütun satırları ve sütunları Panoya kopyalanan verileri tablosuna haline gelir.</span><span class="sxs-lookup"><span data-stu-id="334b3-108">All other rows or columns become rows and columns in the table of data copied to the Clipboard.</span></span> <span data-ttu-id="334b3-109">Bu satır veya sütun seçili hücreleri boş yer tutucu olarak panoya kopyalanır.</span><span class="sxs-lookup"><span data-stu-id="334b3-109">Unselected cells in these rows or columns are copied as blank placeholders to the Clipboard.</span></span>  
  
### <a name="to-enable-cell-copying"></a><span data-ttu-id="334b3-110">Hücre kopyalama etkinleştirmek için</span><span class="sxs-lookup"><span data-stu-id="334b3-110">To enable cell copying</span></span>  
  
-   <span data-ttu-id="334b3-111">Ayarlama <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> özelliği.</span><span class="sxs-lookup"><span data-stu-id="334b3-111">Set the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a><span data-ttu-id="334b3-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="334b3-112">Example</span></span>  
 <span data-ttu-id="334b3-113">Aşağıdaki tam kod örneği hücreleri panoya nasıl kopyalanacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="334b3-113">The following complete code example demonstrates how cells are copied to the Clipboard.</span></span> <span data-ttu-id="334b3-114">Bu örnek Pano kullanmaya seçili hücreleri kopyalar bir düğme içerir <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> Pano içeriği bir metin kutusunda yöntemi ve görüntüler.</span><span class="sxs-lookup"><span data-stu-id="334b3-114">This example includes a button that copies the selected cells to the Clipboard using the <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> method and displays the Clipboard contents in a text box.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="334b3-115">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="334b3-115">Compiling the Code</span></span>  
 <span data-ttu-id="334b3-116">Bu kodu gerektirir:</span><span class="sxs-lookup"><span data-stu-id="334b3-116">This code requires:</span></span>  
  
-   <span data-ttu-id="334b3-117">N: System ve N:System.Windows.Forms derlemelerine başvurular.</span><span class="sxs-lookup"><span data-stu-id="334b3-117">References to the N:System and N:System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="334b3-118">Bu örnek için komut satırından oluşturma hakkında bilgi için [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] veya [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], bkz: [komut satırından derleme](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [komut satırı derleme ile csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="334b3-118">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="334b3-119">Bu örnek ayrıca oluşturmak [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] yeni bir proje kodunu yapıştırma tarafından.</span><span class="sxs-lookup"><span data-stu-id="334b3-119">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="334b3-120">Ayrıca bkz. [nasıl yapılır: derleme ve çalıştırma bir tam Windows Forms kod örneği kullanarak Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="334b3-120">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="334b3-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="334b3-121">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>  
 [<span data-ttu-id="334b3-122">Seçim ve Pano kullanımı Windows Forms DataGridView denetimi ile</span><span class="sxs-lookup"><span data-stu-id="334b3-122">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)