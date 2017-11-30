---
title: "WMI ve performans sayaçları (yönetilmeyen API Başvurusu)"
description: ".NET Framework özetler yönetilmeyen API için WMI ve performans sayacı bilgileri."
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.date: 11/06/2017
ms.topic: article-type-from-white-list
ms.prod: .net-framework
ms.devlang: cpp
ms.openlocfilehash: 461d90aaf5beca1c0f1d1965ce0ea07411e56e79
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2017
---
# <a name="windows-management-instrumentation-wmi-and-performance-counters-unmanaged-api-reference"></a><span data-ttu-id="9e015-103">Windows Yönetim Araçları (WMI) ve performans sayaçları (yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="9e015-103">Windows Management Instrumentation (WMI) and Performance Counters (Unmanaged API Reference)</span></span>

<span data-ttu-id="9e015-104">.NET Framework WMI ve performans sayaçları yönetilmeyen API çağrıları sarmalamak işlevler kümesi oluşur [yerel Windows Yönetim Araçları'nı API](https://msdn.microsoft.com/library/aa389276(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="9e015-104">The .NET Framework WMI and Performance Counters unmanaged API consists of a set of functions that wrap calls to the [native Windows Management Instrumentation API](https://msdn.microsoft.com/library/aa389276(v=vs.85).aspx).</span></span> <span data-ttu-id="9e015-105">Araçlar ve yönetmek ve uzak bilgisayar sistemleri izlemek kitaplıklar geliştirme sağlar.</span><span class="sxs-lookup"><span data-stu-id="9e015-105">It allows you to develop tools and libraries that manage and monitor remote computer systems.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
<span data-ttu-id="9e015-106">API aşağıdaki işlevleri içerir:</span><span class="sxs-lookup"><span data-stu-id="9e015-106">The API includes the following functions:</span></span>

| <span data-ttu-id="9e015-107">İşlev</span><span class="sxs-lookup"><span data-stu-id="9e015-107">Function</span></span> | <span data-ttu-id="9e015-108">Açıklama</span><span class="sxs-lookup"><span data-stu-id="9e015-108">Description</span></span> |
|---------|---------|
| [<span data-ttu-id="9e015-109">BeginEnumeration işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-109">BeginEnumeration function</span></span>](beginenumeration.md) | <span data-ttu-id="9e015-110">Numaralayıcı WMI nesne özellikleri bir numaralandırmanın başlangıç durumuna sıfırlar.</span><span class="sxs-lookup"><span data-stu-id="9e015-110">Resets the enumerator to the beginning of an enumeration of WMI object properties.</span></span> |
| [<span data-ttu-id="9e015-111">BeginMethodEnumeration işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-111">BeginMethodEnumeration function</span></span>](beginmethodenumeration.md) |  <span data-ttu-id="9e015-112">Bir nesne için kullanılabilen yöntemler numaralandırması başlar.</span><span class="sxs-lookup"><span data-stu-id="9e015-112">Begins an enumeration of the methods available for an object.</span></span> |
| [<span data-ttu-id="9e015-113">BlessIWbemServices işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-113">BlessIWbemServices function</span></span>](blessiwbemservices.md) | <span data-ttu-id="9e015-114">Kullanıcı kimlik bilgilerini belirli bir IWbemServices sınıf erişime olup olmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="9e015-114">Indicates whether the user credentials permit access to a specified IWbemServices class.</span></span> |
| [<span data-ttu-id="9e015-115">BlessIWbemServicesObject işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-115">BlessIWbemServicesObject function</span></span>](blessiwbemservicesobject.md) | <span data-ttu-id="9e015-116">Kullanıcı kimlik bilgilerinin belirtilen IWbem servis nesnesi erişime olup olmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="9e015-116">Indicates whether the user credentials permit access to a specified IWbem service object.</span></span> |
| [<span data-ttu-id="9e015-117">Kopya işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-117">Clone function</span></span>](clone.md) | <span data-ttu-id="9e015-118">Geçerli nesnenin tam bir kopyası olan yeni bir nesne döndürür.</span><span class="sxs-lookup"><span data-stu-id="9e015-118">Returns a new object that is a complete clone of the current object.</span></span> |
| [<span data-ttu-id="9e015-119">CloneEnumWbemClassObject işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-119">CloneEnumWbemClassObject function</span></span>](cloneenumwbemclassobject.md) | <span data-ttu-id="9e015-120">Numaralandırma içindeki geçerli konumunu koruyarak bir numaralandırıcı mantıksal bir kopyasını oluşturur.</span><span class="sxs-lookup"><span data-stu-id="9e015-120">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span> |
| [<span data-ttu-id="9e015-121">CompareTo işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-121">CompareTo function</span></span>](compareto.md) | <span data-ttu-id="9e015-122">Nesneyi başka bir Windows Yönetim nesnesi için karşılaştırır.</span><span class="sxs-lookup"><span data-stu-id="9e015-122">Compares an object to another Windows management object.</span></span> |
| [<span data-ttu-id="9e015-123">ConnectServerWmi işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-123">ConnectServerWmi function</span></span>](connectserverwmi.md) | <span data-ttu-id="9e015-124">Belirtilen bir bilgisayardaki bir WMI ad alanı için DCOM aracılığıyla yapılan bağlantı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="9e015-124">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span> |
| [<span data-ttu-id="9e015-125">CreateClassEnumWmi işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-125">CreateClassEnumWmi function</span></span>](createclassenumwmi.md) | <span data-ttu-id="9e015-126">Belirtilen seçim ölçütü karşılayan tüm sınıflar için bir numaralandırıcı döndürür.</span><span class="sxs-lookup"><span data-stu-id="9e015-126">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span> |
| [<span data-ttu-id="9e015-127">CreateInstanceEnumWmi işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-127">CreateInstanceEnumWmi function</span></span>](createinstanceenumwmi.md) | <span data-ttu-id="9e015-128">Belirtilen bir sınıfın belirtilen seçim ölçütlerine intances döndüren bir numaralandırıcı döndürür.</span><span class="sxs-lookup"><span data-stu-id="9e015-128">Returns an enumerator that returns the intances of a specified class that meet specified selection criteria.</span></span> |
| [<span data-ttu-id="9e015-129">İşlev Sil</span><span class="sxs-lookup"><span data-stu-id="9e015-129">Delete function</span></span>](delete.md) | <span data-ttu-id="9e015-130">Belirtilen bir özelliği bir sınıf tanımı ve tüm alt niteleyicileri siler.</span><span class="sxs-lookup"><span data-stu-id="9e015-130">Deletes a specified property from a class definition and all of its qualifiers.</span></span> |
| [<span data-ttu-id="9e015-131">DeleteMethod işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-131">DeleteMethod function</span></span>](deletemethod.md) | <span data-ttu-id="9e015-132">Belirtilen yöntem bir CIM sınıfı tanımından siler.</span><span class="sxs-lookup"><span data-stu-id="9e015-132">Deletes a specified method from a CIM class definition.</span></span> |
| [<span data-ttu-id="9e015-133">Örneğin işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-133">EndEnumeration function</span></span>](endenumeration.md) | <span data-ttu-id="9e015-134">Bir numaralandırma sırasını sonlandırır.</span><span class="sxs-lookup"><span data-stu-id="9e015-134">Terminates an enumeration sequence.</span></span> | 
| [<span data-ttu-id="9e015-135">EndMethodEnumeration işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-135">EndMethodEnumeration function</span></span>](endmethodenumeration.md) | <span data-ttu-id="9e015-136">Çağrılarak başlatılan bir numaralandırma sırasını sonlandırır [BeginMethodEnumeration işlevi](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="9e015-136">Terminates an enumeration sequence started by calling the  [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span> |
| [<span data-ttu-id="9e015-137">ExecNotificationQueryWmi işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-137">ExecNotificationQueryWmi function</span></span>](execnotificationquerywmi.md) | <span data-ttu-id="9e015-138">Olaylarını almak için bir sorgu yürütür.</span><span class="sxs-lookup"><span data-stu-id="9e015-138">Executes a query to receive events.</span></span> |
| [<span data-ttu-id="9e015-139">ExecQueryWmi işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-139">ExecQueryWmi function</span></span>](execquerywmi.md) | <span data-ttu-id="9e015-140">Nesneleri almak için bir sorgu yürütür.</span><span class="sxs-lookup"><span data-stu-id="9e015-140">Executes a query to retrieve objects.</span></span> |
| [<span data-ttu-id="9e015-141">FormatFromRawValue işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-141">FormatFromRawValue function</span></span>](formatfromrawvalue.md) | <span data-ttu-id="9e015-142">Biçim dönüştürmeyi zamana dayalı ise belirtilen biçime bir ham performans veri değeri veya iki ham performans veri değerleri dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="9e015-142">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span> | 
| [<span data-ttu-id="9e015-143">Get işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-143">Get function</span></span>](get.md) | <span data-ttu-id="9e015-144">Varsa belirtilen özellik değerini alır.</span><span class="sxs-lookup"><span data-stu-id="9e015-144">Retrieves a specified property value if it exists.</span></span> |
| [<span data-ttu-id="9e015-145">GetCurrentApartmentType işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-145">GetCurrentApartmentType function</span></span>](getcurrentapartmenttype.md) | <span data-ttu-id="9e015-146">Arayan yürütülmekte olduğu Grup türünü alır.</span><span class="sxs-lookup"><span data-stu-id="9e015-146">Retrieves the type of apartment in which the caller is executing.</span></span> |
| [<span data-ttu-id="9e015-147">GetDemultiplexedStub işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-147">GetDemultiplexedStub function</span></span>](getdemultiplexedstub.md) | <span data-ttu-id="9e015-148">Windows Yönetimi'nden zaman uyumsuz çağrılar alırken bir istemci yardımcı olması için bir nesne iletici havuz oluşturur.</span><span class="sxs-lookup"><span data-stu-id="9e015-148">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span> |
| [<span data-ttu-id="9e015-149">Geterrorınfo işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-149">GetErrorInfo function</span></span>](geterrorinfo.md) | <span data-ttu-id="9e015-150">Önceki işlev çağrısında hata bilgilerini alır.</span><span class="sxs-lookup"><span data-stu-id="9e015-150">Retrieves error information from the previous function call.</span></span> | 
| [<span data-ttu-id="9e015-151">GetMethod işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-151">GetMethod function</span></span>](getmethod.md) | <span data-ttu-id="9e015-152">Belirtilen yöntem bilgilerini alır.</span><span class="sxs-lookup"><span data-stu-id="9e015-152">Retrieves information about the specified method.</span></span> | 
| [<span data-ttu-id="9e015-153">GetMethodOrigin işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-153">GetMethodOrigin function</span></span>](getmethodorigin.md) | <span data-ttu-id="9e015-154">Bir yöntem olarak bildirilen sınıfı belirler.</span><span class="sxs-lookup"><span data-stu-id="9e015-154">Determines the class in which a method is declared.</span></span> |
| [<span data-ttu-id="9e015-155">GetMethodQualifierSet işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-155">GetMethodQualifierSet function</span></span>](getmethodqualifierset.md) | <span data-ttu-id="9e015-156">Belirli bir yöntem için ayarlanmış niteleyicisi alır.</span><span class="sxs-lookup"><span data-stu-id="9e015-156">Retrieves the qualifier set for a particular method.</span></span> |
| [<span data-ttu-id="9e015-157">GetNames işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-157">GetNames function</span></span>](getnames.md) | <span data-ttu-id="9e015-158">Bir alt veya tümünü bir nesnenin özellik adlarını alır.</span><span class="sxs-lookup"><span data-stu-id="9e015-158">Retrieves either a subset or all of the names of the properties of an object.</span></span> |
| [<span data-ttu-id="9e015-159">GetObjectText işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-159">GetObjectText function</span></span>](getobjecttext.md) | <span data-ttu-id="9e015-160">Bir nesnenin bir metinsel oluşturma MOF sözdiziminde döndürür.</span><span class="sxs-lookup"><span data-stu-id="9e015-160">Returns a textual rendering of an object in the MOF syntax.</span></span> | 
| [<span data-ttu-id="9e015-161">GetPropertyHandle işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-161">GetPropertyHandle function</span></span>](getpropertyhandle.md) | <span data-ttu-id="9e015-162">Bir özelliği tanımlayan benzersiz bir tanıtıcı döndürür.</span><span class="sxs-lookup"><span data-stu-id="9e015-162">Returns a unique handle that identifies a property.</span></span> |
| [<span data-ttu-id="9e015-163">GetPropertyOrigin işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-163">GetPropertyOrigin function</span></span>](getpropertyorigin.md) | <span data-ttu-id="9e015-164">Bir özellik bildirilmedi sınıfı belirler.</span><span class="sxs-lookup"><span data-stu-id="9e015-164">Determines the class in which a property is declared.</span></span> |
| [<span data-ttu-id="9e015-165">GetPropertyQualifierSet işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-165">GetPropertyQualifierSet function</span></span>](getpropertyqualifierset.md) | <span data-ttu-id="9e015-166">Belirli bir özelliği için belirlenen niteleyicisi alır.</span><span class="sxs-lookup"><span data-stu-id="9e015-166">Retrieves the qualifier set for a particular property.</span></span>  |
| [<span data-ttu-id="9e015-167">GetQualifierSet işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-167">GetQualifierSet function</span></span>](getqualifierset.md) | <span data-ttu-id="9e015-168">Sınıf örneği veya bir sınıf tanımı için ayarlamak niteleyicisi alır.</span><span class="sxs-lookup"><span data-stu-id="9e015-168">Retrieves the qualifier set for a class instance or a class definition.</span></span> |
| [<span data-ttu-id="9e015-169">InheritsFrom işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-169">InheritsFrom function</span></span>](inheritsfrom.md) | <span data-ttu-id="9e015-170">Geçerli sınıf veya örnek belirtilen üst sınıftan türetilen olup olmadığını belirler.</span><span class="sxs-lookup"><span data-stu-id="9e015-170">Determines whether the current class or instance derives from a specified parent class.</span></span> |
| [<span data-ttu-id="9e015-171">Initialize işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-171">Initialize function</span></span>](initialize.md) | <span data-ttu-id="9e015-172">WMI başlatma gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="9e015-172">Performs WMI initialization.</span></span> |
| [<span data-ttu-id="9e015-173">Next işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-173">Next function</span></span>](next.md) | <span data-ttu-id="9e015-174">Bir listedeki sonraki özelliği alır.</span><span class="sxs-lookup"><span data-stu-id="9e015-174">Retrieves the next property in an enumeration.</span></span> | 
| [<span data-ttu-id="9e015-175">NextMethod işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-175">NextMethod function</span></span>](nextmethod.md) | <span data-ttu-id="9e015-176">Numaralandırma sonraki yöntem alır.</span><span class="sxs-lookup"><span data-stu-id="9e015-176">Retrieves the next method in an enumeration.</span></span> |
| [<span data-ttu-id="9e015-177">PUT işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-177">Put function</span></span>](put.md) | <span data-ttu-id="9e015-178">Adlandırılmış bir özelliği için yeni bir değer ayarlar.</span><span class="sxs-lookup"><span data-stu-id="9e015-178">Sets a named property to a new value.</span></span> |
| [<span data-ttu-id="9e015-179">PutClassWmi işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-179">PutClassWmi function</span></span>](putclasswmi.md) | <span data-ttu-id="9e015-180">Yeni bir sınıf oluşturur veya mevcut bir güncelleştirir.</span><span class="sxs-lookup"><span data-stu-id="9e015-180">Creates a new class or updates an existing one.</span></span> |
| [<span data-ttu-id="9e015-181">PutInstanceWmi işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-181">PutInstanceWmi function</span></span>](putinstancewmi.md) | <span data-ttu-id="9e015-182">Oluşturur veya mevcut bir sınıfın bir örneğini güncelleştirir.</span><span class="sxs-lookup"><span data-stu-id="9e015-182">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="9e015-183">Örnek için WMI deposunun yazılır.</span><span class="sxs-lookup"><span data-stu-id="9e015-183">The instance is written to the WMI repository.</span></span> |
| [<span data-ttu-id="9e015-184">PutMethod işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-184">PutMethod function</span></span>](putmethod.md) | <span data-ttu-id="9e015-185">Bir yöntem oluşturur.</span><span class="sxs-lookup"><span data-stu-id="9e015-185">Creates a method.</span></span> |
| [<span data-ttu-id="9e015-186">QualifierSet_BeginEnumeration işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-186">QualifierSet_BeginEnumeration function</span></span>](qualifierset-beginenumeration.md) | <span data-ttu-id="9e015-187">Bir nesnenin niteleyicileri numaralandırması sabit başlangıç durumuna sıfırlar.</span><span class="sxs-lookup"><span data-stu-id="9e015-187">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span> |
| [<span data-ttu-id="9e015-188">QualifierSet_Delete işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-188">QualifierSet_Delete function</span></span>](qualifierset-delete.md) | <span data-ttu-id="9e015-189">Belirtilen bir niteleyici adıyla siler.</span><span class="sxs-lookup"><span data-stu-id="9e015-189">Deletes a specified qualifier by name.</span></span>  |
| [<span data-ttu-id="9e015-190">QualifierSet_EndEnumeration işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-190">QualifierSet_EndEnumeration function</span></span>](qualifierset-endenumeration.md) | <span data-ttu-id="9e015-191">Çağrısıyla başlamış numaralandırması sonlandırır `QualifierSet_BeginEnumeration` işlevi.</span><span class="sxs-lookup"><span data-stu-id="9e015-191">Terminates the enumeration begun with a call to the `QualifierSet_BeginEnumeration` function.</span></span> |
| [<span data-ttu-id="9e015-192">QualifierSet_Get işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-192">QualifierSet_Get function</span></span>](qualifierset-get.md) | <span data-ttu-id="9e015-193">Belirtilen adlandırılmış niteleyici alır.</span><span class="sxs-lookup"><span data-stu-id="9e015-193">Gets the specified named qualifier.</span></span>  |
| [<span data-ttu-id="9e015-194">QualifierSet_GetNames işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-194">QualifierSet_GetNames function</span></span>](qualifierset-getnames.md) | <span data-ttu-id="9e015-195">Tüm niteleyicileri veya geçerli nesne ya da özellik kullanılabilir belirtilen niteleyicileri adlarını alır.</span><span class="sxs-lookup"><span data-stu-id="9e015-195">Retrieves the names of all qualifiers or of specified qualifiers that are available from the current object or property.</span></span> |
| [<span data-ttu-id="9e015-196">QualifierSet_Next işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-196">QualifierSet_Next function</span></span>](qualifierset-next.md) | <span data-ttu-id="9e015-197">Sonraki çağrı kullanmaya bir numaralandırma niteleyicisinde alır [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) işlevi.</span><span class="sxs-lookup"><span data-stu-id="9e015-197">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span> |
| [<span data-ttu-id="9e015-198">QualifierSet_Put işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-198">QualifierSet_Put function</span></span>](qualifierset-put.md) | <span data-ttu-id="9e015-199">Değeri ve adlandırılmış niteleyicisi yazar.</span><span class="sxs-lookup"><span data-stu-id="9e015-199">Writes the named qualifier and value.</span></span> |
| [<span data-ttu-id="9e015-200">ResetSecurity işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-200">ResetSecurity function</span></span>](resetsecurity.md) | <span data-ttu-id="9e015-201">Sağlanan kimliğe bürünme belirteci geçerli iş parçacığına atar.</span><span class="sxs-lookup"><span data-stu-id="9e015-201">Assigns the supplied impersonation token to the current thread.</span></span> |
| [<span data-ttu-id="9e015-202">SetSecurity işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-202">SetSecurity function</span></span>](setsecurity.md) | <span data-ttu-id="9e015-203">Geçerli iş parçacığı ile ilişkili kimliğe bürünme belirtecini alır.</span><span class="sxs-lookup"><span data-stu-id="9e015-203">Retrieves the impersonation token associated with the current thread.</span></span> |
| [<span data-ttu-id="9e015-204">SpawnDerivedClass işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-204">SpawnDerivedClass function</span></span>](spawnderivedclass.md) | <span data-ttu-id="9e015-205">Belirtilen bir nesneden bir yeni türetilmiş bir sınıf oluşturur.</span><span class="sxs-lookup"><span data-stu-id="9e015-205">Creates a newly derived class object from a specified object.</span></span> | 
| [<span data-ttu-id="9e015-206">SpawnInstance işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-206">SpawnInstance function</span></span>](spawninstance.md) | <span data-ttu-id="9e015-207">Bir sınıfın yeni bir örneğini oluşturur.</span><span class="sxs-lookup"><span data-stu-id="9e015-207">Creates a new instance of a class.</span></span> |   
| [<span data-ttu-id="9e015-208">VerifyClient işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-208">VerifyClient function</span></span>](verifyclientkey.md) | <span data-ttu-id="9e015-209">İstemci anahtar doğru güvenlik sahip olmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="9e015-209">Ensures that the client key has the correct security.</span></span> |
| [<span data-ttu-id="9e015-210">WritePropertyValue işlevi</span><span class="sxs-lookup"><span data-stu-id="9e015-210">WritePropertyValue function</span></span>](writepropertyvalue.md) | <span data-ttu-id="9e015-211">Bir özellik tanımlayıcısı tarafından tanımlanan bir özellik için belirtilen sayıda baytı yazar.</span><span class="sxs-lookup"><span data-stu-id="9e015-211">Writes a specified number of bytes to a property identified by a property handle.</span></span> |

 ## <a name="see-also"></a><span data-ttu-id="9e015-212">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9e015-212">See also</span></span>
[<span data-ttu-id="9e015-213">Yönetilmeyen API Başvurusu</span><span class="sxs-lookup"><span data-stu-id="9e015-213">Unmanaged API reference</span></span>](../index.md) 