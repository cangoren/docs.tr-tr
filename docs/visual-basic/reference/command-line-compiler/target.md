---
title: /target (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8a8a9fcd6fa6dfaace01f8fbb7fa407145acc16f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="target-visual-basic"></a>/target (Visual Basic)
Derleyici çıktı biçimi belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki tabloda özetlenmiştir etkisini `/target` seçeneği.  
  
|**Seçeneği**|**Davranışı**|  
|----------------|------------------|  
|`/target:exe`|Bir yürütülebilir konsol uygulaması oluşturmak derleyici neden olur.<br /><br /> Bu durumlarda varsayılan seçenektir; `/target` seçeneği belirtildi. Yürütülebilir dosyanın .exe uzantısı ile oluşturulur.<br /><br /> İle aksi belirtilmediği sürece `/out` seçeneği, çıktı dosyası adını içeren giriş dosyası adını alır `Sub Main` yordamı.<br /><br /> Yalnızca bir `Sub Main` yordamı bir .exe dosyasına derlenen kaynak kodu dosyaları gereklidir. Kullanım `/main` hangi sınıfı içeren belirtmek için derleyici seçeneği `Sub Main` yordamı.|  
|`/target:library`|Bir dinamik bağlantı kitaplığı (DLL) oluşturmak derleyici neden olur.<br /><br /> Dinamik bağlantı kitaplığı dosya bir .dll uzantısına sahip bir oluşturulur.<br /><br /> İle aksi belirtilmediği sürece `/out` seçeneği, çıktı dosyası adı ilk giriş dosyasının adını alır.<br /><br /> Bir DLL oluştururken bir `Sub Main` yordam gerekli değildir.|  
|`/target:module`|Derleyicinin bir derlemeye eklenebilir bir modül oluşturmasına neden olur.<br /><br /> Çıktı dosyası .netmodule uzantı ile oluşturulur.<br /><br /> .NET ortak dil çalışma zamanı bütünleştirilmiş sahip olmayan bir dosya yüklenemiyor. Bir derlemenin derleme bildirimine kullanarak bu tür bir dosya ancak birleştirebilirsiniz `/reference`.<br /><br /> Kod bir modüldeki başka bir modül iç türlerinde başvurduğunda, her iki modülleri bir derleme bildirimine kullanarak birleştirilmesi gerekir `/reference`.<br /><br /> [/Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) seçenek, bir modülden meta verileri alır.|  
|`/target:winexe`|Yürütülebilir bir Windows tabanlı uygulama oluşturmak derleyici neden olur.<br /><br /> Yürütülebilir dosyanın .exe uzantısı ile oluşturulur. Windows tabanlı bir uygulama bir kullanıcı arabiriminden ya da sağlayan biridir [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] sınıf kitaplığı veya Win32 API'ları ile.<br /><br /> İle aksi belirtilmediği sürece `/out` seçeneği, çıktı dosyası adını içeren giriş dosyası adını alır `Sub Main` yordamı.<br /><br /> Yalnızca bir `Sub Main` yordamı bir .exe dosyasına derlenen kaynak kodu dosyaları gereklidir. Kodunuzu sahip olan birden fazla sınıfı olduğu durumlarda bir `Sub Main` yordamı, kullanım `/main` hangi sınıfı içeren belirtmek için derleyici seçeneği `Sub Main` yordamı|  
|`/target:appcontainerexe`|Bir uygulama kapsayıcısında çalıştırılması gereken yürütülebilir Windows tabanlı bir uygulama oluşturmak derleyici neden olur. Bu ayar için kullanılmak üzere tasarlanmış [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] uygulamalar.<br /><br /> **Appcontainerexe** ayarı ayarlar biraz özellikleri alanında [taşınabilir yürütülebilir](http://go.microsoft.com/fwlink/p/?LinkId=236960) dosya. Bu bit uygulama bir uygulama kapsayıcısında çalıştırmanız gerekir belirtir. Bu bit ayarlandığında, hata durumunda oluşur. `CreateProcess` yöntemi bir uygulama kapsayıcısı dışında uygulamayı başlatmak dener. Bu bit ayarı yanı sıra **/target: appcontainerexe** eşdeğerdir **/target: winexe**.<br /><br /> Yürütülebilir dosyanın .exe uzantısı ile oluşturulur.<br /><br /> Kullanarak aksini belirtmedikçe `/out` seçeneği, çıktı dosyası adını içeren giriş dosyası adını alır `Sub Main` yordamı.<br /><br /> Yalnızca bir `Sub Main` yordamı bir .exe dosyasına derlenen kaynak kodu dosyaları gereklidir. Kodunuzu sahip birden fazla sınıf içeriyorsa bir `Sub Main` yordamı, kullanım `/main` hangi sınıfı içeren belirtmek için derleyici seçeneği `Sub Main` yordamı|  
|`/target:winmdobj`|Windows çalışma zamanı ikili (.winmd) dosyasına dönüştüren bir ara dosyası oluşturmak derleyici neden olur. Yönetilen dil programlar yanı sıra, JavaScript ve C++ programlarla .winmd dosya tüketilebilir.<br /><br /> Ara dosyası .winmdobj uzantısı ile oluşturulur.<br /><br /> Kullanarak aksini belirtmedikçe `/out` seçeneği, çıktı dosyası adı ilk giriş dosyasının adını alır. A `Sub Main` yordam gerekli değildir.<br /><br /> .Winmdobj dosyası için giriş olarak kullanılmak üzere tasarlanmış <xref:Microsoft.Build.Tasks.WinMDExp> dışa aktarma Windows (WinMD) meta veri dosyası üretmek için aracı. WinMD dosyası .winmd uzantısına sahip ve bu JavaScript, C++ ve Windows çalışma zamanı kullanmak kodu özgün kitaplık ve WinMD tanımları içerir.|  
  
 Belirtmediğiniz sürece `/target:module`, `/target` neden olan bir [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] bir çıktı dosyasına eklenecek derleme bildirimi.  
  
 Vbc.exe her örneği, en fazla bir çıkış dosyası. Derleyici seçeneği gibi belirtirseniz `/out` veya `/target` birden fazla kez, derleyici işlemleri yürürlüğe koymak sonuncu. Bir derleme tüm dosyaları hakkında bilgi için bildirim eklenir. Tüm dosyaları ile oluşturulanlar dışındaki çıktı `/target:module` bildiriminde derleme meta verilerini içeriyor. Kullanım [Ildasm.exe (IL ayrıştırıcı)](https://msdn.microsoft.com/library/f7dy01k1) bir çıktı dosyasına meta verileri görüntüleyebilirsiniz.  
  
 Kısa formunu `/target` olan `/t`.  
  
### <a name="to-set-target-in-the-visual-studio-ide"></a>/ Target Visual Studio IDE'de ayarlamak için  
  
1.  Seçili bir projeyi **Çözüm Gezgini**. Üzerinde **proje** menüsünde tıklatın **özellikleri**. Daha fazla bilgi için bkz: [Proje Tasarımcısı giriş](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Tıklatın **uygulama** sekmesi.  
  
3.  Değer değiştirme **uygulama türü** kutusu.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod derlerken `in.vb`, oluşturma `in.dll`:  
  
```  
vbc /target:library in.vb  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Basic komut satırı derleyicisi](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [/ out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [/ addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [/ moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)  
 [Derlemeler ve Genel Derleme Önbelleği](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Örnek derleme komut satırları](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
