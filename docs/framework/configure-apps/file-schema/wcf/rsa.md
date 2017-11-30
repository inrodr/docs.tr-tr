---
title: '&lt;RSA&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ab07508c4cab32cb2a60d37af368c345a0f12d88
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltrsagt"></a><span data-ttu-id="c199c-102">&lt;RSA&gt;</span><span class="sxs-lookup"><span data-stu-id="c199c-102">&lt;rsa&gt;</span></span>
<span data-ttu-id="c199c-103">Bu kimliğe sahip bir uç nokta bağlandığı güvenli bir WCF istemcisi, sunucu tarafından sunulan talepler bu kimliği oluşturmak için kullanılan RSA ortak anahtarı içeren bir talep içeren doğrular.</span><span class="sxs-lookup"><span data-stu-id="c199c-103">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="c199c-104">\<Kimliği ></span><span class="sxs-lookup"><span data-stu-id="c199c-104">\<identity></span></span>  
<span data-ttu-id="c199c-105">\<RSA ></span><span class="sxs-lookup"><span data-stu-id="c199c-105">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c199c-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c199c-106">Syntax</span></span>  
  
```xml  
<rsa value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c199c-107">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="c199c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c199c-108">Öznitelikler, alt öğelerini ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır</span><span class="sxs-lookup"><span data-stu-id="c199c-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c199c-109">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="c199c-109">Attributes</span></span>  
  
|<span data-ttu-id="c199c-110">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="c199c-110">Attribute</span></span>|<span data-ttu-id="c199c-111">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c199c-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c199c-112">value</span><span class="sxs-lookup"><span data-stu-id="c199c-112">value</span></span>|<span data-ttu-id="c199c-113">İsteğe bağlı dize.</span><span class="sxs-lookup"><span data-stu-id="c199c-113">Optional String.</span></span> <span data-ttu-id="c199c-114">İstemcide ile Karşılaştırılacak RSA ortak anahtar değeri.</span><span class="sxs-lookup"><span data-stu-id="c199c-114">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c199c-115">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="c199c-115">Child Elements</span></span>  
 <span data-ttu-id="c199c-116">Yok.</span><span class="sxs-lookup"><span data-stu-id="c199c-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c199c-117">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="c199c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c199c-118">Öğe</span><span class="sxs-lookup"><span data-stu-id="c199c-118">Element</span></span>|<span data-ttu-id="c199c-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c199c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c199c-120">\<Kimliği ></span><span class="sxs-lookup"><span data-stu-id="c199c-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="c199c-121">İstemci tarafından doğrulanmasını hizmetin kimliğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="c199c-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c199c-122">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c199c-122">Remarks</span></span>  
 <span data-ttu-id="c199c-123">RSA onay, özellikle kendi RSA anahtarı temel tek bir sertifika kimlik doğrulaması sınırlamanıza olanak sağlar veya kendi RSA anahtar değeri oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="c199c-123">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="c199c-124">RSA anahtar değeri değiştirilirse bu etkinleştirir daha sıkı kimlik doğrulaması hizmeti ödün verme pahasına belirli bir RSA anahtarı artık mevcut istemciler ile çalışıyor.</span><span class="sxs-lookup"><span data-stu-id="c199c-124">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="c199c-125">Bir istemci için bir hizmet doğrulamak için kimlik kullanma hakkında daha fazla bilgi için bkz: [hizmet kimliği ve kimlik doğrulama](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="c199c-125">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c199c-126">Örnek</span><span class="sxs-lookup"><span data-stu-id="c199c-126">Example</span></span>  
 <span data-ttu-id="c199c-127">Aşağıdaki yapılandırma kodunu bir sunucu kimliğini doğrulaması için kullanılan bir X.509 sertifikası ortak anahtar değerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="c199c-127">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>  
  <rsa value = "0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000"/>  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c199c-128">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c199c-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.RsaEndpointIdentity>  
 [<span data-ttu-id="c199c-129">Hizmet kimliği ve kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="c199c-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="c199c-130">\<Kimliği ></span><span class="sxs-lookup"><span data-stu-id="c199c-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)