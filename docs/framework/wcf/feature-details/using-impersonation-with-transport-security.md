---
title: "Taşıma Güvenliği ile Kimliğe Bürünme Kullanma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 426df8cb-6337-4262-b2c0-b96c2edf21a9
caps.latest.revision: "12"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 906d45ccba7185e82aed82626a13034f2e97422d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="using-impersonation-with-transport-security"></a><span data-ttu-id="5fd19-102">Taşıma Güvenliği ile Kimliğe Bürünme Kullanma</span><span class="sxs-lookup"><span data-stu-id="5fd19-102">Using Impersonation with Transport Security</span></span>
<span data-ttu-id="5fd19-103">*Kimliğe bürünme* bir sunucu uygulaması istemci kimliği üzerinde gerçekleştirilecek özelliğidir.</span><span class="sxs-lookup"><span data-stu-id="5fd19-103">*Impersonation* is the ability of a server application to take on the identity of the client.</span></span> <span data-ttu-id="5fd19-104">Kimliğe bürünme kaynaklarına erişimi doğrularken kullanmak üzere hizmetlerin yaygındır.</span><span class="sxs-lookup"><span data-stu-id="5fd19-104">It is common for services to use impersonation when validating access to resources.</span></span> <span data-ttu-id="5fd19-105">Bir hizmet hesabı kullanarak sunucu uygulaması çalışır, ancak server istemci bağlantısı kabul ettiğinde, böylece erişim denetimlerini istemcinin kimlik bilgileri kullanılarak gerçekleştirilir, istemci temsil eder.</span><span class="sxs-lookup"><span data-stu-id="5fd19-105">The server application runs using a service account, but when the server accepts a client connection, it impersonates the client so that access checks are performed using the client's credentials.</span></span> <span data-ttu-id="5fd19-106">Taşıma güvenliği bir hem de bu kimlik bilgilerini kullanarak güvenli hale getirmek ve kimlik bilgilerini geçirme mekanizmadır.</span><span class="sxs-lookup"><span data-stu-id="5fd19-106">Transport security is a mechanism both for passing credentials and securing communication using those credentials.</span></span> <span data-ttu-id="5fd19-107">Bu konu, taşıma güveliği kullanarak açıklar [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] kimliğe bürünme özelliği ile.</span><span class="sxs-lookup"><span data-stu-id="5fd19-107">This topic describes using transport security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] with the impersonation feature.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5fd19-108">ileti güvenliği kullanarak kimliğe bürünme bkz [temsilcilik ve kimliğe bürünme](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="5fd19-108"> impersonation using message security, see [Delegation and Impersonation](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).</span></span>  
  
## <a name="five-impersonation-levels"></a><span data-ttu-id="5fd19-109">Beş kimliğe bürünme düzeyi</span><span class="sxs-lookup"><span data-stu-id="5fd19-109">Five Impersonation Levels</span></span>  
 <span data-ttu-id="5fd19-110">Aktarım güvenliği kullanır kimliğe bürünme, beş düzeyde aşağıdaki tabloda açıklandığı gibi.</span><span class="sxs-lookup"><span data-stu-id="5fd19-110">Transport security makes use of five levels of impersonation, as described in the following table.</span></span>  
  
