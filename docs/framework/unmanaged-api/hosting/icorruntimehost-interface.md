---
title: ICorRuntimeHost Arabirimi
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost
helpviewer_keywords:
- ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecf6bff10e98ab7f008cfd176f59687f34d89553
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216470"
---
# <a name="icorruntimehost-interface"></a>ICorRuntimeHost Arabirimi
Ortak dil çalışma zamanı (CLR) oluşturma ve uygulama etki alanları, varsayılan etki alanına ve işlemde çalışan tüm etki alanları listelemek için yapılandırma açıkça durdurmak ve başlatmak konak olanak tanıyan yöntemler sağlar.  
  
 .NET Framework sürüm 2. 0'da, bu arabirim tarafından kılınan [Iclrruntimehost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[CloseEnum Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|Bir etki alanı Numaralandırıcı tekrar başlangıcını etki alanı listesi sıfırlar.|  
|[CreateDomain Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|Uygulama etki alanı oluşturur. Çağıranın türü bir arabirim işaretçisi alır <xref:System._AppDomain> türde bir örnek <xref:System.AppDomain?displayProperty=nameWithType>.|  
|[CreateDomainEx Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|Uygulama etki alanı oluşturur. Bu yöntemi çağıran döndürülen ek özellikleri yapılandırmak için Iappdomainsetup örneği geçirilecek sağlar <xref:System._AppDomain> örneği.|  
|[CreateDomainSetup Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|Türü bir arabirim işaretçisi alır `IAppDomainSetup` için bir <xref:System.AppDomainSetup> örneği. `IAppDomainSetup` oluşturulmadan önce bir uygulama etki alanı yönlerini yapılandırmak için yöntemler sağlar.|  
|[CreateEvidence Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|Türü bir arabirim işaretçisi alır <xref:System.Security.Principal.IIdentity>, geçirilecek güvenlik kanıt oluşturmak için ana sağlayan [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) veya [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).|  
|[CreateLogicalThreadState Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|Kullanmayın.|  
|[CurrentDomain Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|Türü bir arabirim işaretçisi alır <xref:System._AppDomain> geçerli iş parçacığı üzerinde yüklü etki alanı temsil eder.|  
|[DeleteLogicalThreadState Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|Kullanmayın.|  
|[EnumDomains Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|Bir numaralandırıcı, geçerli işlem için etki alanlarını alır.|  
|[GetConfiguration Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|CLR geri çağırma yapılandırmasını belirtmek konak izin veren bir nesneyi alır.|  
|[GetDefaultDomain Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|Türü bir arabirim işaretçisi alır <xref:System._AppDomain> , geçerli işlem için varsayılan etki alanı temsil eder.|  
|[LocksHeldByLogicalThread Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|Kullanmayın.|  
|[MapFile Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|Belirtilen dosya belleğe eşler. Bu yöntem artık kullanılmıyor.|  
|[NextDomain Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|Bir arabirim işaretçisi için bir sonraki etki alanına numaralandırmada alır.|  
|[Start Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|CLR'yi başlatır.|  
|[Stop Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|Geçerli işlem için çalışma zamanında kod yürütmeyi durdurur.|  
|[SwitchInLogicalThreadState Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|Kullanmayın.|  
|[SwitchOutLogicalThreadState Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|Kullanmayın.|  
|[UnloadDomain Yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|Belirtilen uygulama etki alanından geçerli işlem kaldırır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:** 1.0, 1.1  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.AppDomain>  
 [Barındırma](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [ICLRRuntimeHost Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [Çalışma zamanı ana bilgisayarları](https://msdn.microsoft.com/library/99d9246a-b994-4fe5-985c-8588d1d59998)  
 [Barındırma Arabirimleri](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [CorRuntimeHost Coclass](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
