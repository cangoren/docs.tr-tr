---
title: "WCF Hizmet Yayımlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
caps.latest.revision: "22"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1dd63ca472ef5ee9211a8a9a1fd19d983694b43f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="wcf-service-publishing"></a><span data-ttu-id="5995e-102">WCF Hizmet Yayımlama</span><span class="sxs-lookup"><span data-stu-id="5995e-102">WCF Service Publishing</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="5995e-103">Hizmet yayımlama yardımcı olur, İleri aşamalara tarafından sağlanan erken geliştirme ortamı'ndan [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hizmet ana bilgisayarı ve [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] gerçekten uygulamayı test amacıyla bir üretim ortamında dağıtmak için Test istemcisi.</span><span class="sxs-lookup"><span data-stu-id="5995e-103"> Service Publishing assists you in progressing from the early development environment provided by [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Host and [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client to actually deploying the application to a production environment for testing purposes.</span></span> <span data-ttu-id="5995e-104">Son dağıtım plana yürütme önce kullanabileceğiniz [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] doğrulamak için Yayımlama hizmeti, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hizmet doğru şekilde gerçekleştirir ve yayımlanmaya hazır.</span><span class="sxs-lookup"><span data-stu-id="5995e-104">Before you commit to a final deployment plan, you can use [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Service Publishing to verify that your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service performs correctly and is ready to be published.</span></span> <span data-ttu-id="5995e-105">Ayrıca dağıtmayı seçebilirsiniz, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hizmet test etmek için çeşitli hedef konumlara kitaplıkları.</span><span class="sxs-lookup"><span data-stu-id="5995e-105">You can also choose to deploy your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service libraries to various target locations for testing.</span></span>  
  
## <a name="supported-services-and-target-locations"></a><span data-ttu-id="5995e-106">Desteklenen hizmetler ve hedef konumları</span><span class="sxs-lookup"><span data-stu-id="5995e-106">Supported Services and Target Locations</span></span>  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="5995e-107">Hizmet yayımlama destekleyen yayımlama [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] kümesinden oluşturulan Hizmetleri [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hizmet kitaplık şablonları ve aşağıdakiler dahil, karşılık gelen öğe şablonları:</span><span class="sxs-lookup"><span data-stu-id="5995e-107"> Service Publishing supports publishing [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services created from the set of [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library templates, and their corresponding item templates, which include the following:</span></span>  
  