|<span data-ttu-id="5fd19-111">Kimliğe bürünme düzeyi</span><span class="sxs-lookup"><span data-stu-id="5fd19-111">Impersonation level</span></span>|<span data-ttu-id="5fd19-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="5fd19-112">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="5fd19-113">Yok.</span><span class="sxs-lookup"><span data-stu-id="5fd19-113">None</span></span>|<span data-ttu-id="5fd19-114">Sunucu uygulaması istemci kimliğine bürünmek denemez.</span><span class="sxs-lookup"><span data-stu-id="5fd19-114">The server application does not attempt to impersonate the client.</span></span>|  
|<span data-ttu-id="5fd19-115">Anonim</span><span class="sxs-lookup"><span data-stu-id="5fd19-115">Anonymous</span></span>|<span data-ttu-id="5fd19-116">Sunucu uygulaması istemci kimlik bilgilerine yönelik erişim denetimleri gerçekleştirebilirsiniz, ancak istemcinin kimliği hakkında hiçbir bilgi almaz.</span><span class="sxs-lookup"><span data-stu-id="5fd19-116">The server application can perform access checks against the client's credentials, but does not receive any information about the client's identity.</span></span> <span data-ttu-id="5fd19-117">Bu kimliğe bürünme düzeyini, yalnızca adlandırılmış kanallar gibi makine üzerindeki iletişim için anlamlıdır.</span><span class="sxs-lookup"><span data-stu-id="5fd19-117">This impersonation level is meaningful only for on-machine communication, such as named pipes.</span></span> <span data-ttu-id="5fd19-118">Kullanarak `Anonymous` ile uzak bağlantı tanımla kimliğe bürünme düzeyini yükseltir.</span><span class="sxs-lookup"><span data-stu-id="5fd19-118">Using `Anonymous` with a remote connection promotes the impersonation level to Identify.</span></span>|  
|<span data-ttu-id="5fd19-119">Tanımlayın</span><span class="sxs-lookup"><span data-stu-id="5fd19-119">Identify</span></span>|<span data-ttu-id="5fd19-120">Sunucu uygulaması istemci kimliğini bilir ve erişimi doğrulaması istemcinin kimlik bilgilerine karşı gerçekleştirebilirsiniz, ancak istemci alınamıyor.</span><span class="sxs-lookup"><span data-stu-id="5fd19-120">The server application knows the client's identity and can perform access validation against the client's credentials, but cannot impersonate the client.</span></span> <span data-ttu-id="5fd19-121">Tanımlamak SSPI kimlik bilgileri ile kullanılan varsayılan kimliğe bürünme düzeyi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sürece farklı kimliğe bürünme düzeyi belirteç sağlayıcı sağlar.</span><span class="sxs-lookup"><span data-stu-id="5fd19-121">Identify is the default impersonation level used with SSPI credentials in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unless the token provider provides a different impersonation level.</span></span>|  
|<span data-ttu-id="5fd19-122">Impersonate</span><span class="sxs-lookup"><span data-stu-id="5fd19-122">Impersonate</span></span>|<span data-ttu-id="5fd19-123">Sunucu uygulaması, erişim denetimleri yapmak yanı sıra istemci olarak server makinesinde kaynaklara erişebilir.</span><span class="sxs-lookup"><span data-stu-id="5fd19-123">The server application can access resources on the server machine as the client in addition to performing access checks.</span></span> <span data-ttu-id="5fd19-124">Sunucu uygulaması Kimliğine bürünülen belirteci ağ kimlik bilgilerine sahip olmadığından istemcinin kimliğini kullanarak uzak makinelerde kaynaklarına erişemiyor</span><span class="sxs-lookup"><span data-stu-id="5fd19-124">The server application cannot access resources on remote machines using the client's identity because the impersonated token does not have network credentials</span></span>|  
|<span data-ttu-id="5fd19-125">Temsilci</span><span class="sxs-lookup"><span data-stu-id="5fd19-125">Delegate</span></span>|<span data-ttu-id="5fd19-126">Aynı özelliklerine sahip yanı sıra `Impersonate`, temsilci kimliğe bürünme düzeyini ayrıca istemcinin kimliğini kullanarak uzak makinelerde ve başka uygulamalar için kimlik geçirmek için kaynaklara erişmek için sunucu uygulaması sağlar.</span><span class="sxs-lookup"><span data-stu-id="5fd19-126">In addition to having the same capabilities as `Impersonate`, the Delegate impersonation level also enables the server application to access resources on remote machines using the client's identity and to pass the identity to other applications.</span></span><br /><br /> <span data-ttu-id="5fd19-127">**Önemli** sunucusu etki alanı hesabı işaretlenmelidir bu ek özellikleri kullanmak için etki alanı denetleyicisinde temsilci olarak güvenilir.</span><span class="sxs-lookup"><span data-stu-id="5fd19-127">**Important** The server domain account must be marked as trusted for delegation on the domain controller to use these additional features.</span></span> <span data-ttu-id="5fd19-128">Bu kimliğe bürünme düzeyi, gizli olarak işaretlenmiş istemci etki alanı hesaplarıyla kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="5fd19-128">This level of impersonation cannot be used with client domain accounts marked as sensitive.</span></span>|  
  
 <span data-ttu-id="5fd19-129">İle taşıma güvenliği en yaygın olarak kullanılan düzeyleri `Identify` ve `Impersonate`.</span><span class="sxs-lookup"><span data-stu-id="5fd19-129">The levels most commonly used with transport security are `Identify` and `Impersonate`.</span></span> <span data-ttu-id="5fd19-130">Düzeyleri `None` ve `Anonymous` genel kullanım için tavsiye edilmez ve birçok taşımaları bu düzeyleri ile kimlik doğrulaması kullanmayı desteklemez.</span><span class="sxs-lookup"><span data-stu-id="5fd19-130">The levels `None` and `Anonymous` are not recommended for typical use, and many transports do not support using those levels with authentication.</span></span> <span data-ttu-id="5fd19-131">`Delegate` Düzeyi dikkatli kullanılması gereken güçlü bir özelliktir.</span><span class="sxs-lookup"><span data-stu-id="5fd19-131">The `Delegate` level is a powerful feature that should be used with care.</span></span> <span data-ttu-id="5fd19-132">Yalnızca güvenilir sunucu uygulamalarını kimlik bilgileri temsilcisi izni verilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="5fd19-132">Only trusted server applications should be given the permission to delegate credentials.</span></span>  
  
 <span data-ttu-id="5fd19-133">Kimliğe bürünme sırasında kullanılarak `Impersonate` veya `Delegate` düzeyleri gerektiren sunucu uygulamayı `SeImpersonatePrivilege` ayrıcalık.</span><span class="sxs-lookup"><span data-stu-id="5fd19-133">Using impersonation at the `Impersonate` or `Delegate` levels requires the server application to have the `SeImpersonatePrivilege` privilege.</span></span> <span data-ttu-id="5fd19-134">Bir hizmet SID ile (ağ hizmeti, yerel hizmet veya yerel sistem) Administrators grubundaki bir hesabı veya bir hesap üzerinde çalışıyorsa bir uygulama bu ayrıcalık varsayılan olarak sahiptir.</span><span class="sxs-lookup"><span data-stu-id="5fd19-134">An application has this privilege by default if it is running on an account in the Administrators group or on an account with a Service SID (Network Service, Local Service, or Local System).</span></span> <span data-ttu-id="5fd19-135">Kimliğe bürünme, istemci ve sunucu, karşılıklı kimlik doğrulaması gerektirmez.</span><span class="sxs-lookup"><span data-stu-id="5fd19-135">Impersonation does not require mutual authentication of the client and server.</span></span> <span data-ttu-id="5fd19-136">Kimliğe bürünme, NTLM gibi destek bazı kimlik doğrulama şemasını ile karşılıklı kimlik doğrulaması kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="5fd19-136">Some authentication schemes that support impersonation, such as NTLM, cannot be used with mutual authentication.</span></span>  
  
