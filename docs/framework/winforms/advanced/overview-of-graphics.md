---
title: "Grafiklere Genel Bakış"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b0a3286cbcaa0eebf59500582a749804b5e1b8ba
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="overview-of-graphics"></a><span data-ttu-id="5e2d8-102">Grafiklere Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="5e2d8-102">Overview of Graphics</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="5e2d8-103">Microsoft Windows işletim sistemi alt formları bir uygulama programlama arabirimi (API) var.</span><span class="sxs-lookup"><span data-stu-id="5e2d8-103"> is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="5e2d8-104">ekranlar ve yazıcılar bilgilerini görüntülemek için sorumludur.</span><span class="sxs-lookup"><span data-stu-id="5e2d8-104"> is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="5e2d8-105">Adından da anlaşılacağı gibi [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] devamıdır [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], önceki Windows sürümlerinde bulunan grafik cihaz arabirimi.</span><span class="sxs-lookup"><span data-stu-id="5e2d8-105">As its name suggests, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is the successor to [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="5e2d8-106">Yönetilen sınıf arabirimi</span><span class="sxs-lookup"><span data-stu-id="5e2d8-106">Managed Class Interface</span></span>  
 <span data-ttu-id="5e2d8-107">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API kümesi ile yönetilen kod dağıtılan sınıfları gösterilir.</span><span class="sxs-lookup"><span data-stu-id="5e2d8-107">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="5e2d8-108">Bu sınıf kümesini olarak adlandırılır *yönetilen sınıf arabirimi* için [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e2d8-108">This set of classes is called the *managed class interface* to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="5e2d8-109">Şu ad alanlarından yönetilen sınıf arabirimi olun:</span><span class="sxs-lookup"><span data-stu-id="5e2d8-109">The following namespaces make up the managed class interface:</span></span>  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="5e2d8-110">Grafik cihaz arabirimi ile gibi [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], belirli görüntü aygıtı ayrıntılar hakkında endişelenmeniz zorunda kalmadan bir ekran veya yazıcı bilgileri görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5e2d8-110">With a Graphics Device Interface, such as [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="5e2d8-111">Programcı tarafından sağlanan yöntemleri çağrılar [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] sınıfları.</span><span class="sxs-lookup"><span data-stu-id="5e2d8-111">The programmer makes calls to methods provided by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span> <span data-ttu-id="5e2d8-112">Bu yöntem, buna karşılık, belirli aygıt sürücüleri için uygun çağrıları yapma.</span><span class="sxs-lookup"><span data-stu-id="5e2d8-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="5e2d8-113">Grafik donanım uygulamadan korunmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="5e2d8-113"> insulates the application from the graphics hardware.</span></span> <span data-ttu-id="5e2d8-114">CİHAZDAN bağımsız uygulamalar oluşturmak için programcı sağlayan bu yalıtımı olur.</span><span class="sxs-lookup"><span data-stu-id="5e2d8-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e2d8-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5e2d8-115">See Also</span></span>  
 [<span data-ttu-id="5e2d8-116">Grafiklere genel bakış</span><span class="sxs-lookup"><span data-stu-id="5e2d8-116">Graphics Overview</span></span>](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)