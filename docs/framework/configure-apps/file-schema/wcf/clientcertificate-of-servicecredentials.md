---
title: "&lt;serviceCredentials&gt; için &lt;clientCertificate&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
caps.latest.revision: "19"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bc4b3251a85a6926c93f418c154b4eabbd44092f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientcertificategt-of-ltservicecredentialsgt"></a><span data-ttu-id="7806c-102">&lt;serviceCredentials&gt; için &lt;clientCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="7806c-102">&lt;clientCertificate&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="7806c-103">Oturum açın ve bir istemci forma çift yönlü iletişim düzeni hizmetinde iletileri şifrelemek için kullanılan bir X.509 sertifikası tanımlar.</span><span class="sxs-lookup"><span data-stu-id="7806c-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
 <span data-ttu-id="7806c-104">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7806c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7806c-105">\<davranışları ></span><span class="sxs-lookup"><span data-stu-id="7806c-105">\<behaviors></span></span>  
<span data-ttu-id="7806c-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7806c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="7806c-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7806c-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="7806c-108">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="7806c-108">\<behavior></span></span>  
<span data-ttu-id="7806c-109">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="7806c-109">\<serviceCredentials></span></span>  
<span data-ttu-id="7806c-110">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="7806c-110">\<clientCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7806c-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="7806c-111">Syntax</span></span>  
  
```xml  
<clientCertificate>  
 <certificate/>  
 <authentication/>  
</clientCertificate>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7806c-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="7806c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7806c-113">Öznitelikler, alt öğelerini ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır</span><span class="sxs-lookup"><span data-stu-id="7806c-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7806c-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="7806c-114">Attributes</span></span>  
 <span data-ttu-id="7806c-115">Yok.</span><span class="sxs-lookup"><span data-stu-id="7806c-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7806c-116">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="7806c-116">Child Elements</span></span>  
  
|<span data-ttu-id="7806c-117">Öğe</span><span class="sxs-lookup"><span data-stu-id="7806c-117">Element</span></span>|<span data-ttu-id="7806c-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7806c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7806c-119">\<kimlik doğrulama ></span><span class="sxs-lookup"><span data-stu-id="7806c-119">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)|<span data-ttu-id="7806c-120">İstemci sertifikası kimlik doğrulama seçeneklerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="7806c-120">Specifies authentication options for the client certificate.</span></span>|  
|[<span data-ttu-id="7806c-121">\<Sertifika ></span><span class="sxs-lookup"><span data-stu-id="7806c-121">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md)|<span data-ttu-id="7806c-122">Kullanılacak sertifikayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="7806c-122">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7806c-123">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="7806c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7806c-124">Öğe</span><span class="sxs-lookup"><span data-stu-id="7806c-124">Element</span></span>|<span data-ttu-id="7806c-125">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7806c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7806c-126">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="7806c-126">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="7806c-127">Hizmet kimlik doğrulaması kullanmak için kimlik bilgilerini belirtir ve istemci kimlik doğrulaması ilgili ayarları.</span><span class="sxs-lookup"><span data-stu-id="7806c-127">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7806c-128">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7806c-128">Remarks</span></span>  
 <span data-ttu-id="7806c-129">Bu öğe, hizmeti istemcisi ile önceden güvenli bir şekilde iletişim kurmak için istemci sertifikasını olmalıdır kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7806c-129">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="7806c-130">Bu, çift yönlü iletişim düzeni kullanırken oluşur.</span><span class="sxs-lookup"><span data-stu-id="7806c-130">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="7806c-131">Daha tipik istek/yanıt desende istemci sertifikasını istemciye yanıt imzalamak ve şifrelemek için hizmet kullanır istekte içerir.</span><span class="sxs-lookup"><span data-stu-id="7806c-131">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="7806c-132">Çift yönlü iletişimi düzeninde ancak, hizmeti istemciden gelen istekte yok ve bu nedenle önceden istemciye ileti güvenliğini sağlamak için istemci sertifikasını gerekiyor.</span><span class="sxs-lookup"><span data-stu-id="7806c-132">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="7806c-133">Bu nedenle bir bant dışı anlaşma istemci sertifikasını elde etmek ve bu öğe kullanarak sertifikayı belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="7806c-133">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="7806c-134">Çift yönlü hizmetler hakkında daha fazla bilgi için bkz: [nasıl yapılır: çift yönlü sözleşme oluşturma](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="7806c-134">For more information about duplex services, see [How to: Create a Duplex Contract](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="7806c-135">Bu öğe kümesindeki sertifika ile yapılandırılmış bağlamaları için istemciye iletileri şifrelemek için kullanılan `MutualCertificateDuplex` ileti güvenlik kimlik doğrulama modu.</span><span class="sxs-lookup"><span data-stu-id="7806c-135">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7806c-136">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7806c-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>  
 [<span data-ttu-id="7806c-137">Nasıl yapılır: çift yönlü sözleşme oluşturma</span><span class="sxs-lookup"><span data-stu-id="7806c-137">How to: Create a Duplex Contract</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [<span data-ttu-id="7806c-138">Güvenlik davranışları</span><span class="sxs-lookup"><span data-stu-id="7806c-138">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="7806c-139">Sertifikalar ile çalışma</span><span class="sxs-lookup"><span data-stu-id="7806c-139">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)