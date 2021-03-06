---
title: COR_HEAPOBJECT Yapısı
ms.date: 03/30/2017
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91e64bb2e1c8a7b11fe70024eb4a4fa1717c06e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407355"
---
# <a name="corheapobject-structure"></a>COR_HEAPOBJECT Yapısı
Yönetilen yığında bir nesne hakkında bilgi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`address`|Bellekteki nesne adresi.|  
|`size`|Nesnesinin bayt olarak toplam boyutu.|  
|`type`|A [cor_typeıd](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) nesne türünü temsil eden belirteci.|  
  
## <a name="remarks"></a>Açıklamalar  
 `COR_HEAPOBJECT` örnekleri numaralandırılırken tarafından alınabilir bir [Icordebugheapenum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) çağırarak doldurulur arabirimi nesnesi [Icordebugprocess5::enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) yöntemi.  
  
 A `COR_HEAPOBJECT` örneği yönetilen yığında canlı bir nesneyle ilgili ya da herhangi bir nesne tarafından kökü değil, ancak henüz atık toplayıcısı tarafından toplanan değil bir nesne hakkında bilgi sağlar.  
  
 Daha iyi performans için `COR_HEAPOBJECT.address` alan bir `CORDB_ADDRESS` Icordebugvalue yerine değeri arabirimi hata ayıklama API'si çoğunu kullanılan değer. Verilen nesne adresi için bir Icordebugvalue nesnesi edinmek için iletebilirsiniz `CORDB_ADDRESS` değeri [Icordebugprocess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) yöntemi.  
  
 Daha iyi performans için `COR_HEAPOBJECT.type` alan bir `COR_TYPEID` Icordebugtype yerine değeri arabirimi hata ayıklama API'si çoğunu kullanılan değer. Icordebugtype nesne için belirtilen tür kimliği edinmek için iletebilirsiniz `COR_TYPEID` değeri [Icordebugprocess5::gettypefortypeıd](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) yöntemi.  
  
 `COR_HEAPOBJECT` Yapısı başvuruları sayılan COM arabirimi içerir. Aldığınız varsa bir `COR_HEAPOBJECT` çağırarak numaralandırıcı örneğinden [Icordebugheapenum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) yöntemi, daha sonra başvuru serbest bırakmanız gerekir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama Yapıları](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Hata Ayıklama](../../../../docs/framework/unmanaged-api/debugging/index.md)
