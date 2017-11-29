---
title: "Nasıl yapılır: Uygulama Ayarları Oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], creating
ms.assetid: 1e7aa347-af75-41e5-89ca-f53cab704f72
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 481239b472ced5ef6251b665dad16e83a170607d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-application-settings"></a><span data-ttu-id="e6148-102">Nasıl yapılır: Uygulama Ayarları Oluşturma</span><span class="sxs-lookup"><span data-stu-id="e6148-102">How to: Create Application Settings</span></span>
<span data-ttu-id="e6148-103">Yönetilen kod kullanarak, yeni uygulama ayarları oluşturabilir ve böylece bu ayarlar yüklenir ve çalışma zamanında otomatik olarak kaydedilir bunları özelliklerine formunuz veya, formun denetimlerinde bağlayın.</span><span class="sxs-lookup"><span data-stu-id="e6148-103">Using managed code, you can create new application settings and bind them to properties on your form or your form's controls, so that these settings are loaded and saved automatically at run time.</span></span>  
  
 <span data-ttu-id="e6148-104">Aşağıdaki yordamda, el ile türeyen bir sarmalayıcı sınıfı oluşturmanız <xref:System.Configuration.ApplicationSettingsBase>.</span><span class="sxs-lookup"><span data-stu-id="e6148-104">In the following procedure, you manually create a wrapper class that derives from <xref:System.Configuration.ApplicationSettingsBase>.</span></span> <span data-ttu-id="e6148-105">Bu sınıf için kullanıma sunmak istediğiniz her uygulama ayarı için genel olarak erişilebilir bir özellik ekleyin.</span><span class="sxs-lookup"><span data-stu-id="e6148-105">To this class you add a publicly accessible property for each application setting that you want to expose.</span></span>  
  
 <span data-ttu-id="e6148-106">Ayrıca, bu yordamı Visual Studio tasarımcısında çok az kod kullanarak gerçekleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e6148-106">You can also perform this procedure using minimal code in the Visual Studio designer.</span></span>  <span data-ttu-id="e6148-107">Ayrıca bkz. [nasıl yapılır: uygulama ayarları kullanarak Tasarımcı](http://msdn.microsoft.com/library/wabtadw6\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="e6148-107">Also see [How to: Create Application Settings Using the Designer](http://msdn.microsoft.com/library/wabtadw6\(v=vs.110\)).</span></span>  
  
### <a name="to-create-new-application-settings-programmatically"></a><span data-ttu-id="e6148-108">Yeni uygulama ayarları program aracılığıyla oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="e6148-108">To create new Application Settings programmatically</span></span>  
  
1.  <span data-ttu-id="e6148-109">Projeniz için yeni bir sınıf ekleyin ve yeniden adlandırın.</span><span class="sxs-lookup"><span data-stu-id="e6148-109">Add a new class to your project, and rename it.</span></span> <span data-ttu-id="e6148-110">Bu yordam, biz Bu sınıf çağıracaktır `MyUserSettings`.</span><span class="sxs-lookup"><span data-stu-id="e6148-110">For this procedure, we will call this class `MyUserSettings`.</span></span> <span data-ttu-id="e6148-111">Sınıf tanımını değiştirin, böylece sınıfın türetildiği <xref:System.Configuration.ApplicationSettingsBase>.</span><span class="sxs-lookup"><span data-stu-id="e6148-111">Change the class definition so that the class derives from <xref:System.Configuration.ApplicationSettingsBase>.</span></span>  
  
