---
title: "Dosya Sistemi ve .NET Framework Dosyası G/Ç ile İlgili Temel Bilgiler (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- file access, file I/O in Visual Basic
- file attributes, determining
- streams, fundamental operations
- file permissions
- streams
- streams, definition
ms.assetid: 49d837c0-cf28-416f-8606-4d83d7b479ef
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53bd56647d04c40c44a240edcd084f0719c3d4aa
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/09/2017
---
# <a name="basics-of-net-framework-file-io-and-the-file-system-visual-basic"></a>Dosya Sistemi ve .NET Framework Dosyası G/Ç ile İlgili Temel Bilgiler (Visual Basic)
Sınıfları <xref:System.IO> ad alanı, sürücüler, dosyaları ve dizinleri ile çalışmak için kullanılır.  
  
 <xref:System.IO> Ad alanında <xref:System.IO.File> ve <xref:System.IO.Directory> sağlayan sınıflar [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] dosyaları ve dizinleri yöneten işlevselliği. Nedeni bu nesnelerin yöntemleri statik veya paylaşılan üyeler, bunları doğrudan sınıfının bir örneği ilk kez oluşturmadan kullanabilirsiniz. Bu sınıfların ile ilişkili olan <xref:System.IO.FileInfo> ve <xref:System.IO.DirectoryInfo> kullanıcıları için tanıdık gelecektir sınıfları `My` özelliği. Bu sınıfların kullanmak için tam olarak adları nitelemeniz veya içeri aktarmanız gerekir uygun ad alanlarını dahil ederek `Imports` başında deyim etkilenen kod. Daha fazla bilgi için bkz: [Imports deyimi (.NET Namespace ve türü)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
> [!NOTE]
>  Diğer konular bu bölüm kullanım `My.Computer.FileSystem` yerine nesne `System.IO` sürücüsü, dosyalar ve dizinler ile çalışmak için sınıflar. `My.Computer.FileSystem` Nesnesi, öncelikli olarak kullanılmak üzere tasarlanmıştır [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programlar. `System.IO`sınıfları destekleyen herhangi bir dil tarafından kullanıma yöneliktir [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]gibi [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
## <a name="definition-of-a-stream"></a>Bir akış tanımı  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Okuma ve dosyalara yazma desteklemek için akışlarını kullanır. Tek boyutlu bir başlangıç ve bitiş tarihi olan ve burada imleci akışında geçerli konumu gösterir bitişik veri kümesi olarak akışı düşünebilirsiniz.  
  
 ![İmleç akışında geçerli konumu gösterir. ] (../../../../visual-basic/developing-apps/programming/drives-directories-files/media/filestream.gif "FILESTREAM")  
  
## <a name="stream-operations"></a>Akış işlemleri  
 Akış içinde bulunan verileri, bellek, bir dosya ya da bir TCP/IP'yi yuva gelebilir. Akışlar için uygulanabilir temel işlemler vardır:  
  
-   Okuma. Bir dize veya bir bayt dizisi gibi bir veri yapıda akıştan veri aktarırken bir akıştan okuyabilir.  
  
-   **Yazma**. Akışa bir veri kaynağından veri aktarırken bir akışa yazabilirsiniz.  
  
-   **Aramayı**. Sorgulamak ve konumunuzu akışında değiştirin.  
  
 Daha fazla bilgi için bkz: [oluşturma akışları](../../../../../docs/standard/io/composing-streams.md).  
  
## <a name="types-of-streams"></a>Akışlar türleri  
 İçinde [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], bir akış tarafından temsil edilen <xref:System.IO.Stream> diğer tüm akışlar için Özet sınıf forms sınıfı. Doğrudan bir örneğini oluşturamaz <xref:System.IO.Stream> sınıfı, ancak bunu uygulayan sınıflar birini kullanmanız gerekir.  
  
 Akışlar türlerde vardır, ancak dosya giriş/çıkış ile (g/ç) çalışma amacıyla, en önemli türleridir <xref:System.IO.FileStream> bir şekilde okuma ve dosyalara yazmasını sağlar, sınıf ve <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> dosyaları oluşturmak için bir yol sağlayan sınıfı ve yalıtılmış depolamada dizinleri. Dosya g/ç ile çalışırken, kullanılabilir diğer akışlar şunları içerir:  
  
-   <xref:System.IO.BufferedStream>  
  
-   <xref:System.Security.Cryptography.CryptoStream>  
  
-   <xref:System.IO.MemoryStream>  
  
-   <xref:System.Net.Sockets.NetworkStream>.  
  
 Aşağıdaki tablo olan bir akış sık gerçekleştirilen görevleri listeler:  
  
|Bitiş|Bkz. |
|---|---|   
|Okuma ve bir veri dosyasına yazma|[Nasıl yapılır: Okuma ve yeni oluşturulan veri dosyasına yazma](../../../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)|  
|Bir dosyadan metin okuma|[Nasıl yapılır: dosyadan metin okuma](../../../../../docs/standard/io/how-to-read-text-from-a-file.md)|  
|Bir dosyaya metin yazma|[Nasıl yapılır: bir dosyaya metin yazma](../../../../../docs/standard/io/how-to-write-text-to-a-file.md)|  
|Bir dizeden karakterleri okuma|[Nasıl yapılır: bir dizeden karakterleri okuma](../../../../../docs/standard/io/how-to-read-characters-from-a-string.md)|  
|Karakterleri dizeye yazma|[Nasıl yapılır: bir dizeye karakter yazma](../../../../../docs/standard/io/how-to-write-characters-to-a-string.md)|  
|Veri şifreleme|[Veri şifreleme](../../../../../docs/standard/security/encrypting-data.md)|  
|Verilerin şifresini|[Verilerin şifresini çözme](../../../../../docs/standard/security/decrypting-data.md)|  
  
## <a name="file-access-and-attributes"></a>Dosya erişimi ve öznitelikleri  
 Nasıl dosyaları, açık olan paylaşılan oluşturulduğunu ve kontrol edebilirsiniz <xref:System.IO.FileAccess>, <xref:System.IO.FileMode>, ve <xref:System.IO.FileShare> oluşturucular tarafından kullanılan bayrak içeren numaralandırmalar <xref:System.IO.FileStream> sınıfı. Örneğin, açtığınızda veya yeni bir <xref:System.IO.FileStream>, <xref:System.IO.FileMode> numaralandırma, dosya ekleme için açılıp açılmayacağını dosyanın üzerine olup belirtilen dosya mevcut değilse yeni bir dosya oluşturulur olup olmadığını belirlemek için ve benzeri sağlar.  
  
 <xref:System.IO.FileAttributes> Dosya özgü bilgileri toplanıyor etkinleştirir. <xref:System.IO.FileAttributes> Numaralandırma sıkıştırılmış şifrelenmiş, gizli, salt okunur olup, bir arşiv, bir dizin, bir sistem dosyası veya geçici bir dosya gibi dosyanın saklı öznitelikleri döndürür.  
  
 Aşağıdaki tabloda dosya erişimi ve dosya özniteliklerini içeren görevler listelenmektedir:  
  
|Bitiş|Bkz. |  
|---|---|
|Açın ve bir günlük dosyasına metin ekleme|[Nasıl yapılır: açın ve bir günlük dosyasına Ekle](../../../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)|  
|Bir dosyanın özniteliklerini belirleme|<xref:System.IO.FileAttributes>|  
  
## <a name="file-permissions"></a>Dosya izinleri  
 İle dosya ve dizinleri erişimini denetleme yapılabilir <xref:System.Security.Permissions.FileIOPermission> sınıfı. Bu, bir parçası olarak oluşturulan ASPNET adlı özel bir yerel kullanıcı hesabı bağlamı içinde çalıştırılır varsayılan Web Forms ile çalışan geliştiriciler için özellikle önemlidir olabilir [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] ve [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] yüklemeleri. Bu tür bir uygulama erişme isteğinde bulunduğunda bir kaynağa, ASPNET kullanıcı hesabı kullanıcının bir Web uygulamasından bir dosyaya yazmak gibi eylemleri gerçekleştirmesini engelleyebilir izinleri sınırlıdır. Daha fazla bilgi için bkz: [güvenlik izinleri](http://msdn.microsoft.com/en-us/b03757b4-e926-4196-b738-3733ced2bda0)ve <xref:System.Security.Permissions.FileIOPermission>.  
  
## <a name="isolated-file-storage"></a>Yalıtılmış dosya depolama  
 Yalıtılmış Depolama burada kullanıcı veya kod gerekli izinlere sahip olmayabilir dosyaları ile çalışırken, oluşturulan sorunları çözmek için bir denemedir. Yalıtılmış Depolama her kullanıcıya bir veya daha fazla depoları tutabilen veri bölme atar. Depoları birbirinden derleme ve kullanıcı tarafından yalıtılmış olabilir. Yalnızca kullanıcı ve bir depo oluşturulduğuna derleme erişime sahiptir. Bir mağaza tam sanal dosya sistemi gibi davranan — bir deposu içinde oluşturabilir ve dizinleri ve dosyaları değiştirmek.  
  
 Aşağıdaki tabloda, yaygın olarak yalıtılmış file storage ile ilişkili görevleri listeler.  
  
|Bitiş|Bkz. |
|---|---|  
|Yalıtılmış depolama alanı oluşturun|[Nasıl yapılır: yalıtılmış depolama için depoları alın](../../../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)|  
|Yalıtılmış depoları listeleme|[Nasıl yapılır: yalıtılmış depolama için depoları listeleme](../../../../../docs/standard/io/how-to-enumerate-stores-for-isolated-storage.md)|  
|Yalıtılmış depolamada Sil|[Nasıl yapılır: yalıtılmış depolamadaki depoları silme](../../../../../docs/standard/io/how-to-delete-stores-in-isolated-storage.md)|  
|Yalıtılmış depolamada dosya veya dizin oluşturma|[Nasıl yapılır: yalıtılmış depolamada dosyalar ve dizinler oluşturma](../../../../../docs/standard/io/how-to-create-files-and-directories-in-isolated-storage.md)|  
|Yalıtılmış depolamada dosya bulma|[Nasıl yapılır: yalıtılmış depolamada mevcut dosya ve dizinleri bulma](../../../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md)|  
|Okuma veya insolated depolama dosyasında yazma|[Nasıl yapılır: yalıtılmış depolamadaki dosyaları yönelik Okuma ve yazma](../../../../../docs/standard/io/how-to-read-and-write-to-files-in-isolated-storage.md)|  
|Bir dosya veya dizin yalıtılmış depolamada Sil|[Nasıl yapılır: dosya ve dizinleri yalıtılmış depolamada silme](../../../../../docs/standard/io/how-to-delete-files-and-directories-in-isolated-storage.md)|  
  
## <a name="file-events"></a>Dosya olayları  
 <xref:System.IO.FileSystemWatcher> Bileşeni, dosyalar ve dizinler sisteminizde veya olan ağ erişimi herhangi bir bilgisayarda değişiklikleri izlemek sağlar. Örneğin, bir dosya değiştirilirse, bir kullanıcı değişiklik gerçekleştikten bir uyarı göndermek isteyebilirsiniz. Değişiklikler olduğunda, bir veya daha fazla olay gerçekleşti, arabellekte depolanan ve karmalayan <xref:System.IO.FileSystemWatcher> işleme için bileşen.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akışlar oluşturma](../../../../../docs/standard/io/composing-streams.md)  
 [Dosya ve akış g/ç](https://msdn.microsoft.com/library/k3352a4t)  
 [Zaman uyumsuz dosya g/ç](https://msdn.microsoft.com/library/kztecsys)  
 [.NET Framework dosyası g/ç ve dosya sistemi (Visual Basic) de kullanılan sınıflar](../../../../visual-basic/developing-apps/programming/drives-directories-files/classes-used-in-net-framework-file-io-and-the-file-system.md)
