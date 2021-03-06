---
title: Özel Bağlama Üzerinden Meta Veri Yayımlama ve Alma
ms.date: 03/30/2017
ms.assetid: 904e11b4-d90e-45c6-9ee5-c3472c90008c
ms.openlocfilehash: 528f7662ee3a1f956427e5e42f540816f55027f8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803890"
---
# <a name="publishing-and-retrieving-metadata-over-a-custom-binding"></a>Özel Bağlama Üzerinden Meta Veri Yayımlama ve Alma
<xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> Bir hizmet için meta veri uç noktası eklemek için destek sağlar. Bu meta veri uç noktalarını bir URL HTTP GET isteklerine yanıt vermesini sağlayabilirsiniz bir `?wsdl` querystring ve WS-MetadataExchange (MEX) belirtiminde tanımlanan WS aktarma GET istekleri. MEX uç noktaları uygulamak <xref:System.ServiceModel.Description.IMetadataExchange?displayProperty=nameWithType> sözleşme.  
  
## <a name="publishing-metadata-over-a-custom-binding"></a>Özel bağlama üzerinden meta verileri yayımlama  
 Meta veri uç noktalarını alma HTTPS ve HTTP GET meta veri uç noktaları ayarlanarak etkinleştirilir <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A?displayProperty=nameWithType> veya <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A?displayProperty=nameWithType> özelliklerine `true`. Bu uç noktalar için olan bağlamaları yapılandırılamaz.  
  
 <xref:System.ServiceModel.Description.IMetadataExchange> Sözleşme, ancak kullanılabilir özel bağlamalar kullanan çünkü dahil olmak üzere herhangi bir uç nokta ile <xref:System.ServiceModel.Description.IMetadataExchange> uç noktaları için başka bir Windows Communication Foundation (WCF) hizmetini endpoint aynıdır. Sistem tarafından sağlanan bir bağlamayı yapılandırmasını değiştirmek nasıl bilmiyorsanız veya nasıl yapılandırılacağı bildiğiniz bir <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>, bağlama ile kullanmak için yapılandırabilirsiniz sonra bir <xref:System.ServiceModel.Description.IMetadataExchange> uç noktası.  
  
## <a name="retrieving-metadata-over-a-custom-binding"></a>Özel bağlama üzerinden meta verileri alma  
 Standart HTTP veya HTTPS GET isteklerini kullanarak HTTP Get hem de HTTPS alma meta veri uç noktalarından meta verileri alınabilir.  
  
 MEX meta veri uç noktasından meta verilerini almak için genellikle WCF tarafından desteklenen standart MEX bağlamaları birini kullanabilirsiniz. Daha fazla bilgi için bkz. <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>. <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> Türü ve Svcutil.exe Aracı'nı otomatik olarak aşağıdakilerden birini seçin belirtilen meta veri uç noktasının adresini temel alan bu standart MEX bağlar.  
  
 MEX meta veri uç noktasının standart MEX bağlamaları olandan farklı bir bağlama kullanıyorsa, bağlama tarafından kullanılan yapılandırabilirsiniz <xref:System.ServiceModel.Description.MetadataExchangeClient> kod kullanarak veya göre sağlayan bir <xref:System.ServiceModel.Description.IMetadataExchange> istemci uç nokta yapılandırması. Svcutil.exe Aracı'nı otomatik olarak yükler, yapılandırma dosyasından bir <xref:System.ServiceModel.Description.IMetadataExchange> URI düzeni meta veri uç noktası adresi için aynı ada sahip istemci uç nokta yapılandırması.  
  
## <a name="security"></a>Güvenlik  
 Özel bağlama üzerinden meta veri yayımlama sırasında bağlama meta verileriniz gerektiren güvenlik desteği sağladığından emin olun. Örneğin, istemci meta verileri elde hakkına sahip olduğundan emin olun ve bilgilerin açığa çıkmasını önlemek için meta verilerinizin ve uygulamanızı daha güvenli yapılandırarak yapabilirsiniz, <xref:System.ServiceModel.Description.IMetadataExchange> kimlik doğrulama ve şifreleme gerektirecek şekilde uç noktası. Örnek [özel güvenli meta veri uç noktasının](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) bu senaryo gösterir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizmetleri Güvenli Hale Getirme](../../../../docs/framework/wcf/securing-services.md)  
 [WS-MetadataExchange Bağlamaları](../../../../docs/framework/wcf/extending/ws-metadataexchange-bindings.md)  
 [Nasıl yapılır: Özel Bir WS-Metadata Exchange Bağlaması Yapılandırma](../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)  
 [Nasıl yapılır: MEX Olmayan Bağlama Üzerinden Meta Verileri Alma](../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