## <a name="transport-specific-issues-with-impersonation"></a><span data-ttu-id="5fd19-137">Kimliğe bürünme aktarım özgü sorunları</span><span class="sxs-lookup"><span data-stu-id="5fd19-137">Transport-Specific Issues with Impersonation</span></span>  
 <span data-ttu-id="5fd19-138">Bir taşıma seçimi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kimliğe bürünme için olası seçeneklerini etkiler.</span><span class="sxs-lookup"><span data-stu-id="5fd19-138">The choice of a transport in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] affects the possible choices for impersonation.</span></span> <span data-ttu-id="5fd19-139">Bu bölümde, standart HTTP etkileyen sorunları açıklar ve kanal aktarımlarda adlı [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fd19-139">This section describes issues affecting the standard HTTP and named pipe transports in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="5fd19-140">Özel taşımaları kimliğe bürünme için destek kendi kısıtlamaları vardır.</span><span class="sxs-lookup"><span data-stu-id="5fd19-140">Custom transports have their own restrictions on support for impersonation.</span></span>  
  
### <a name="named-pipe-transport"></a><span data-ttu-id="5fd19-141">Adlandırılmış kanal taşıma</span><span class="sxs-lookup"><span data-stu-id="5fd19-141">Named Pipe Transport</span></span>  
 <span data-ttu-id="5fd19-142">Aşağıdaki öğeler ile adlandırılmış kanal taşıma kullanılır:</span><span class="sxs-lookup"><span data-stu-id="5fd19-142">The following items are used with the named pipe transport:</span></span>  
  
-   <span data-ttu-id="5fd19-143">Adlandırılmış kanal taşıma yalnızca yerel makinede kullanıma yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="5fd19-143">The named pipe transport is intended for use only on the local machine.</span></span> <span data-ttu-id="5fd19-144">Adlandırılmış kanal taşıma [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] makineler arası bağlantılar açıkça izin vermez.</span><span class="sxs-lookup"><span data-stu-id="5fd19-144">The named pipe transport in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explicitly disallows cross-machine connections.</span></span>  
  
-   <span data-ttu-id="5fd19-145">Adlandırılmış Kanallar ile kullanılamaz `Impersonate` veya `Delegate` kimliğe bürünme düzeyi.</span><span class="sxs-lookup"><span data-stu-id="5fd19-145">Named pipes cannot be used with the `Impersonate` or `Delegate` impersonation level.</span></span> <span data-ttu-id="5fd19-146">Adlandırılmış kanal Bu kimliğe bürünme düzeyleri makine üzerinde garantisi zorunlu kılamaz.</span><span class="sxs-lookup"><span data-stu-id="5fd19-146">The named pipe cannot enforce the on-machine guarantee at these impersonation levels.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5fd19-147">Adlandırılmış Kanallar, bkz: [taşıma seçme](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md).</span><span class="sxs-lookup"><span data-stu-id="5fd19-147"> named pipes, see [Choosing a Transport](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md).</span></span>  
  
### <a name="http-transport"></a><span data-ttu-id="5fd19-148">HTTP taşıma</span><span class="sxs-lookup"><span data-stu-id="5fd19-148">HTTP Transport</span></span>  
 <span data-ttu-id="5fd19-149">HTTP taşıması kullanan bağlamaları (<xref:System.ServiceModel.WSHttpBinding> ve <xref:System.ServiceModel.BasicHttpBinding>) birden fazla kimlik doğrulama şemasını açıklandığı gibi destek [anlama HTTP kimlik doğrulaması](../../../../docs/framework/wcf/feature-details/understanding-http-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="5fd19-149">The bindings that use the HTTP transport (<xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.BasicHttpBinding>) support several authentication schemes, as explained in [Understanding HTTP Authentication](../../../../docs/framework/wcf/feature-details/understanding-http-authentication.md).</span></span> <span data-ttu-id="5fd19-150">Kimliğe bürünme düzeyi desteklenen kimlik doğrulama şeması bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="5fd19-150">The impersonation level supported depends on the authentication scheme.</span></span> <span data-ttu-id="5fd19-151">Aşağıdaki öğeler ile HTTP aktarma kullanılır:</span><span class="sxs-lookup"><span data-stu-id="5fd19-151">The following items are used with the HTTP transport:</span></span>  
  
-   <span data-ttu-id="5fd19-152">`Anonymous` Kimlik doğrulama düzeni, kimliğe bürünme göz ardı eder.</span><span class="sxs-lookup"><span data-stu-id="5fd19-152">The `Anonymous` authentication scheme ignores impersonation.</span></span>  
  
-   <span data-ttu-id="5fd19-153">`Basic` Kimlik doğrulama düzenini destekler yalnızca `Delegate` düzeyi.</span><span class="sxs-lookup"><span data-stu-id="5fd19-153">The `Basic` authentication scheme supports only the `Delegate` level.</span></span> <span data-ttu-id="5fd19-154">Tüm alt kimliğe bürünme düzeyi yükseltilir.</span><span class="sxs-lookup"><span data-stu-id="5fd19-154">All lower impersonation levels are upgraded.</span></span>  
  
-   <span data-ttu-id="5fd19-155">`Digest` Kimlik doğrulama düzenini destekler yalnızca `Impersonate` ve `Delegate` düzeyleri.</span><span class="sxs-lookup"><span data-stu-id="5fd19-155">The `Digest` authentication scheme supports only the `Impersonate` and `Delegate` levels.</span></span>  
  
-   <span data-ttu-id="5fd19-156">`NTLM` Doğrudan ya da üzerinden anlaşması, kimlik doğrulama düzeni, seçilebilir destekleyen yalnızca `Delegate` yerel makinede düzeyi.</span><span class="sxs-lookup"><span data-stu-id="5fd19-156">The `NTLM` authentication scheme, selectable either directly or through negotiation, supports only the `Delegate` level on the local machine.</span></span>  
  
-   <span data-ttu-id="5fd19-157">Yalnızca anlaşması ile seçilebilir, Kerberos kimlik doğrulama şeması herhangi bir desteklenen kimliğe bürünme düzeyi ile kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="5fd19-157">The Kerberos authentication scheme, which can only be selected through negotiation, can be used with any supported impersonation level.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5fd19-158">HTTP taşıma bkz [taşıma seçme](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md).</span><span class="sxs-lookup"><span data-stu-id="5fd19-158"> the HTTP transport, see [Choosing a Transport](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fd19-159">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5fd19-159">See Also</span></span>  
 [<span data-ttu-id="5fd19-160">Temsilcilik ve kimliğe bürünme</span><span class="sxs-lookup"><span data-stu-id="5fd19-160">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 [<span data-ttu-id="5fd19-161">Yetkilendirme</span><span class="sxs-lookup"><span data-stu-id="5fd19-161">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="5fd19-162">Nasıl yapılır: bir hizmette istemci kimliğine bürün</span><span class="sxs-lookup"><span data-stu-id="5fd19-162">How to: Impersonate a Client on a Service</span></span>](../../../../docs/framework/wcf/how-to-impersonate-a-client-on-a-service.md)  
 [<span data-ttu-id="5fd19-163">HTTP kimlik doğrulamasını anlama</span><span class="sxs-lookup"><span data-stu-id="5fd19-163">Understanding HTTP Authentication</span></span>](../../../../docs/framework/wcf/feature-details/understanding-http-authentication.md)