---
title: '&lt;netHttpBinding&gt; &lt;taşıma&gt;'
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 092072df2b88c59c7744a694175ce5ddf39cf79b
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2018
ms.locfileid: "48842651"
---
# <a name="lttransportgt-of-ltnethttpbindinggt"></a>&lt;netHttpBinding&gt; &lt;taşıma&gt;
HTTP taşıma için kimlik doğrulama parametrelerini denetleyen özellikleri tanımlar.  
  
\<system.serviceModel>  
\<bağlamaları >  
\<netHttpBinding>  
\<bağlama >  
\<Güvenlik >  
\<taşıma >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml
<netHttpBinding>  
  <binding>  
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string">  
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"  
                                  protectionScenario="TransportSelected|TrustedProxy">  
          <customServiceNames></customServiceNames>  
        </extendedProtectionPolicy>  
      </transport>  
    </security>  
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|clientCredentialType|-HTTP kimlik doğrulaması kullanarak istemci kimlik doğrulaması yapılırken kullanılacak kimlik bilgisi türünü belirtir.  Varsayılan, `None` değeridir. Bu öznitelik türünde <xref:System.ServiceModel.HttpClientCredentialType>.|  
|proxyCredentialType|-Gelen istemci kimlik doğrulaması Ara sunucu kullanarak HTTP üzerinden bir etki alanı içinde gerçekleştirirken kullanılacak kimlik bilgisi türünü belirtir. Bu özniteliği yalnızca uygun olduğunda, `mode` üst öğenin özniteliğini `security` öğesi `Transport` veya `TransportCredentialsOnly`. Bu öznitelik türünde <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|Bölge|HTTP kimlik doğrulama şemasının Özet veya temel kimlik doğrulaması için kullanılan ölge belirten bir dize. Varsayılan değer boş bir dizedir.|  
|policyEnforcement|Bu sabit listesi ne zaman belirtir <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> zorlanmalıdır.<br /><br /> 1.  Hiçbir zaman – hiçbir zaman ilkenin uygulanıp (genişletilmiş koruma devre dışı).<br />2.  Yalnızca istemci genişletilmiş koruma destekliyorsa WhenSupported – ilke zorunlu tutulur.<br />3.  Her zaman – ilke her zaman uygulanmaz. Genişletilmiş Koruma desteklemeyen istemciler kimlik doğrulaması başarısız olur.|  
|protectionScenario|Bu numaralandırma, ilke tarafından zorunlu koruma senaryosu belirtir.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType özniteliği  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|Yok.|İleti aktarımı sırasında sağlanmaz.|  
|Temel|Temel kimlik doğrulaması belirtir.|  
|Özet|Özet kimlik doğrulaması belirtir.|  
|NTLM|Mümkün olduğunda ve Windows kimlik doğrulaması başarısız olursa, NTLM kimlik doğrulaması belirtir.|  
|Windows|Windows tümleşik kimlik doğrulaması belirtir.|  
  
## <a name="proxycredentialtype-attribute"></a>proxyCredentialType özniteliği  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|Yok.|-Sıradaki iletiler, aktarım sırasında sağlanmaz.|  
|Temel|RFC 2617 – HTTP kimlik doğrulaması tarafından tanımlandığı gibi temel kimlik doğrulaması belirtir: temel ve Özet kimlik doğrulaması.|  
|Özet|Özet kimlik doğrulaması RFC 2617 – HTTP kimlik doğrulaması tarafından tanımlanan belirtir: temel ve Özet kimlik doğrulaması.|  
|NTLM|Mümkün olduğunda ve Windows kimlik doğrulaması başarısız olursa, NTLM kimlik doğrulaması belirtir.|  
|Windows|Windows tümleşik kimlik doğrulaması belirtir.|  
|Sertifika|Bir sertifika kullanarak bir istemci kimlik doğrulaması gerçekleştirir. Bu seçenek yalnızca çalışır `Mode` üst öğenin özniteliğini `security` öğe taşıma imkanı kullanılarak ayarlanır ve TransportCredentialOnly için ayarlanmışsa çalışmaz.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<Güvenlik >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|İçin güvenlik özelliklerini tanımlar [ \<netHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, basit bağlama ile SSL Aktarım güvenliği kullanımını gösterir. Varsayılan olarak, HTTP iletişimi için temel bağlamayı destekler.  
  
```xml
<system.serviceModel>  
  <services>  
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <endpoint address=""  
                binding="netHttpBinding"  
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
    <netHttpBinding>  
      <!-- Configure basicHttpBinding with Transport security -- >  
      <!-- mode and clientCredentialType set to None.-->  
      <binding name="Binding1">  
        <security mode="Transport">  
          <transport clientCredentialType="None"  
                     proxyCredentialType="None">  
            <extendedProtectionPolicy policyEnforcement="WhenSupported"  
                                      protectionScenario="TransportSelected">  
              <customServiceNames></customServiceNames>  
            </extendedProtectionPolicy>
          </transport> 
        </security>  
      </binding>  
    </netHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport><xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 [Hizmet ve İstemcileri Güvenli Hale Getirme](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Bağlamalar](../../../../../docs/framework/wcf/bindings.md)  
 [Sistem Tarafından Sağlanan Bağlamaları Yapılandırma](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Hizmetler ve İstemcileri Yapılandırmak için Bağlamaları Kullanma](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [\<bağlama >](../../../../../docs/framework/misc/binding.md)
