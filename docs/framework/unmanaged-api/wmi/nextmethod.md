---
title: NextMethod işlevi (yönetilmeyen API Başvurusu)
description: Bir numaralandırma sonraki yöntem NextMethod işlevi alır.
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d019c67849197cd24171ff607e60e9f08d5ff70
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "44040882"
---
# <a name="nextmethod-function"></a>NextMethod işlevi
Sonraki yöntem çağrısı ile başlayan bir numaralandırma alır [BeginMethodEnumeration](beginmethodenumeration.md).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a>Parametreler

`vFunc`  
[in] Bu parametre kullanılmaz.

`ptr`  
[in] Bir işaretçi bir [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) örneği.

`lFlags`  
[in] Ayrılmış. Bu parametre 0 olmalıdır.

`pName`  
[out] İşaret eden bir işaretçi `null` çağrıdan önce. İşlevi döndüğünde, yeni bir adres `BSTR` içeren yöntem adı. 

`ppSignatureIn`  
[out] Bir işaretçi alır bir işaretçi bir [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) içeren `in` yönteminin parametreleri. 

`ppSignatureOut`  
[out] Bir işaretçi alır bir işaretçi bir [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) içeren `out` yönteminin parametreleri. 

## <a name="return-value"></a>Dönüş değeri

Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:

|Sabit  |Değer  |Açıklama  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | Hiçbir çağrı oluştu [ `BeginEnumeration` ](beginenumeration.md) işlevi. |
| `WBEM_S_NO_ERROR` | 0 | İşlev çağrısı başarılı oldu.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Sabit listede daha fazla özellik vardır. |
  
## <a name="remarks"></a>Açıklamalar

Bu işlev bir çağrı sarılır [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) yöntemi.

Çağıranın çağırarak sabit listesi sırası başlar [BeginMethodEnumeration](beginmethodenumeration.md) işlev ve işlev dönene kadar sonra [NextMethod] işlevini çağırır `WBEM_S_NO_MORE_DATA`. İsteğe bağlı olarak, çağıran çağırarak sırası tamamlandıktan [EndMethodEnumeration](endmethodenumeration.md). Çağıranın numaralandırma erken çağırarak sonlandırabilir [EndMethodEnumeration](endmethodenumeration.md) dilediğiniz zaman.

## <a name="example"></a>Örnek

C++ örnek için bkz: [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) yöntemi.

## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** WMINet_Utils.idl  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
[WMI ve performans sayaçları (yönetilmeyen API Başvurusu)](index.md)