-   [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="5995e-108">Öğe şablonu şablonla hizmet kitaplığı.</span><span class="sxs-lookup"><span data-stu-id="5995e-108"> Service Library template with item template.</span></span>  
  
-   <span data-ttu-id="5995e-109">Dağıtım Hizmeti kitaplığı.</span><span class="sxs-lookup"><span data-stu-id="5995e-109">Syndication Service Library.</span></span>  
  
 <span data-ttu-id="5995e-110">Bu hizmet şablonları seçerek bulabileceğiniz **dosya** -> **yeni proje** -> **Visual Basic** veya **Visual C#**  ->  **WCF**.</span><span class="sxs-lookup"><span data-stu-id="5995e-110">You can find these service templates by choosing **File** -> **New Project** -> **Visual Basic** or **Visual C#** -> **WCF**.</span></span> <span data-ttu-id="5995e-111">(WCF iş akışı hizmeti uygulama ve WCF Hizmeti uygulama dahil) bu konumda diğer WCF şablonları kullanarak yayımlayabileceğiniz [tek tıklatmayla web uygulamaları için yayımlamayı](https://msdn.microsoft.com/en-us/library/dd465337\(v=vs.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="5995e-111">For other WCF templates in this location (including WCF Workflow Service Application and WCF Service Application) you can publish using [One-Click publishing for web applications](https://msdn.microsoft.com/en-us/library/dd465337\(v=vs.110\).aspx).</span></span>  
  
 <span data-ttu-id="5995e-112">Hizmet aşağıdaki hedef konumlara yayımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="5995e-112">The service can be published to the following target locations.</span></span>  
  
-   <span data-ttu-id="5995e-113">Yerel IIS.</span><span class="sxs-lookup"><span data-stu-id="5995e-113">Local IIS.</span></span>  
  
-   <span data-ttu-id="5995e-114">Dosya sistemi.</span><span class="sxs-lookup"><span data-stu-id="5995e-114">File System.</span></span>  
  
-   <span data-ttu-id="5995e-115">FTP sitesi.</span><span class="sxs-lookup"><span data-stu-id="5995e-115">FTP Site.</span></span>  
  
## <a name="using-wcf-service-publishing"></a><span data-ttu-id="5995e-116">WCF kullanarak hizmet yayımlama</span><span class="sxs-lookup"><span data-stu-id="5995e-116">Using WCF Service Publishing</span></span>  
 <span data-ttu-id="5995e-117">Bir hizmet uygulaması dağıtmak için aşağıdaki adımları gerçekleştirin:</span><span class="sxs-lookup"><span data-stu-id="5995e-117">Perform the following steps to deploy a service implementation:</span></span>  
  
1.  <span data-ttu-id="5995e-118">Yükseltilmiş ayrıcalık ile Visual Studio'yu açın (yürütülebilir dosyayı sağ tıklayın ve başlatmak için "Yönetici olarak çalıştır" kullanın).</span><span class="sxs-lookup"><span data-stu-id="5995e-118">Open Visual Studio with elevated privilege ( right-click the executable and use "Run as Administrator" to launch it).</span></span>  <span data-ttu-id="5995e-119">Daha sonra "IIS metatabanı ve IIS6 yapılandırma Uyumluluğu" bileşenini kullanarak yüklediğinizden emin olun veya IIS 7.0 kullanıyorsanız "' dönüş Windows özelliklerini aç veya kapat" Denetim Masası'nda.</span><span class="sxs-lookup"><span data-stu-id="5995e-119">If you are using IIS 7.0 or later, ensure that you have installed the "IIS Metabase and IIS6 Configuration Compatibility" component using "'Turn Windows features on or off" in Control Panel.</span></span>  
  
2.  <span data-ttu-id="5995e-120">Bir hizmet projesi'ni açın, **yapı**->**Yayımla \<proje adı >** ana menüden veya'nde projeye sağ **Çözüm Gezgini**tıklatıp **Yayımla**.</span><span class="sxs-lookup"><span data-stu-id="5995e-120">Open a service project, select **Build**->**Publish \<Project Name>** from the main menu, or right-click the project in **Solution Explorer** and click **Publish**.</span></span>  
  
3.  <span data-ttu-id="5995e-121">**Yayımla** penceresi görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="5995e-121">The **Publish** window appears.</span></span> <span data-ttu-id="5995e-122">Tıklatın **...** .</span><span class="sxs-lookup"><span data-stu-id="5995e-122">Click the **…**.</span></span> <span data-ttu-id="5995e-123">hizmetin dağıtılması hedef konumu belirtmek için düğmesi.</span><span class="sxs-lookup"><span data-stu-id="5995e-123">button to specify the target location that the service should be deployed to.</span></span> <span data-ttu-id="5995e-124">Yerel IIS, dosya sistemi veya FTP sitesi için uygulama dağıtmak için seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5995e-124">You can select to deploy the application to local IIS, File System, or FTP Site.</span></span> <span data-ttu-id="5995e-125">Yerel IIS uygulama dağıtımı, Web sitenizi seçin ve tıklayarak, altında web uygulamanızı oluşturun **yeni Web uygulaması oluştur** sağ üst köşedeki simgesine tıklayın.</span><span class="sxs-lookup"><span data-stu-id="5995e-125">If deploying the application to local IIS, you can select your website and create your web application under it, by clicking the **Create New Web Application** icon at the top right corner.</span></span>  
  
4.  <span data-ttu-id="5995e-126">Tıklattıktan sonra **Yayımla** ana penceresinde, Visual Studio, belirtilen hedef konuma uygulama dağıtır ve Web.config, .svc ve derleme dosyalarını hedef dizine kopyalar.</span><span class="sxs-lookup"><span data-stu-id="5995e-126">After you click **Publish** in the main window, Visual Studio deploys the application to the specified target location and copies the Web.config, .svc, and assembly files to the target directory.</span></span> <span data-ttu-id="5995e-127">biçimindeki telefon numarasıdır.</span><span class="sxs-lookup"><span data-stu-id="5995e-127">.</span></span> <span data-ttu-id="5995e-128">.Svc adı "ProjectName.ServiceName.svc" olacaktır.</span><span class="sxs-lookup"><span data-stu-id="5995e-128">The name of .svc will be "ProjectName.ServiceName.svc".</span></span> <span data-ttu-id="5995e-129">Hizmet başarıyla yayımlandıktan sonra "..."http://localhost/WebApplicationFolderName"http://localhost/WebApplicationFolderName köprü bağlanma" benzer Visual Studio çıktı penceresinde bir etkin bağlantı bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5995e-129">After the service is published successfully, you can find a hotlink in the Visual Studio Output window, which looks similar to "Connecting to  HYPERLINK "http://localhost/WebApplicationFolderName" http://localhost/WebApplicationFolderName ...".</span></span> <span data-ttu-id="5995e-130">CTRL tuşunu BASILI tutun ve hizmet dizin yapısını görüntülemek için Visual Studio içinde tarayıcı sayfasını açmak için bağlantıya tıklayın.</span><span class="sxs-lookup"><span data-stu-id="5995e-130">You can press CTRL and click the link to open a browser page inside Visual Studio to view the service directory structure.</span></span>  
  
     <span data-ttu-id="5995e-131">Siteye göz atın, dizin tarayıcısı IIS'de etkinleştirilmediğinden olabilir.</span><span class="sxs-lookup"><span data-stu-id="5995e-131">If you cannot browse to the site, it may because directory browser is not enabled in IIS.</span></span> <span data-ttu-id="5995e-132">Lütfen etkinleştirmek için "Şeyler deneyebilirsiniz" bölümünde ipuçlarını izleyin.</span><span class="sxs-lookup"><span data-stu-id="5995e-132">Please follow the tips in the "Things you can try" section to enable it.</span></span> <span data-ttu-id="5995e-133">Alternatif olarak, doğrudan yazabileceğiniz"Köprü"http://localhost/WebApplicationFolderName"http://localhost/WebApplicationFolderName/ProjectName.ServiceName.svc" hizmet sayfasını görüntülemek için.</span><span class="sxs-lookup"><span data-stu-id="5995e-133">Alternatively, you can directly type" HYPERLINK "http://localhost/WebApplicationFolderName" http://localhost/WebApplicationFolderName/ProjectName.ServiceName.svc" to view your service page.</span></span>  
  
 <span data-ttu-id="5995e-134">Kullanabileceğiniz **Yayımla** derleme, yapılandırma ve hedef konumuna proje tanımlanan tüm hizmetler için .svc dosyasını kopyalamak isteyip istemediğinizi belirtin ve hedef konumda mevcut dosyaların üzerine yazabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5995e-134">You can use **Publish** to specify if you want to copy the assembly, configuration, and .svc file for all services defined in the project to the target location, and overwrite existing files at the destination.</span></span>  
  
 <span data-ttu-id="5995e-135">Uygulamanızı yerel IIS dağıtmak isterseniz IIS kurulumu için ilgili hatalarla karşılaşabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5995e-135">If you choose to deploy your application to local IIS, you may encounter errors related to IIS setup.</span></span> <span data-ttu-id="5995e-136">IIS düzgün yüklendiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="5995e-136">Please ensure that IIS is installed properly.</span></span> <span data-ttu-id="5995e-137">Tarayıcınızda "Köprü"http://localhost"http://localhost" yazın ve IIS varsayılan sayfasını gösteren olup olmadığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="5995e-137">You can type " HYPERLINK "http://localhost" http://localhost" in your browser and check whether the IIS default page is showing up.</span></span>  <span data-ttu-id="5995e-138">Bazı durumlarda, sorunları da ASP.NET tarafından kaynaklanıyor olabilir veya [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] IIS'de hatalı kayıt.</span><span class="sxs-lookup"><span data-stu-id="5995e-138">In some cases, the issues may also be caused by ASP.NET or [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] improper registration in IIS.</span></span> <span data-ttu-id="5995e-139">Visual Studio komut istemi açın ve ASP.NET kayıt sorunlarını gidermek için "aspnet_regiis.exe - ir" komutunu çalıştırın veya düzeltme WCF kayıt sorunları için "ServiceModelReg.exe – ia" komutunu çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="5995e-139">You can open the Visual Studio Command Prompt and run the command "aspnet_regiis.exe -ir" to fix ASP.NET registration issues, or run command "ServiceModelReg.exe –ia" to fix WCF registration issues.</span></span>  
  
## <a name="files-generated-for-publishing"></a><span data-ttu-id="5995e-140">Yayımlama için oluşturulan dosyalar</span><span class="sxs-lookup"><span data-stu-id="5995e-140">Files Generated for Publishing</span></span>  
 <span data-ttu-id="5995e-141">Önce bir [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hizmet Kitaplığı Web barındırılan olabilir, aracı tarafından oluşturulan aşağıdaki dosyaları: derleme dosyalarını, Web.config dosyasında ve .svc dosya.</span><span class="sxs-lookup"><span data-stu-id="5995e-141">Before a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library can be Web-hosted, the following files are generated by the tool: assembly files, Web.config file, and .svc file.</span></span> <span data-ttu-id="5995e-142">Tüm dosyalar, hedef konuma kopyalanır.</span><span class="sxs-lookup"><span data-stu-id="5995e-142">All the files are copied to the target location.</span></span> <span data-ttu-id="5995e-143">Hizmet sonra yayımlanır.</span><span class="sxs-lookup"><span data-stu-id="5995e-143">The service is then published.</span></span>  
  
### <a name="assembly-files"></a><span data-ttu-id="5995e-144">Derleme dosyaları</span><span class="sxs-lookup"><span data-stu-id="5995e-144">Assembly files</span></span>  
 <span data-ttu-id="5995e-145">Yayımladığınızda bir [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] bu aracı kullanarak hizmet, hizmet otomatik olarak ilk oluşturulur ve derleme dosyalarını oluşturma işleminden sonra hizmet projede oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="5995e-145">When you publish a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service using this tool, the service is automatically built first and the assembly files are generated in the service project after building.</span></span>  
  
### <a name="svc-file"></a><span data-ttu-id="5995e-146">. SVC dosyası</span><span class="sxs-lookup"><span data-stu-id="5995e-146">.SVC File</span></span>  
 <span data-ttu-id="5995e-147">Yayımlama işlemi *.svc dosyası her biri için oluşturur [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] veya değil, bir sürüm doğruluğundan emin olmak için dosyanın var olup olmadığını hizmet.</span><span class="sxs-lookup"><span data-stu-id="5995e-147">The publishing operation generates a *.svc file for each [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service, whether the file exists or not, to ensure version validity.</span></span> <span data-ttu-id="5995e-148">Svc dosyaları iki farklı tür vardır: biri [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hizmet kitaplığı ve dağıtım hizmeti kitaplığı ve başka bir sıralı ve Durum makinesi iş akışı hizmeti kitaplığı.</span><span class="sxs-lookup"><span data-stu-id="5995e-148">There are two different kinds of svc files: one for [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Library and Syndication Service Library, and another one for Sequential and State Machine Workflow Service Library.</span></span> <span data-ttu-id="5995e-149">Oluşturulan \*.svc dosya hedef konumu kök klasörüne kopyalanır.</span><span class="sxs-lookup"><span data-stu-id="5995e-149">The generated \*.svc file is copied to the root folder in the target location.</span></span>  
  
### <a name="webconfig-file"></a><span data-ttu-id="5995e-150">Web.config dosyası</span><span class="sxs-lookup"><span data-stu-id="5995e-150">Web.config File</span></span>  
 <span data-ttu-id="5995e-151">Bir hizmet projesi belirli hedef konuma yayımlanan her seferinde bir Web.config dosyası oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="5995e-151">Each time a service project is published to a specific target location, a Web.config file is created.</span></span>  
  
 <span data-ttu-id="5995e-152">Oluşturulan Web.config dosyası Web barındırma ve App.config için içeriği için yararlı olan Web bölümleri içerir [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] aşağıdaki değişiklikleri hizmet kitaplığı:</span><span class="sxs-lookup"><span data-stu-id="5995e-152">The generated Web.config file includes Web sections that are useful for Web hosting, and the content of App.config for the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library with the following changes:</span></span>  
  
-   <span data-ttu-id="5995e-153">Temel adres dışlandı.</span><span class="sxs-lookup"><span data-stu-id="5995e-153">The base address is excluded.</span></span>  
  
-   <span data-ttu-id="5995e-154">Ayarlarında `<diagnostics>` öğesi, hedef platformu izleme ayarlarını korumak için dışlanır.</span><span class="sxs-lookup"><span data-stu-id="5995e-154">Settings in the `<diagnostics>` element are excluded to preserve the tracing settings of the target platform.</span></span>  
  
## <a name="publishing-wcf-services-with-non-http-bindings-to-iis"></a><span data-ttu-id="5995e-155">IIS WCF hizmetleri HTTP olmayan bağlamaları ile yayımlama</span><span class="sxs-lookup"><span data-stu-id="5995e-155">Publishing WCF services with non-HTTP Bindings to IIS</span></span>  
 <span data-ttu-id="5995e-156">Daha sonra yayımlayabilirsiniz veya IIS7.0 kullanıyorsanız [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] IIS HTTP olmayan bağlamalar hizmetleriyle.</span><span class="sxs-lookup"><span data-stu-id="5995e-156">If you are using IIS7.0 or later, you can publish [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services with non-HTTP bindings to IIS.</span></span> <span data-ttu-id="5995e-157">Bazı öncesi yapılandırmalar yapmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="5995e-157">You need to do some pre-configurations.</span></span> <span data-ttu-id="5995e-158">Daha fazla bilgi için lütfen konuları Bkz [Windows İşlem Etkinleştirme hizmetinde barındırma](../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).</span><span class="sxs-lookup"><span data-stu-id="5995e-158">For more information, please see the topics at  [Hosting in Windows Process Activation Service](../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="5995e-159">Güvenlik</span><span class="sxs-lookup"><span data-stu-id="5995e-159">Security</span></span>  
 <span data-ttu-id="5995e-160">IIS Yönetici hesabında çalıştıran gerektirdiğinden yayımlama yerel IIS Yönetici ayrıcalığı gerektirir.</span><span class="sxs-lookup"><span data-stu-id="5995e-160">Publishing to local IIS requires administrator privilege, because IIS requires running in Administrator account.</span></span> <span data-ttu-id="5995e-161">Yönetici ayrıcalığı olmayan bir kullanıcı açarsa [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hizmet yayımlama, IIS bir hedef konum olarak kullanılabilir değil.</span><span class="sxs-lookup"><span data-stu-id="5995e-161">If a user without administrator privilege opens [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Publishing, IIS is not available as a target location.</span></span> <span data-ttu-id="5995e-162">Dosya sistemi veya FTP sitesi için yayımlama yönetici ayrıcalığı çalışır.</span><span class="sxs-lookup"><span data-stu-id="5995e-162">Publishing to File System, or FTP Site works without administrator privilege.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5995e-163">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5995e-163">See Also</span></span>  
 [<span data-ttu-id="5995e-164">WCF Visual Studio şablonları</span><span class="sxs-lookup"><span data-stu-id="5995e-164">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [<span data-ttu-id="5995e-165">WCF hizmet Konağı (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="5995e-165">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [<span data-ttu-id="5995e-166">WCF Test İstemcisi (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="5995e-166">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)