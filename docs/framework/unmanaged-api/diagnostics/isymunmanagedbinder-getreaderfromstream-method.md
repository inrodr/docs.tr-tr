---
title: ISymUnmanagedBinder::GetReaderFromStream Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder.GetReaderFromStream
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 96bd12b69b84537415ddf2e0ae992ec179f32493
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="a26c2-102">ISymUnmanagedBinder::GetReaderFromStream Metodu</span><span class="sxs-lookup"><span data-stu-id="a26c2-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="a26c2-103">Bir meta veri arabirimi ve sembol deposu içeren bir akışı doğru döndürür <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> hata ayıklama okuma yapısı belirtilen simge Mağazası'ndan simgeler.</span><span class="sxs-lookup"><span data-stu-id="a26c2-103">Given a metadata interface and a stream that contains the symbol store, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a26c2-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a26c2-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a26c2-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="a26c2-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="a26c2-106">[in] Meta veri alma arayüzü için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="a26c2-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="a26c2-107">[in] Sembol deposu içeren akışı için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="a26c2-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="a26c2-108">[out] Ayarlanmış bir işaretçi döndürülen için <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="a26c2-108">[out] A pointer that is set to the returned <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a26c2-109">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="a26c2-109">Return Value</span></span>  
 <span data-ttu-id="a26c2-110">Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="a26c2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a26c2-111">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="a26c2-111">Requirements</span></span>  
 <span data-ttu-id="a26c2-112">**Başlık:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a26c2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a26c2-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a26c2-113">See Also</span></span>  
 [<span data-ttu-id="a26c2-114">Isymunmanagedbinder arabirimi</span><span class="sxs-lookup"><span data-stu-id="a26c2-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)