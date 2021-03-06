---
title: '&lt;tokenReplayDetection&gt;'
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: bd2272cb83dc0183d5008cfa178e11783f51ca2d
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48261061"
---
# <a name="lttokenreplaydetectiongt"></a>&lt;tokenReplayDetection&gt;
Belirteç yeniden yürütme algılaması sağlar ve belirteçleri sona erme süresini belirtir.  
  
 \<system.identityModel>  
\<identityConfiguration >  
\<tokenReplayDetection >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a>Tür  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|Etkin|Belirteç yeniden yürütme algılaması etkin olup olmadığını belirten bir değeri; belirteç etkinleştirmek için "true" algılama yeniden yürütün.|  
|expirationPeriod|A <xref:System.TimeSpan> öğenin süresi doldu ve önbellekten kaldırıldı olarak kabul edilmeden önce zaman maksimum miktarını belirtir.  Belirtme hakkında daha fazla bilgi için <xref:System.TimeSpan> değerleri, görmek [Timespan değerleri](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Hizmet düzeyi kimlik ayarlarını belirtir.|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Güvenlik topluluğu için yapılandırma, belirteç işleyicileri sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 A `<tokenReplayDetection>` öğesi altında hizmet düzeyinde belirtilebilir `<identityConfiguration>` öğesi veya güvenlik belirteci işleyicisi koleksiyon düzeyi altında `<securityTokenHandlerConfiguration>` öğesi. Bir belirteci işleyicisi koleksiyon ayarlarını hizmette belirtilen geçersiz kılar.  
  
 Belirteç yeniden yürütme önbellek türü tarafından belirtilen [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) öğesi.