2.  <span data-ttu-id="e6148-112">Bu sarmalayıcı sınıfı ihtiyaç duyduğunuz her uygulama ayarı için bir özellik tanımlamak ve bu özellik ile ya da geçerli <xref:System.Configuration.ApplicationScopedSettingAttribute> veya <xref:System.Configuration.UserScopedSettingAttribute>ayarı kapsamını bağlı olarak.</span><span class="sxs-lookup"><span data-stu-id="e6148-112">Define a property on this wrapper class for each application setting you require, and apply that property with either the <xref:System.Configuration.ApplicationScopedSettingAttribute> or <xref:System.Configuration.UserScopedSettingAttribute>, depending on the scope of the setting.</span></span> <span data-ttu-id="e6148-113">Ayarları kapsamı hakkında daha fazla bilgi için bkz: [uygulama ayarlarına genel bakış](../../../../docs/framework/winforms/advanced/application-settings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e6148-113">For more information about settings scope, see [Application Settings Overview](../../../../docs/framework/winforms/advanced/application-settings-overview.md).</span></span> <span data-ttu-id="e6148-114">Artık, kodunuzu aşağıdaki gibi görünmelidir:</span><span class="sxs-lookup"><span data-stu-id="e6148-114">By now, your code should look like this:</span></span>  
  
     [!code-csharp[ApplicationSettings.Create#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/MyAppSettings.cs#1)]
     [!code-vb[ApplicationSettings.Create#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/MyAppSettings.vb#1)]  
  
3.  <span data-ttu-id="e6148-115">Bu sarmalayıcı sınıfının bir örneği, uygulamanızda oluşturun.</span><span class="sxs-lookup"><span data-stu-id="e6148-115">Create an instance of this wrapper class in your application.</span></span> <span data-ttu-id="e6148-116">Ayrıca, özel üye ana formun sık olacaktır.</span><span class="sxs-lookup"><span data-stu-id="e6148-116">It will commonly be a private member of the main form.</span></span> <span data-ttu-id="e6148-117">Sınıfınızda tanımladığınız, bir özelliği Bağla gerekir; Bu durumda, <xref:System.Windows.Forms.Form.BackColor%2A> formunuz özelliği.</span><span class="sxs-lookup"><span data-stu-id="e6148-117">Now that you have defined your class, you need to bind it to a property; in this case, the <xref:System.Windows.Forms.Form.BackColor%2A> property of your form.</span></span> <span data-ttu-id="e6148-118">Bunu, formun gerçekleştirebilirsiniz `Load` olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="e6148-118">You can accomplish this in your form's `Load` event handler.</span></span>  
  
     [!code-csharp[ApplicationSettings.Create#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#2)]
     [!code-vb[ApplicationSettings.Create#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#2)]  
  
4.  <span data-ttu-id="e6148-119">Çalışma zamanında ayarlarını değiştirmek için bir yol belirtirseniz, kullanıcının geçerli ayarlarının, formu kapatır, aksi takdirde, bu değişiklikler kaybolacak diske kaydetmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="e6148-119">If you provide a way to change settings at run time, you will need to save the user's current settings to disk when your form closes, or else these changes will be lost.</span></span>  
  
     [!code-csharp[ApplicationSettings.Create#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ApplicationSettings.Create/CS/Form1.cs#3)]
     [!code-vb[ApplicationSettings.Create#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ApplicationSettings.Create/VB/Form1.vb#3)]  
  
     <span data-ttu-id="e6148-120">Şimdi başarıyla yeni bir uygulama ayarı oluşturduktan ve belirtilen özelliğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="e6148-120">You have now successfully created a new application setting and bound it to the specified property.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e6148-121">.NET Framework Güvenliği</span><span class="sxs-lookup"><span data-stu-id="e6148-121">.NET Framework Security</span></span>  
 <span data-ttu-id="e6148-122">Varsayılan ayarları sağlayıcısı <xref:System.Configuration.LocalFileSettingsProvider>, yapılandırma dosyalarını bilgileri düz metin olarak devam ettirir.</span><span class="sxs-lookup"><span data-stu-id="e6148-122">The default settings provider, <xref:System.Configuration.LocalFileSettingsProvider>, persists information to configuration files as plain text.</span></span> <span data-ttu-id="e6148-123">Bu, geçerli kullanıcı için işletim sistemi tarafından sağlanan dosya erişim güvenliği için güvenlik sınırlar.</span><span class="sxs-lookup"><span data-stu-id="e6148-123">This limits security to the file access security provided by the operating system for the current user.</span></span> <span data-ttu-id="e6148-124">Bu nedenle dikkatli yapılandırma dosyalarında depolanan bilgileri alınması gerekir.</span><span class="sxs-lookup"><span data-stu-id="e6148-124">Because of this, care must be taken with the information stored in configuration files.</span></span> <span data-ttu-id="e6148-125">Örneğin, bir genel uygulama ayarları için uygulamanın veri deposuna'nın üzerine bağlantı dizeleri depolamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e6148-125">For example, one common use for application settings is to store connection strings that point to the application's data store.</span></span> <span data-ttu-id="e6148-126">Ancak, güvenlik sorunları nedeniyle, parolalar gibi dizeleri içermemelidir.</span><span class="sxs-lookup"><span data-stu-id="e6148-126">However, because of security concerns, such strings should not include passwords.</span></span> <span data-ttu-id="e6148-127">Bağlantı dizeleri hakkında daha fazla bilgi için bkz: <xref:System.Configuration.SpecialSetting>.</span><span class="sxs-lookup"><span data-stu-id="e6148-127">For more information about connection strings, see <xref:System.Configuration.SpecialSetting>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6148-128">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e6148-128">See Also</span></span>  
 <xref:System.Configuration.SpecialSettingAttribute>  
 <xref:System.Configuration.LocalFileSettingsProvider>  
 [<span data-ttu-id="e6148-129">Uygulama ayarlarına genel bakış</span><span class="sxs-lookup"><span data-stu-id="e6148-129">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [<span data-ttu-id="e6148-130">Nasıl yapılır: uygulama ayarlarını doğrulama</span><span class="sxs-lookup"><span data-stu-id="e6148-130">How to: Validate Application Settings</span></span>](../../../../docs/framework/winforms/advanced/how-to-validate-application-settings.md)