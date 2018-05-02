### <a name="default-value-of-servicepointmanagersecurityprotocol-is-securityprotocoltypesystemdefault"></a>SecurityProtocolType.System.Default ServicePointManager.SecurityProtocol varsayılan değeri.

|   |   |
|---|---|
|Ayrıntılar|Varsayılan değer olan .NET Framework 4.7 hedef uygulamalarla başlangıç <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> özelliği <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>. Bu değişiklik, .NET Framework ağ API'leri SslStream (örneğin, FTP, HTTPS ve SMTP) .NET Framework tarafından tanımlanan sabit kodlanmış değerler yerine bu işletim sistemindeki varsayılan güvenlik protokollerini devralmak için temel sağlar. Varsayılan işletim sistemi ve Sistem Yöneticisi tarafından gerçekleştirilen herhangi bir özel yapılandırma göre değişir. Her Windows işletim sistemi sürümü varsayılan SChannel protokol hakkında daha fazla bilgi için bkz: [protokolleri de TLS/SSL'deki (Schannel SSP)](https://msdn.microsoft.com/library/windows/desktop/mt808159.aspx). Varsayılan değer olan .NET Framework'ün önceki bir sürümünü kullanan uygulamalar için <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> özellik hedeflenen .NET Framework sürümüne bağlıdır. Bkz: [.NET Framework 4.5.2 için 4.6 geçiş için yeniden hedefleme değişiklikleri ağ bölümünü](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking) daha fazla bilgi için.|
|Öneri|Bu değişiklik, .NET Framework 4.7 veya sonraki sürümlerini hedefleyen uygulamaları etkiler. Yerine tanımlanan Protokolü kullanmayı tercih ederseniz, sistem varsayılan olarak bağlı olan, değeri açıkça ayarlayabilirsiniz <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> özelliği. Bu değişiklik istenmeyen ise, bunun dışında bir yapılandırma ayarı ekleyerek seçebilirsiniz [ \<çalışma zamanı >](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) uygulama yapılandırma dosyasının. Aşağıdaki örnek, her ikisi de gösterir <code>&lt;runtime&gt;</code> bölüm ve <code>Switch.System.Net.DontEnableSystemDefaultTlsVersions</code> çevirin anahtarı:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableSystemDefaultTlsVersions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Kapsam|Küçük|
|Sürüm|4.7|
|Tür|Yeniden hedefleme|
|Etkilenen API'leri|<ul><li><xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType></li></ul>|
