### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a>Bir SQL Server veritabanına çözümler TCP/IP bağlantı kurmaya çalışan `localhost` başarısız

|   |   |
|---|---|
|Ayrıntılar|.NET Framework 4.6 ve 4.6.1, çözümler bir SQL Server veritabanına TCP/IP bağlantı kurmaya çalışan <code>localhost</code> hatasıyla başarısız oluyor &quot;bir SQL Server bağlantısı kurulurken ağla ilgili veya örneğe özel bir hata oluştu. Sunucu bulunamadı veya erişilebilir durumda değildi. Örnek adının doğru olduğundan ve SQL Server Uzak bağlantılara izin verecek şekilde yapılandırıldığını doğrulayın. (sağlayıcı: SQL ağ arabirimleri, hata: 26 - Server/örneği belirtilen hata bulma)&quot;|
|Öneri|Bu sorun giderilmiştir ve .NET Framework 4.6.2 önceki davranış geri. Bağlanmak için çözümler bir SQL Server ı <code>localhost</code>, .NET Framework 4.6.2 yükseltin.|
|Kapsam|Küçük|
|Sürüm|4.6|
|Tür|Çalışma zamanı|

