---
title: "&lt;kimlik&gt; için &lt;certificateReference&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 883ae318e32493013f009f3580ef102e4d39b3e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltcertificatereferencegt-for-ltidentitygt"></a><span data-ttu-id="3b54c-102">&lt;kimlik&gt; için &lt;certificateReference&gt;</span><span class="sxs-lookup"><span data-stu-id="3b54c-102">&lt;certificateReference&gt; for &lt;identity&gt;</span></span>
<span data-ttu-id="3b54c-103">X.509 Sertifika doğrulama ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="3b54c-103">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="3b54c-104">Güvenli [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Bu kimliğe sahip bir uç nokta bağlanan istemci doğrular sunucu tarafından sunulan talepler bu kimliği oluşturmak için kullanılan kimlik talebi içerir.</span><span class="sxs-lookup"><span data-stu-id="3b54c-104">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity verifies that the claims presented by the server contain the identity claim used to construct this identity.</span></span>  
  
 <span data-ttu-id="3b54c-105">\<Kimliği ></span><span class="sxs-lookup"><span data-stu-id="3b54c-105">\<identity></span></span>  
<span data-ttu-id="3b54c-106">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="3b54c-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b54c-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="3b54c-107">Syntax</span></span>  
  
```xml  
<certificateReference   
        findValue="String"   
    isChainIncluded="Boolean"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
  
    storeLocation="LocalMachine/CurrentUser"  
  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
</certificateReference>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b54c-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="3b54c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3b54c-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="3b54c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b54c-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="3b54c-110">Attributes</span></span>  
  
|<span data-ttu-id="3b54c-111">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="3b54c-111">Attribute</span></span>|<span data-ttu-id="3b54c-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="3b54c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3b54c-113">findValue</span><span class="sxs-lookup"><span data-stu-id="3b54c-113">findValue</span></span>|<span data-ttu-id="3b54c-114">X.509 sertifika deposunda aramak için kullanılacak değeri belirtir.</span><span class="sxs-lookup"><span data-stu-id="3b54c-114">Specifies the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="3b54c-115">Bu öznitelikte bulunan türü belirtilen gereksinimleri karşılaması gerekir `X509FindType` değeri.</span><span class="sxs-lookup"><span data-stu-id="3b54c-115">The type contained in this attribute must satisfy the requirements of the specified `X509FindType` value.</span></span> <span data-ttu-id="3b54c-116">Varsayılan boş bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="3b54c-116">The default is an empty string.</span></span>|  
|<span data-ttu-id="3b54c-117">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="3b54c-117">isChainIncluded</span></span>|<span data-ttu-id="3b54c-118">Doğrulama atanarak belirten bir Boole değeri kullanarak bir sertifika zinciri.</span><span class="sxs-lookup"><span data-stu-id="3b54c-118">A Boolean value that specifies if the validation is done using a certificate chain.</span></span>|  
|<span data-ttu-id="3b54c-119">storeLocation</span><span class="sxs-lookup"><span data-stu-id="3b54c-119">storeLocation</span></span>|<span data-ttu-id="3b54c-120">İstemci, sunucu sertifikasını doğrulamak üzere kullanabilir sertifika depolama konumunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="3b54c-120">Specifies the location of the certificate store that the client can use to validate the server’s certificate.</span></span><br /><br /> <span data-ttu-id="3b54c-121">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="3b54c-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3b54c-122">-LocalMachine: sertifika deposu yerel makineye atanmış.</span><span class="sxs-lookup"><span data-stu-id="3b54c-122">-   LocalMachine: The cert store assigned to the local machine.</span></span><br /><span data-ttu-id="3b54c-123">-Currentuser'a: sertifika deposu geçerli kullanıcıya atanmış.</span><span class="sxs-lookup"><span data-stu-id="3b54c-123">-   CurrentUser: The cert store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="3b54c-124">Varsayılan, LocalMachine değerdir.</span><span class="sxs-lookup"><span data-stu-id="3b54c-124">The default value is LocalMachine.</span></span><br /><br /> <span data-ttu-id="3b54c-125">Bu öznitelik türünde <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="3b54c-125">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
|<span data-ttu-id="3b54c-126">storeName</span><span class="sxs-lookup"><span data-stu-id="3b54c-126">storeName</span></span>|<span data-ttu-id="3b54c-127">Açmak için X.509 Sertifika deposu adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="3b54c-127">Specifies the name of the X.509 certificate store to open.</span></span><br /><br /> <span data-ttu-id="3b54c-128">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="3b54c-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3b54c-129">-Adres Defteri: Diğer kullanıcılar sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="3b54c-129">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="3b54c-130">-AuthRoot: sertifika deposunu üçüncü taraf sertifika yetkilileri (CA'lar) için.</span><span class="sxs-lookup"><span data-stu-id="3b54c-130">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="3b54c-131">-CertificateAuthority: Ara CA'lar sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="3b54c-131">-   CertificateAuthority: Certificate store for intermediate CAs.</span></span><br /><span data-ttu-id="3b54c-132">-İzin verilmeyen: mağaza iptal edilen sertifikaları için sertifika.</span><span class="sxs-lookup"><span data-stu-id="3b54c-132">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="3b54c-133">-My: Sertifika deposunda kişisel sertifikalar için.</span><span class="sxs-lookup"><span data-stu-id="3b54c-133">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="3b54c-134">-Kök: Güvenilen kök CA sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="3b54c-134">-   Root: Certificate store for trusted root CAs.</span></span><br /><span data-ttu-id="3b54c-135">-TrustedPeople: Doğrudan güvenilir kişiler ve kaynaklar sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="3b54c-135">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="3b54c-136">-TrustedPublisher: Doğrudan Güvenilen Yayımcılar sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="3b54c-136">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="3b54c-137">Varsayılan değer My.</span><span class="sxs-lookup"><span data-stu-id="3b54c-137">The default value is My.</span></span><br /><br /> <span data-ttu-id="3b54c-138">Bu öznitelik türünde <xref:System.Security.Cryptography.X509Certificates.StoreName>.</span><span class="sxs-lookup"><span data-stu-id="3b54c-138">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreName>.</span></span>|  
|<span data-ttu-id="3b54c-139">X509FindType</span><span class="sxs-lookup"><span data-stu-id="3b54c-139">X509FindType</span></span>|<span data-ttu-id="3b54c-140">Yürütülecek X.509 arama türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="3b54c-140">Specifies the type of X.509 search to be executed.</span></span> <span data-ttu-id="3b54c-141">İçinde yer alan türü `findValue` özniteliği belirtilen X509FindType gereksinimlerini karşılaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="3b54c-141">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="3b54c-142">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="3b54c-142">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3b54c-143">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="3b54c-143">-   FindByThumbPrint</span></span><br /><span data-ttu-id="3b54c-144">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="3b54c-144">-   FindBySubjectName</span></span><br /><span data-ttu-id="3b54c-145">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="3b54c-145">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="3b54c-146">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="3b54c-146">-   FindByIssuerName</span></span><br /><span data-ttu-id="3b54c-147">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="3b54c-147">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="3b54c-148">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="3b54c-148">-   FindBySerialNumber</span></span><br /><span data-ttu-id="3b54c-149">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="3b54c-149">-   FindByTimeValid</span></span><br /><span data-ttu-id="3b54c-150">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="3b54c-150">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="3b54c-151">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="3b54c-151">-   FindByTemplateName</span></span><br /><span data-ttu-id="3b54c-152">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="3b54c-152">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="3b54c-153">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="3b54c-153">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="3b54c-154">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="3b54c-154">-   FindByExtension</span></span><br /><span data-ttu-id="3b54c-155">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="3b54c-155">-   FindByKeyUsage</span></span><br /><span data-ttu-id="3b54c-156">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="3b54c-156">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="3b54c-157">FindBySubjectDistinguishedName varsayılan değerdir.</span><span class="sxs-lookup"><span data-stu-id="3b54c-157">The default value is FindBySubjectDistinguishedName.</span></span><br /><br /> <span data-ttu-id="3b54c-158">Bu öznitelik türünde <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span><span class="sxs-lookup"><span data-stu-id="3b54c-158">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b54c-159">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="3b54c-159">Child Elements</span></span>  
 <span data-ttu-id="3b54c-160">Yok.</span><span class="sxs-lookup"><span data-stu-id="3b54c-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3b54c-161">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="3b54c-161">Parent Elements</span></span>  
  
|<span data-ttu-id="3b54c-162">Öğe</span><span class="sxs-lookup"><span data-stu-id="3b54c-162">Element</span></span>|<span data-ttu-id="3b54c-163">Açıklama</span><span class="sxs-lookup"><span data-stu-id="3b54c-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b54c-164">\<Kimliği ></span><span class="sxs-lookup"><span data-stu-id="3b54c-164">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="3b54c-165">Bir uç nokta onunla ileti değiş tokuşu diğer uç noktaları tarafından kimlik doğrulaması sağlayan ayarları belirtir.</span><span class="sxs-lookup"><span data-stu-id="3b54c-165">Specifies settings that enable the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3b54c-166">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3b54c-166">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>