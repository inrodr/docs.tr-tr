---
title: Ağ izlemeyi etkinleştirme
ms.date: 03/30/2017
helpviewer_keywords:
- trace destinations
- sending traces to log file
- trace listeners, network tracing
- network tracing, enabling
- CLR Debugger
- default listeners
- logs, trace
- destination for tracing output
ms.assetid: 5fff458c-51a6-4134-ba47-8a6137ddc41e
ms.openlocfilehash: b289aa2a60deb10ebda0ca8efc3e172caf2df8a6
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2018
ms.locfileid: "50202074"
---
# <a name="enabling-network-tracing"></a>Ağ izlemeyi etkinleştirme
Ağ izleme yöntem çağrıları ve yönetilen bir uygulama tarafından oluşturulan ağ trafiğiyle ilgili bilgilere erişim sağlar. Uygulamanızda ağ izlemeyi etkinleştirmek için aşağıdaki görevleri tamamlamanız gerekir:  
  
-   Kodunuzu izleme etkin derleyin. Bkz: [nasıl yapılır: izleme ve hata ayıklama ile koşullu derleme](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) izlemeyi etkinleştirmek için gerekli derleyici anahtarları hakkında daha fazla bilgi.  
  
-   İzleme çıkışı için bir hedef belirtin.  
  
-   Ağ izleme davranışını yapılandırın. Bkz: [nasıl yapılır: ağ izlemeyi yapılandırma](../../../docs/framework/network-programming/how-to-configure-network-tracing.md) ayrıntılı bilgi için.  
  
 İzleme dinleyicileri da adlandırılan en yaygın izleme hedefleri şunlardır: varsayılan dinleyici ve günlük dosyası.  
  
 İzleme, İzleme dinleyicisi belirtmezseniz varsayılan dinleyicisi kullanır. CLR hata ayıklayıcısı .NET Framework SDK ile birlikte gelen veya DBwin32.exe Windows SDK'sı ile birlikte gelen gibi bir yönetilen kod etkin hata ayıklayıcıda kodunuzu yürüterek varsayılan dinleyiciye gönderilen iletileri görüntüleyebilirsiniz. CLR hata ayıklayıcıyı kullanarak izleme iletilerini görünür **çıkış** penceresi.  
  
 İzlemeleri almak için bir dosya kullanmayı tercih ederseniz, günlük dosyası, yapılandırma ayarlarını kullanarak aşağıdaki örnekte gösterildiği gibi belirtebilirsiniz. (Yapılandırma dosyaları hakkında genel bilgiler için bkz: [yapılandırma dosyalarını](../../../docs/framework/configure-apps/index.md).)  
  
 Bir günlük dosyasına izlemeleri göndermek için aşağıdaki düğüm için ekleme `<system.diagnostics>` düğümü uygun yapılandırma dosyasının (uygulama veya makine). İhtiyaçlarınıza uygun şekilde (trace.log) dosyasının adını değiştirebilirsiniz.  
  
```xml  
<system.diagnostics>  
  <trace autoflush="true" indentsize="4">  
    <listeners>  
      <add name="file" type="System.Diagnostics.TextWriterTraceListener" initializeData="trace.log"/>  
    </listeners>   
  </trace>  
</system.diagnostics>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ağ İzlemeyi Yorumlama](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [.NET Framework'te Ağ İzleme](../../../docs/framework/network-programming/network-tracing.md)  
 [İzleme ve İşaretleme Uygulamaları](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
