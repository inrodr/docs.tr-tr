---
title: '&lt;localIssuer&gt;'
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: cb5afb0e73ad0a07ea43f06915f4e477d7f8f985
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2018
ms.locfileid: "48841559"
---
# <a name="ltlocalissuergt"></a>&lt;localIssuer&gt;
Bir güvenlik belirteci almak için kullanılacak yerel verenin bağlamasını ve adresini belirtir.  
  
 \<system.ServiceModel>  
\<davranışlar >  
endpointBehaviors bölümü  
\<davranışı >  
\<clientCredentials >  
\<IssuedToken >  
\<localIssuer >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|adres|Zorunlu dize. Yerel dağıtımcının URI belirtir.|  
|bağlama|İsteğe bağlı dize. Sistem tarafından sağlanan bağlamalar biri. Bir liste için bkz. [System-Provided bağlamaları](../../../../../docs/framework/wcf/system-provided-bindings.md).|  
|bindingConfiguration|İsteğe bağlı dize. Yapılandırma dosyasında bulunan bir bağlama yapılandırmasını belirtir.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<Kimliği >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Yerel verici kimlik bilgilerini belirtir.|  
|[\<üstbilgiler >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Yerel verici doğru bir şekilde çözmek için gerekli adres üst bilgileri koleksiyonu. Kullanabileceğiniz `add` anahtar sözcüğü, bir üst bilgisi bu koleksiyona eklenecek.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<IssuedToken >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Bir hizmete istemcinin kimliğini doğrulamak için kullanılan özel simgeyi belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Verilen bir belirteç bir güvenlik belirteci hizmeti (STS) öğesinden alırken, istemci uygulaması yapılandırılmalıdır adresi ve bir STS ile iletişim kurmak için kullanılacak bağlama. Zaman <xref:System.ServiceModel.WSFederationHttpBinding> URL veya güvenlik belirteci hizmeti için bir federe bağlama veren adresini olduğunda sağlamaz `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` veya `null`, istemcinin Windows Communication Foundation (WCF) kanal tarafındanbelirtilendeğerlerikullanan`address`ve `binding` verilen belirteç almak için bir STS ile iletişim kurmak için. Yerel yayımlayan yapılandırma hakkında daha fazla bilgi için bkz. [nasıl yapılır: yerel yayımlayan yapılandırma](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kümeleri `address`, `binding`, ve `bindingConfiguration` özniteliklerinin bir `localIssuer` öğesi.  
  
```xml  
<system.serviceModel>  
 <behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <issuedToken cacheIssuedTokens="false"   
                 defaultKeyEntropyMode="ClientEntropy">  
     <localIssuer address="net.tcp://cohowinery/tokens"   
                  binding="netTcpBinding"  
                  bindingConfiguration="myTcpBindingConfig" />  
    </issuedToken>  
   </clientCredentials>  
  </behavior>  
  </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [Güvenlik Davranışları](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Nasıl yapılır: Yerel Yayımlayan Yapılandırma](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [Kimlik Doğrulama ile Hizmet Kimliği](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Güvenlik Davranışları](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Federasyon ve Verilen Belirteçler](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Hizmet ve İstemcileri Güvenli Hale Getirme](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [İstemcileri Güvenli Hale Getirme](../../../../../docs/framework/wcf/securing-clients.md)  
 [Nasıl yapılır: Federe İstemci Oluşturma](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Federasyon ve Verilen Belirteçler](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
