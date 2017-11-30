---
title: "&lt;eş&gt; &lt;sertifikası&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bf53ec9538834fc6fdb098bff4f78ef1c726ef5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltcertificategt-of-ltpeergt"></a><span data-ttu-id="9fd01-102">&lt;eş&gt; &lt;sertifikası&gt;</span><span class="sxs-lookup"><span data-stu-id="9fd01-102">&lt;certificate&gt; of &lt;peer&gt;</span></span>
<span data-ttu-id="9fd01-103">Bir eş tarafından kullanılan bir sertifika belirtir.</span><span class="sxs-lookup"><span data-stu-id="9fd01-103">Specifies a certificate used by a peer.</span></span>  
  
 <span data-ttu-id="9fd01-104">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9fd01-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9fd01-105">\<davranışları ></span><span class="sxs-lookup"><span data-stu-id="9fd01-105">\<behaviors></span></span>  
<span data-ttu-id="9fd01-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9fd01-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="9fd01-107">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="9fd01-107">\<behavior></span></span>  
<span data-ttu-id="9fd01-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="9fd01-108">\<serviceCredentials></span></span>  
<span data-ttu-id="9fd01-109">\<Eş ></span><span class="sxs-lookup"><span data-stu-id="9fd01-109">\<peer></span></span>  
<span data-ttu-id="9fd01-110">\<Sertifika ></span><span class="sxs-lookup"><span data-stu-id="9fd01-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fd01-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="9fd01-111">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fd01-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="9fd01-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9fd01-113">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="9fd01-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fd01-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="9fd01-114">Attributes</span></span>  
  
|<span data-ttu-id="9fd01-115">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="9fd01-115">Attribute</span></span>|<span data-ttu-id="9fd01-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="9fd01-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="9fd01-117">X.509 sertifika deposunda arama için değer içeren bir dize.</span><span class="sxs-lookup"><span data-stu-id="9fd01-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="9fd01-118">Özniteliğinde bulunan türü belirtilen gereksinimleri karşılaması gerekir `x509FindType`.</span><span class="sxs-lookup"><span data-stu-id="9fd01-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="9fd01-119">Varsayılan boş bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="9fd01-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="9fd01-120">İstemcinin karşı eşin sertifikasını doğrulamak için kullandığı X.509 sertifika depolama konumunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="9fd01-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="9fd01-121">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="9fd01-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9fd01-122">-LocalMachine: Yerel Makine sertifika deposuna.</span><span class="sxs-lookup"><span data-stu-id="9fd01-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="9fd01-123">-Currentuser'a: sertifika deposuna geçerli kullanıcıya atanmış.</span><span class="sxs-lookup"><span data-stu-id="9fd01-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="9fd01-124">LocalMachine varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="9fd01-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="9fd01-125">Açmak için X.509 Sertifika deposu adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="9fd01-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="9fd01-126">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="9fd01-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9fd01-127">-Adres Defteri: Diğer kullanıcılar sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="9fd01-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="9fd01-128">-AuthRoot: sertifika deposunu üçüncü taraf sertifika yetkilileri (CA'lar) için.</span><span class="sxs-lookup"><span data-stu-id="9fd01-128">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="9fd01-129">-CertificateAuthority: Ara sertifika yetkilileri (CA) sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="9fd01-129">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="9fd01-130">-İzin verilmeyen: mağaza iptal edilen sertifikaları için sertifika.</span><span class="sxs-lookup"><span data-stu-id="9fd01-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="9fd01-131">-My: Sertifika deposunda kişisel sertifikalar için.</span><span class="sxs-lookup"><span data-stu-id="9fd01-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="9fd01-132">-Kök: Güvenilen kök sertifika yetkilileri (CA'lar) sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="9fd01-132">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="9fd01-133">-TrustedPeople: Doğrudan-güvenilir kişiler ve kaynaklar sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="9fd01-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="9fd01-134">-TrustedPublisher: Doğrudan-Güvenilen Yayımcılar sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="9fd01-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="9fd01-135">Varsayılan değer My.</span><span class="sxs-lookup"><span data-stu-id="9fd01-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="9fd01-136">Yürütülecek X.509 arama türünü tanımlar.</span><span class="sxs-lookup"><span data-stu-id="9fd01-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="9fd01-137">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="9fd01-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9fd01-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="9fd01-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="9fd01-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="9fd01-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="9fd01-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="9fd01-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="9fd01-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="9fd01-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="9fd01-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="9fd01-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="9fd01-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="9fd01-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="9fd01-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="9fd01-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="9fd01-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="9fd01-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="9fd01-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="9fd01-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="9fd01-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="9fd01-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="9fd01-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="9fd01-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="9fd01-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="9fd01-149">-   FindByExtension</span></span><br /><span data-ttu-id="9fd01-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="9fd01-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="9fd01-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="9fd01-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="9fd01-152">İçinde yer alan türü `findValue` özniteliği belirtilen gereksinimleri karşılaması gerekir `X509FindType`.</span><span class="sxs-lookup"><span data-stu-id="9fd01-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="9fd01-153">FindBySubjectDistinguishedName varsayılan değerdir.</span><span class="sxs-lookup"><span data-stu-id="9fd01-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9fd01-154">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="9fd01-154">Child Elements</span></span>  
 <span data-ttu-id="9fd01-155">Yok.</span><span class="sxs-lookup"><span data-stu-id="9fd01-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9fd01-156">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="9fd01-156">Parent Elements</span></span>  
  
|<span data-ttu-id="9fd01-157">Öğe</span><span class="sxs-lookup"><span data-stu-id="9fd01-157">Element</span></span>|<span data-ttu-id="9fd01-158">Açıklama</span><span class="sxs-lookup"><span data-stu-id="9fd01-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fd01-159">\<Eş ></span><span class="sxs-lookup"><span data-stu-id="9fd01-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="9fd01-160">Eş düğüm için geçerli kimlik bilgilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="9fd01-160">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fd01-161">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9fd01-161">Remarks</span></span>  
 <span data-ttu-id="9fd01-162">Bu yapılandırma öğesi içeren bir `X509Certificate2` eş kafes Komşuları doğrulanırken kullanılan örnek.</span><span class="sxs-lookup"><span data-stu-id="9fd01-162">This configuration element contains an `X509Certificate2` instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="9fd01-163">Eşler arası programlama hakkında daha fazla bilgi için bkz: [eşler arası ağ](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="9fd01-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fd01-164">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9fd01-164">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="9fd01-165">Sertifikalar ile çalışma</span><span class="sxs-lookup"><span data-stu-id="9fd01-165">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="9fd01-166">Eşler arası ağ</span><span class="sxs-lookup"><span data-stu-id="9fd01-166">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="9fd01-167">Eş kanal ileti kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="9fd01-167">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="9fd01-168">Eş kanal özel kimlik doğrulama</span><span class="sxs-lookup"><span data-stu-id="9fd01-168">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="9fd01-169">Eş kanalı uygulamalarını güvenli hale getirme</span><span class="sxs-lookup"><span data-stu-id="9fd01-169">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="9fd01-170">Hizmetler ve istemcileri güvenli hale getirme</span><span class="sxs-lookup"><span data-stu-id="9fd01-170">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)