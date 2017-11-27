---
title: "İzleme için Güvenlikle İlgili Noktalar ve Faydalı İpuçları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88bc2880-ecb9-47cd-9816-39016a07076f
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 07ac814253a563a0cbdad1014970af3d18c6fdde
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="security-concerns-and-useful-tips-for-tracing"></a><span data-ttu-id="b4901-102">İzleme için Güvenlikle İlgili Noktalar ve Faydalı İpuçları</span><span class="sxs-lookup"><span data-stu-id="b4901-102">Security Concerns and Useful Tips for Tracing</span></span>
<span data-ttu-id="b4901-103">Bu konuda, hem de WebHost kullanırken yararlı ipuçları açıklanmasını hassas bilgileri nasıl koruyabilirim açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="b4901-103">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
## <a name="using-a-custom-trace-listener-with-webhost"></a><span data-ttu-id="b4901-104">Özel İzleme dinleyicisi WebHost ile kullanma</span><span class="sxs-lookup"><span data-stu-id="b4901-104">Using a Custom Trace Listener with WebHost</span></span>  
 <span data-ttu-id="b4901-105">Kendi İzleme dinleyicisi yazıyorsanız, izlemeleri Web barındırılan hizmet durumunda kaybolabilir olasılığı haberdar olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="b4901-105">If you are writing your own trace listener, you should be aware of the possibility that traces might be lost in the case of a Web-hosted service.</span></span> <span data-ttu-id="b4901-106">WebHost dönüştürüldüğünde yinelenen devreye girer ederken dinamik işlemi kapatır.</span><span class="sxs-lookup"><span data-stu-id="b4901-106">When WebHost recycles, it shuts down the live process while a duplicate takes over.</span></span> <span data-ttu-id="b4901-107">Ancak, iki işlem dinleyicisi türüne bağlıdır süre için hala aynı kaynağa erişim izni olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b4901-107">However, the two processes must still have access to the same resource for some time, which is dependent on the listener type.</span></span> <span data-ttu-id="b4901-108">Bu durumda, `XmlWriterTraceListener` Windows olay izleme aynı oturumunda birden çok işlem yönetir ve aynı dosyaya erişim verir ancak ikinci işlem için; yeni bir izleme dosyası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b4901-108">In this case, , `XmlWriterTraceListener` creates a new trace file for the second process; while Windows event tracing manages multiple processes within the same session and gives access to the same file.</span></span> <span data-ttu-id="b4901-109">Kendi dinleyicisi benzer işlevler sağlamıyorsa, dosyanın iki işlem tarafından kilitli olduğunda izlemeleri kaybolabilir.</span><span class="sxs-lookup"><span data-stu-id="b4901-109">If your own listener does not provide similar functionalities, traces can be lost when the file is locked up by the two processes.</span></span>  
  
 <span data-ttu-id="b4901-110">Özel İzleme dinleyicisi izlemeleri ve iletileri hattaki, örneğin, uzak bir veritabanına gönderebildiğini farkında olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b4901-110">You should also be aware that a custom trace listener can send traces and messages on the wire, for example, to a remote database.</span></span> <span data-ttu-id="b4901-111">Bir uygulama dağıtıcı uygun erişim denetimi ile özel dinleyicileri yapılandırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="b4901-111">As an application deployer, you should configure custom listeners with appropriate access control.</span></span> <span data-ttu-id="b4901-112">Ayrıca, uzak konumda verilebilen herhangi bir kişisel bilgi güvenlik denetimi uygulamalısınız.</span><span class="sxs-lookup"><span data-stu-id="b4901-112">You should also apply security control on any personal information that can be exposed at the remote location.</span></span>  
  
## <a name="logging-sensitive-information"></a><span data-ttu-id="b4901-113">Hassas bilgileri günlüğe kaydetme</span><span class="sxs-lookup"><span data-stu-id="b4901-113">Logging Sensitive Information</span></span>  
 <span data-ttu-id="b4901-114">Bir ileti kapsamda olduğunda izlemeleri ileti üstbilgilerini içerir.</span><span class="sxs-lookup"><span data-stu-id="b4901-114">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="b4901-115">İzleme etkinleştirildiğinde, uygulamaya özgü üstbilgiler, sorgu dize gibi kişisel bilgilerinizi; ve kredi kartı numarası gibi bilgileri gövde, günlüklerde görünür hale gelebilir.</span><span class="sxs-lookup"><span data-stu-id="b4901-115">When tracing is enabled, personal information in application-specific headers, such as, a query string; and body information, such as, a credit card number, can become visible in the logs.</span></span> <span data-ttu-id="b4901-116">Erişim denetimini yapılandırma ve izleme dosyaları uygulama için uygulama dağıtıcı sorumludur.</span><span class="sxs-lookup"><span data-stu-id="b4901-116">The application deployer is responsible for enforcing access control on the configuration and trace files.</span></span> <span data-ttu-id="b4901-117">Bu tür bilgilerin görünür olmasını istemiyorsanız, izlemeyi devre dışı bırakmak veya izleme günlüklerini paylaşmak istiyorsanız verilerin bir kısmını filtre gerekir.</span><span class="sxs-lookup"><span data-stu-id="b4901-117">If you do not want this kind of information to be visible, you should disable tracing, or filter out part of the data if you want to share the trace logs.</span></span>  
  
 <span data-ttu-id="b4901-118">Aşağıdaki ipuçları bir izleme dosyası içeriğini istenmeden açıklanmasını önlemeye yardımcı olabilir:</span><span class="sxs-lookup"><span data-stu-id="b4901-118">The following tips can help you to prevent the content of a trace file from being exposed unintentionally:</span></span>  
  
