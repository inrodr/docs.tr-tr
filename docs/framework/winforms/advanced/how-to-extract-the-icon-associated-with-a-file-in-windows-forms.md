---
title: "Nasıl yapılır: Windows Formlarında Bir Dosyayla İlişkili Simgeyi Çıkarma"
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
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 69999e598bfc57278c1793d3cc82e0055026267d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="d2b7d-102">Nasıl yapılır: Windows Formlarında Bir Dosyayla İlişkili Simgeyi Çıkarma</span><span class="sxs-lookup"><span data-stu-id="d2b7d-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="d2b7d-103">Çok sayıda dosya ilişkili dosya türü için görsel bir sunumdur sağlamak simgeler katıştırılmış.</span><span class="sxs-lookup"><span data-stu-id="d2b7d-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="d2b7d-104">Örneğin, Microsoft Word belgelerini Word belgeleri olarak belirten bir simge içerir.</span><span class="sxs-lookup"><span data-stu-id="d2b7d-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="d2b7d-105">Dosyaları bir liste denetimini veya tablo denetim görüntülerken, her dosya adının yanındaki dosya türünü temsil eden simgeyi görüntülemek isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d2b7d-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="d2b7d-106">Kolayca kullanarak bunu yapabilirsiniz <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="d2b7d-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2b7d-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="d2b7d-107">Example</span></span>  
 <span data-ttu-id="d2b7d-108">Aşağıdaki kod örneğinde bir dosyayla ilişkili simgeyi çıkarma ve dosya adını ve ilişkili simgesini görüntülemek nasıl gösteren bir <xref:System.Windows.Forms.ListView> denetim.</span><span class="sxs-lookup"><span data-stu-id="d2b7d-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d2b7d-109">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="d2b7d-109">Compiling the Code</span></span>  
 <span data-ttu-id="d2b7d-110">Örnek derlemek için:</span><span class="sxs-lookup"><span data-stu-id="d2b7d-110">To compile the example:</span></span>  
  
-   <span data-ttu-id="d2b7d-111">Önceki kod bir Windows formu, arama yapıştırın ve `ExtractAssociatedIconExample` formun Oluşturucusu yönteminden veya <xref:System.Windows.Forms.Form.Load> olay işleme yöntemi.</span><span class="sxs-lookup"><span data-stu-id="d2b7d-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="d2b7d-112">Formunuz alındığından emin olmak gerekir <xref:System.IO> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="d2b7d-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b7d-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d2b7d-113">See Also</span></span>  
 [<span data-ttu-id="d2b7d-114">Resimler, bit eşlemler ve meta dosyaları</span><span class="sxs-lookup"><span data-stu-id="d2b7d-114">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="d2b7d-115">ListView denetimi</span><span class="sxs-lookup"><span data-stu-id="d2b7d-115">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)