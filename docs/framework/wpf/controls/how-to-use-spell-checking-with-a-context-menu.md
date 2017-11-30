---
title: "Nasıl yapılır: Bağlam Menüsü ile Yazım Denetimi Kullanma"
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
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 257f343a7fa01e251159797a83e89b533292b6b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a><span data-ttu-id="22a46-102">Nasıl yapılır: Bağlam Menüsü ile Yazım Denetimi Kullanma</span><span class="sxs-lookup"><span data-stu-id="22a46-102">How to: Use Spell Checking with a Context Menu</span></span>
<span data-ttu-id="22a46-103">Varsayılan olarak, bir düzenleme denetiminde yazım etkinleştirdiğinizde ister <xref:System.Windows.Controls.TextBox> veya <xref:System.Windows.Controls.RichTextBox>, bağlam menüsünde yazım denetimi seçenekleri Al.</span><span class="sxs-lookup"><span data-stu-id="22a46-103">By default, when you enable spell checking in an editing control like <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>, you get spell-checking choices in the context menu.</span></span> <span data-ttu-id="22a46-104">Kullanıcı yanlış yazılmış bir sözcük tıkladığında, örneğin, yazım önerileri ya da seçeneğini elde **Tümünü Yoksay**.</span><span class="sxs-lookup"><span data-stu-id="22a46-104">For example, when users right-click a misspelled word, they get a set of spelling suggestions or the option to **Ignore All**.</span></span> <span data-ttu-id="22a46-105">Ancak, kendi özel bağlam menüsü ile varsayılan bağlam menüsünü geçersiz kıldığınızda, bu işlevsellik kaybolur ve bağlam menüsünden Yazım denetimi özelliği yeniden etkinleştirmek için kod yazmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="22a46-105">However, when you override the default context menu with your own custom context menu, this functionality is lost, and you need to write code to reenable the spell-checking feature in the context menu.</span></span> <span data-ttu-id="22a46-106">Aşağıdaki örnek, bunu etkinleştirmek gösterilmiştir bir <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="22a46-106">The following example shows how to enable this on a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22a46-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="22a46-107">Example</span></span>  
 <span data-ttu-id="22a46-108">Aşağıdaki örnekte gösterildiği [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oluşturan bir <xref:System.Windows.Controls.TextBox> bağlam menüsünü uygulamak için kullanılan bazı olaylar ile.</span><span class="sxs-lookup"><span data-stu-id="22a46-108">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that creates a <xref:System.Windows.Controls.TextBox> with some events that are used to implement the context menu.</span></span>  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="22a46-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="22a46-109">Example</span></span>  
 <span data-ttu-id="22a46-110">Aşağıdaki örnek bağlam menüsünü uygulayan kodu gösterir.</span><span class="sxs-lookup"><span data-stu-id="22a46-110">The following example shows the code that implements the context menu.</span></span>  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 <span data-ttu-id="22a46-111">Bunu yapmak için kullanılan kod bir <xref:System.Windows.Controls.RichTextBox> benzer.</span><span class="sxs-lookup"><span data-stu-id="22a46-111">The code used for doing this with a <xref:System.Windows.Controls.RichTextBox> is similar.</span></span> <span data-ttu-id="22a46-112">Geçirilen parametre ana farktır `GetSpellingError` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="22a46-112">The main difference is in the parameter passed to the `GetSpellingError` method.</span></span> <span data-ttu-id="22a46-113">İçin bir <xref:System.Windows.Controls.TextBox>, düzeltme işareti konumunun tamsayı dizinini geçirin:</span><span class="sxs-lookup"><span data-stu-id="22a46-113">For a <xref:System.Windows.Controls.TextBox>, pass the integer index of the caret position:</span></span>  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 <span data-ttu-id="22a46-114">İçin bir <xref:System.Windows.Controls.RichTextBox>, geçirmek <xref:System.Windows.Documents.TextPointer> imleç konumunu belirtir:</span><span class="sxs-lookup"><span data-stu-id="22a46-114">For a <xref:System.Windows.Controls.RichTextBox>, pass the <xref:System.Windows.Documents.TextPointer> that specifies the caret position:</span></span>  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a><span data-ttu-id="22a46-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="22a46-115">See Also</span></span>  
 [<span data-ttu-id="22a46-116">TextBox genel bakış</span><span class="sxs-lookup"><span data-stu-id="22a46-116">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="22a46-117">RichTextBox Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="22a46-117">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [<span data-ttu-id="22a46-118">Yazım denetimi düzenleme bir metin denetimini etkinleştir</span><span class="sxs-lookup"><span data-stu-id="22a46-118">Enable Spell Checking in a Text Editing Control</span></span>](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)  
 [<span data-ttu-id="22a46-119">TextBox ile özel bağlam menüsünü kullanın</span><span class="sxs-lookup"><span data-stu-id="22a46-119">Use a Custom Context Menu with a TextBox</span></span>](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)