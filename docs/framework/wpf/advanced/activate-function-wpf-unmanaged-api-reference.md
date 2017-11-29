---
title: "İşlevini etkinleştirin (WPF yönetilmeyen API Başvurusu)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: Acrivate
api_location: PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 68f3f2a29da11a648b8c635667de6493a04ccd54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="d972a-102">İşlevini etkinleştirin (WPF yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="d972a-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="d972a-103">Bu API Windows Presentation Foundation (WPF) altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.</span><span class="sxs-lookup"><span data-stu-id="d972a-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="d972a-104">Windows Presentation Foundation (WPF) altyapısı tarafından windows yönetimi için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="d972a-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d972a-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="d972a-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d972a-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="d972a-106">Parameters</span></span>  
 <span data-ttu-id="d972a-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="d972a-107">pParameters</span></span>  
 <span data-ttu-id="d972a-108">Pencerenin etkinleştirme parametresi için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="d972a-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="d972a-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="d972a-109">ppInner</span></span>  
 <span data-ttu-id="d972a-110">Bir işaretçi içeren bir tek öğe arabelleği adresini gösteren bir işaretçi bir <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="d972a-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d972a-111">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="d972a-111">Requirements</span></span>  
 <span data-ttu-id="d972a-112">**Platformlar:** bkz [.NET Framework sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d972a-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d972a-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="d972a-113">**DLL:**</span></span>  
  
 <span data-ttu-id="d972a-114">.NET Framework 3.0 ve 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="d972a-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="d972a-115">.NET Framework 4 ve üzeri: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="d972a-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="d972a-116">**.NET framework sürümü:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d972a-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d972a-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d972a-117">See Also</span></span>  
 [<span data-ttu-id="d972a-118">WPF yönetilmeyen API Başvurusu</span><span class="sxs-lookup"><span data-stu-id="d972a-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)