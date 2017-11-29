---
title: "Nasıl yapılır: Bir ToolStrip Denetimi Dışında Hareket Etmek için SEKME tuşunu etkinleştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5f4583a0381af6f0f85f9c2e2aea1d122f5174ba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a><span data-ttu-id="a5391-102">Nasıl yapılır: Bir ToolStrip Denetimi Dışında Hareket Etmek için SEKME tuşunu etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="a5391-102">How to: Enable the TAB Key to Move Out of a ToolStrip Control</span></span>
<span data-ttu-id="a5391-103">İşyeri dışında taşımak için SEKME tuşuna basın kullanıcıya etkinleştirmek için aşağıdaki yordamı kullanın bir <xref:System.Windows.Forms.ToolStrip> sekme sırasında bir sonraki denetime.</span><span class="sxs-lookup"><span data-stu-id="a5391-103">Use the following procedure to enable the user to press the TAB key to move out of a <xref:System.Windows.Forms.ToolStrip> to the next control in the tab order.</span></span>  
  
 <span data-ttu-id="a5391-104"><xref:System.Windows.Forms.ToolStrip> İçin SEKME tuşunu ve ok tuşları select öğeleri ilk tuşuna kabul <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="a5391-104">The <xref:System.Windows.Forms.ToolStrip> accepts the first press of the TAB key, and the arrow keys select items within the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="a5391-105">Kullanıcı ikinci kez SEKME tuşuna bastığında, kullanıcının bir sonraki denetime sekme sırasını alır.</span><span class="sxs-lookup"><span data-stu-id="a5391-105">When the user presses the TAB key a second time, it takes the user to the next control in the tab order.</span></span>  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a><span data-ttu-id="a5391-106">Kullanıcının bir sonraki denetime dışında bir ToolStrip taşımak için SEKME tuşuna etkinleştirmek için</span><span class="sxs-lookup"><span data-stu-id="a5391-106">To enable the user to press the TAB key to move out of a ToolStrip to the next control</span></span>  
  
-   <span data-ttu-id="a5391-107">Ayarlama <xref:System.Windows.Forms.ToolStrip.TabStop%2A> özelliği <xref:System.Windows.Forms.ToolStrip> için `true`.</span><span class="sxs-lookup"><span data-stu-id="a5391-107">Set the <xref:System.Windows.Forms.ToolStrip.TabStop%2A> property of the <xref:System.Windows.Forms.ToolStrip> to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5391-108">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a5391-108">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.TabStop%2A>  
 [<span data-ttu-id="a5391-109">ToolStrip denetimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="a5391-109">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)