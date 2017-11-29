---
title: "Nasıl yapılır: Menü Birleştirme ve ToolStrip Denetimleri içeren MDI Formu Oluşturma"
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
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b99f68c970efc096bc4dfab264183de11beb135
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="99eec-102">Nasıl yapılır: Menü Birleştirme ve ToolStrip Denetimleri içeren MDI Formu Oluşturma</span><span class="sxs-lookup"><span data-stu-id="99eec-102">How to: Create an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="99eec-103"><xref:System.Windows.Forms?displayProperty=nameWithType> Ad alanı birden çok belge arabirimi (MDI) uygulamaları destekler ve <xref:System.Windows.Forms.MenuStrip> denetimi, menü birleştirme destekler.</span><span class="sxs-lookup"><span data-stu-id="99eec-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="99eec-104">MDI formları için de <xref:System.Windows.Forms.ToolStrip> kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="99eec-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="99eec-105">Bu özellik için kapsamlı destek [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99eec-105">There is extensive support for this feature in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="99eec-106">Ayrıca bkz. [izlenecek yol: menü birleştirme ve ToolStrip denetimleri içeren MDI formu oluşturma](http://msdn.microsoft.com/library/ms233676\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="99eec-106">Also see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](http://msdn.microsoft.com/library/ms233676\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99eec-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="99eec-107">Example</span></span>  
 <span data-ttu-id="99eec-108">Aşağıdaki kod örneğinde nasıl kullanılacağı ortaya <xref:System.Windows.Forms.ToolStripPanel> denetimleriyle MDI formu.</span><span class="sxs-lookup"><span data-stu-id="99eec-108">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="99eec-109">Formun alt menüler ile birleştirme menü de destekler.</span><span class="sxs-lookup"><span data-stu-id="99eec-109">The form also supports menu merging with child menus.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="99eec-110">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="99eec-110">Compiling the Code</span></span>  
 <span data-ttu-id="99eec-111">Bu kod örneği gerektirir:</span><span class="sxs-lookup"><span data-stu-id="99eec-111">This code example requires:</span></span>  
  
-   <span data-ttu-id="99eec-112">System.Drawing ve System.Windows.Forms derlemelerine başvurular.</span><span class="sxs-lookup"><span data-stu-id="99eec-112">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="99eec-113">Bu örnek için komut satırından oluşturma hakkında bilgi için [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] veya [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], bkz: [komut satırından derleme](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [komut satırı derleme ile csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="99eec-113">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="99eec-114">Bu örnek ayrıca oluşturmak [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] yeni bir proje kodunu yapıştırma tarafından.</span><span class="sxs-lookup"><span data-stu-id="99eec-114">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="99eec-115">Ayrıca sssee [nasıl yapılır: derleme ve çalıştırma bir tam Windows Forms kod örneği kullanarak Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="99eec-115">Also sssee [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99eec-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="99eec-116">See Also</span></span>  
 [<span data-ttu-id="99eec-117">ToolStrip denetimi</span><span class="sxs-lookup"><span data-stu-id="99eec-117">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)