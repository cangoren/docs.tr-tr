---
title: /win32manifest (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a46641181c3ff66882468f8372bb97c3a49a8462
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="win32manifest-visual-basic"></a>/win32manifest (Visual Basic)
Bir projenin taşınabilir yürütülebilir (PE) dosyasına katıştırılmış bir kullanıcı tarafından tanımlanan Win32 uygulama bildirim dosyasının tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/win32manifest: fileName  
```  
  
## <a name="arguments"></a>Arguments  
  
|Terim|Tanım|  
|---|---|  
|`fileName`|Özel bildirim dosyasının yolu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, Visual Basic derleyici asInvoker istenen yürütme düzeyini belirten bir uygulama bildirimi katıştırır. Hangi yürütülebilir dosya yapılandırıldığında, genellikle bin\Debug veya bin\Release klasörü, Visual Studio kullandığınızda aynı klasörde bildirimi oluşturur. Örneğin highestAvailable veya requireAdministrator istenen yürütme düzeyini belirtmek özel bir bildirimi sağlamak istiyorsanız, dosya adını belirtmek için bu seçeneği kullanın.  
  
> [!NOTE]
>  Bu seçenek ve [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) seçeneği karşılıklı olarak birbirini dışlar. Her iki seçenek aynı komut satırında kullanmaya çalışırsa, bir derleme hatası alırsınız.  
  
 Hiçbir uygulama bildirimini olan bir uygulama, istenen yürütme düzeyinin Windows Vista kullanıcı hesabı denetimi özelliği altında dosya/kayıt defteri sanallaştırma tabi olacağını belirtir. Sanallaştırma hakkında daha fazla bilgi için bkz: [Windows Vista'da ClickOnce dağıtımı](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 Aşağıdaki koşullardan biri doğru olduğunda, uygulamanızın sanallaştırma tabi olacaktır:  
  
1.  Kullandığınız `/nowin32manifest` seçeneğini sağlamaz daha yeni bir derleme adımı veya Windows Kaynak (.res) dosyasının bir parçası olarak bir bildirim kullanarak `/win32resource` seçeneği.  
  
2.  İstenen yürütme düzeyinin belirtmiyor özel bir bildirim sağlar.  
  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]Varsayılan bir .manifest dosyası oluşturur ve yürütülebilir dosyanın yanında hata ayıklama ve yayın dizinleri depolar. Görüntülemek veya tıklayarak varsayılan app.manifest dosyasını düzenleyin **görünümü UAC ayarları** üzerinde **uygulama** Proje Tasarımcısı'nda sekmesi. Daha fazla bilgi için bkz: [uygulama sayfası, Proje Tasarımcısı (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 Kullanarak oluşturma sonrası özel bir adım veya Win32 kaynak dosyasını bir parçası olarak uygulama bildirimini sağlayabilirsiniz `/nowin32manifest` seçeneği. Uygulamanızın Windows Vista dosya veya kayıt defteri sanallaştırma tabi olmasını istiyorsanız aynı seçeneği kullanın. Bu oluşturma ve varsayılan bildirimini PE'yi dosyasında katıştırma derleyici engeller.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, Visual Basic derleyici bir PE'ye eklediği varsayılan bildirimi gösterir.  
  
> [!NOTE]
>  Derleyici standart uygulama adı MyApplication.app XML bildirimine ekler. Bu, uygulamaların Windows Server 2003 Service Pack 3 üzerinde çalışmasını etkinleştirmek için bir çözüm olabilir.  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Basic komut satırı derleyicisi](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
