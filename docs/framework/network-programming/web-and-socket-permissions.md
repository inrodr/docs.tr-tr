---
title: Web ve yuva izinleri
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- positions [.NET Framework], accepting
- sockets, permissions
- network, permissions
- Internet, permissions
- Network Resources
- SocketPermission class, about SocketPermission class
- positions [.NET Framework], connecting
- WebPermission class, about WebPermission class
- permissions [.NET Framework], sockets
- security [.NET Framework], Internet
- positions [.NET Framework], granting
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
ms.openlocfilehash: b5767f4e16e691fec5714f98114b3ed9d5692a50
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50205093"
---
# <a name="web-and-socket-permissions"></a>Web ve yuva izinleri
Internet güvenliği kullanan uygulamalar için <xref:System.Net> ad alanı tarafından sağlanır <xref:System.Net.WebPermission> ve <xref:System.Net.SocketPermission> sınıfları. **WebPermission** sınıfı uygulama isteği verilerini Sağdan bir URI veya Internet'e bir URI sunmak için denetler. **SocketPermission** sınıfını kullanmak doğru uygulama denetimleri bir <xref:System.Net.Sockets.Socket> verileri bir yerel bağlantı noktasında kabul etmek için veya başka bir adreste bağlantı noktası numarası, konak temel alınarak bir aktarım protokolünü kullanarak uzak aygıtıyla bağlantı kurmayı ve Yuva Aktarımı Protokolü.  
  
 Kullandığınız hangi izin sınıfı uygulama türüne bağlıdır. Kullanan uygulamalar <xref:System.Net.WebRequest> ve alt öğelerini kullanması gereken **WebPermission** izinleri yönetmek için sınıf. Yuva düzeyinde erişim kullanan uygulamaların kullanması gereken **SocketPermission** izinleri yönetmek için sınıf.  
  
 **WebPermission** ve **SocketPermission** iki izinleri tanımlayın: kabul edin ve bağlanın. Kabul etmek uygulamanın başka bir tarafın gelen bağlantının yanıt verme hakkı tanımaz. Connect uygulama başka bir tarafa bağlantı verme hakkı tanımaz.  
  
 İçin **SocketPermission** örnekleri, bir uygulamanın yerel gelen bağlantıları kabul edebilir anlamına gelir kabul Aktarım adresi; bağlandıkları bir uygulamanın bazı Uzak (veya yerel) aktarım adresine bağlanabileceği anlamına gelir.  
  
 İçin **WebPermission** örnekleri, bir uygulama tarafından denetlenen URI verebilirsiniz anlamına gelir kabul **WebPermission** uygulama (olup bu URI'ye erişebileceği anlamına gelir; dünya bağlanma Uzak veya yerel).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenlik](../../../docs/standard/security/index.md)  
 [Ağ Programlama Güvenliği](../../../docs/framework/network-programming/security-in-network-programming.md)