-   <span data-ttu-id="b4901-119">Tarafından erişim denetim listeleri (ACL) hem de WebHost ve kendi kendini barındıran senaryoları korunan dosyaları günlük emin olun.</span><span class="sxs-lookup"><span data-stu-id="b4901-119">Ensure that the log files are protected by Access Control Lists (ACL) both in WebHost and self-host scenarios.</span></span>  
  
-   <span data-ttu-id="b4901-120">Web isteği kullanarak kolayca sunulamıyor bir dosya uzantısı seçin.</span><span class="sxs-lookup"><span data-stu-id="b4901-120">Choose a file extension that cannot be easily served using a Web request.</span></span> <span data-ttu-id="b4901-121">Örneğin, .xml dosya uzantısı güvenli bir seçenek değil.</span><span class="sxs-lookup"><span data-stu-id="b4901-121">For example, the .xml file extension is not a safe choice.</span></span> <span data-ttu-id="b4901-122">Sunulabilecek uzantıların listesini görmek için IIS Yönetim kılavuzuna bakabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b4901-122">You can check the IIS administration guide to see a list of extensions that can be served.</span></span>  
  
-   <span data-ttu-id="b4901-123">Bir Web tarayıcısı kullanılarak harici bir tarafça erişilmesini önlemek için WebHost vroot genel dizininin dışında olması gereken günlük dosyası konumu için mutlak bir yol belirtin.</span><span class="sxs-lookup"><span data-stu-id="b4901-123">Specify an absolute path for the log file location, which should be outside of the WebHost vroot public directory to prevent it from being accessed by an external party using a Web browser.</span></span>  
  
 <span data-ttu-id="b4901-124">Varsayılan olarak, anahtarları ve kullanıcı adı ve parola gibi kişisel bilgileri (PII) içindeki oturum açmadığı ve iletileri günlüğe.</span><span class="sxs-lookup"><span data-stu-id="b4901-124">By default, keys and personally identifiable information (PII) such as username and password are not logged in traces and logged messages.</span></span> <span data-ttu-id="b4901-125">Bir Makine Yöneticisi, ancak kullanabilirsiniz `enableLoggingKnownPII` özniteliğini `machineSettings` makinede çalışan uygulamaların bilinen kişisel bilgileri (PII) gibi oturum izin vermek için Machine.config dosyasının öğesi:</span><span class="sxs-lookup"><span data-stu-id="b4901-125">A machine administrator, however, can use the `enableLoggingKnownPII` attribute in the `machineSettings` element of the Machine.config file to permit applications running on the machine to log known personally identifiable information (PII) as follows:</span></span>  
  
```xml  
<configuration>  
   <system.ServiceModel>  
      <machineSettings enableLoggingKnownPii="Boolean"/>  
   </system.ServiceModel>  
</configuration>   
```  
  
 <span data-ttu-id="b4901-126">Bir uygulama dağıtıcı sonra kullanabileceğiniz `logKnownPii` özniteliği PII gibi günlüğe kaydetmeyi etkinleştirmek için App.config veya Web.config dosyasında:</span><span class="sxs-lookup"><span data-stu-id="b4901-126">An application deployer can then use the `logKnownPii` attribute in either the App.config or Web.config file to enable PII logging as follows:</span></span>  
  
