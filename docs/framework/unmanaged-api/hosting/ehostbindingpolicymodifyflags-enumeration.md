---
title: EHostBindingPolicyModifyFlags Numaralandırması
ms.date: 03/30/2017
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fa8cc15f77ff59e3d3c570341d9bba70cf1e953
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431720"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a>EHostBindingPolicyModifyFlags Numaralandırması
Ortak dil çalışma zamanı (CLR) bir hedef derleme kaynak derlemesinden İlkesi değişiklikleri uygularken gerçekleştirmesi gereken yeniden yönlendirme türü belirtmek ana bilgisayar tanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|CLR ilke değerleri bu hedef derlemenin üzerine kaynak derlemenin zincirine bağlı olduğunu belirtir.|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|CLR varsayılan eylem gerçekleştireceğini belirtir.|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|CLR en yüksek değerleri hedef derlemenin ilke değerleri ayarlamak belirtir.|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|CLR İlkesi değerleri hedef derlemenin kaynak assembly olanlar değiştirir olduğunu belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 [Iclrhostbindingpolicymanager::modifyapplicationpolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) yöntemi türünde bir parametre alan `EHostBindingPolicyModifyFlags`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** MSCorEE.dll  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ICLRHostBindingPolicyManager Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [Barındırma Sabit Listeleri](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