```xml  
<system.diagnostics>  
  <sources>  
      <source name="System.ServiceModel.MessageLogging"  
        logKnownPii="true">  
        <listeners>  
                 <add name="messages"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\logs\messages.svclog" />  
          </listeners>  
      </source>  
  </sources>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="b4901-127">Yalnızca her iki ayarın olduğunda `true` PII günlük kaydı etkin.</span><span class="sxs-lookup"><span data-stu-id="b4901-127">Only when both settings are `true` is PII logging enabled.</span></span> <span data-ttu-id="b4901-128">İki anahtar birleşimi her uygulama için bilinen PII oturum esnekliği sağlar.</span><span class="sxs-lookup"><span data-stu-id="b4901-128">The combination of two switches allows the flexibility to log known PII for each application.</span></span>  
  
 <span data-ttu-id="b4901-129">İki veya daha fazla özel kaynağı bir yapılandırma dosyası belirtirseniz, yalnızca ilk kaynak özniteliklerini okuma bilmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="b4901-129">You should be aware that if you specify two or more custom sources in a configuration file, only the attributes of the first source are read.</span></span> <span data-ttu-id="b4901-130">Diğerleri yoksayılır.</span><span class="sxs-lookup"><span data-stu-id="b4901-130">The others are ignored.</span></span> <span data-ttu-id="b4901-131">Bu, PII günlüğü açıkça ikinci kaynağı için etkin olsa bile aşağıdaki App.config için dosya, PII hem kaynakları için günlüğe kaydedilmez, anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="b4901-131">This means that, for the following App.config, file, PII is not logged for both sources even though PII logging is explicitly enabled for the second source.</span></span>  
  
```xml  
<system.diagnostics>  
  <sources>  
      <source name="System.ServiceModel.MessageLogging"  
        logKnownPii="false">  
        <listeners>  
           <add name="messages"  
                type="System.Diagnostics.XmlWriterTraceListener"  
                initializeData="c:\logs\messages.svclog" />  
          </listeners>  
      </source>  
      <source name="System.ServiceModel"   
         logKnownPii="true">  
         <listeners>  
            <add name="xml" />  
         </listeners>  
      </source>  
  </sources>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="b4901-132">Varsa `<machineSettings enableLoggingKnownPii="Boolean"/>` öğesi dışında Machine.config dosyasının var, sistem oluşturur bir <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="b4901-132">If the `<machineSettings enableLoggingKnownPii="Boolean"/>` element exists outside the Machine.config file, the system throws a <xref:System.Configuration.ConfigurationErrorsException>.</span></span>  
  
 <span data-ttu-id="b4901-133">Uygulama başlatıldığında veya yeniden başlatır değişiklikler etkili olur.</span><span class="sxs-lookup"><span data-stu-id="b4901-133">The changes are effective only when the application starts or restarts.</span></span> <span data-ttu-id="b4901-134">Her iki öznitelik ayarlandığında bir olay başlangıçta kaydedilir `true`.</span><span class="sxs-lookup"><span data-stu-id="b4901-134">An event is logged at startup when both attributes are set to `true`.</span></span> <span data-ttu-id="b4901-135">Bir olay, ayrıca kaydedilir `logKnownPii` ayarlanır `true` ancak `enableLoggingKnownPii` olan `false`.</span><span class="sxs-lookup"><span data-stu-id="b4901-135">An event is also logged if `logKnownPii` is set to `true` but `enableLoggingKnownPii` is `false`.</span></span>  
  
 <span data-ttu-id="b4901-136">PII günlüğe kaydetme hakkında daha fazla bilgi için bkz: [PII güvenlik kilidi](../../../../../docs/framework/wcf/samples/pii-security-lockdown.md) örnek.</span><span class="sxs-lookup"><span data-stu-id="b4901-136">For more information on PII logging, see [PII Security Lockdown](../../../../../docs/framework/wcf/samples/pii-security-lockdown.md) sample.</span></span>  
  
 <span data-ttu-id="b4901-137">Makine Yöneticisi ve bu iki anahtar kullanıldığında, uygulama dağıtıcı son derece dikkatli olun çalışma.</span><span class="sxs-lookup"><span data-stu-id="b4901-137">The machine administrator and application deployer should exercise extreme caution when using these two switches.</span></span> <span data-ttu-id="b4901-138">PII günlüğe kaydetme işlemi etkinleştirilmişse, güvenlik anahtarlarını ve PII günlüğe kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="b4901-138">If PII logging is enabled, security keys and PII are logged.</span></span> <span data-ttu-id="b4901-139">Devre dışı ise, hala ileti üstbilgilerini ve gövdeleri hassas ve uygulamaya özgü veriler günlüğe kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="b4901-139">If it is disabled, sensitive and application-specific data is still logged in message headers and bodies.</span></span> <span data-ttu-id="b4901-140">Gizlilik ve maruz kalma PII koruma daha kapsamlı bir açıklama için bkz: [kullanıcı gizliliği](http://go.microsoft.com/fwlink/?LinkID=94647).</span><span class="sxs-lookup"><span data-stu-id="b4901-140">For a more thorough discussion on privacy and protecting PII from being exposed, see [User Privacy](http://go.microsoft.com/fwlink/?LinkID=94647).</span></span>  
  
 <span data-ttu-id="b4901-141">Ayrıca, IP adresi iletiyi gönderenin kez bağlantı yönelimli taşıma için bağlantısı ve başına bir kez aksi gönderilen ileti günlüğe kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="b4901-141">In addition, the IP address of the message sender is logged once per connection for connection-oriented transports, and once per message sent otherwise.</span></span> <span data-ttu-id="b4901-142">Bu gönderen izniniz olmadan gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="b4901-142">This is done without the consent of the sender.</span></span> <span data-ttu-id="b4901-143">Ancak, bu günlük yalnızca, varsayılan olmayan ya da izleme düzeylerini üretim, önerilen dışında hata ayıklama Canlı bilgi veya ayrıntılı izleme düzeyde oluşur.</span><span class="sxs-lookup"><span data-stu-id="b4901-143">However, this logging only occurs at the Information or Verbose tracing levels, which are not the default or recommended tracing levels in production, except for live debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4901-144">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b4901-144">See Also</span></span>  
 [<span data-ttu-id="b4901-145">İzleme</span><span class="sxs-lookup"><span data-stu-id="b4901-145">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)