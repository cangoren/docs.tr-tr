---
title: "Nasıl yapılır: Görüntü Meta Verilerini Okuma"
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
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9df2866251e08b8989f8550d045b587c9de8d2cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-image-metadata"></a>Nasıl yapılır: Görüntü Meta Verilerini Okuma
Bazı resim dosyaları görüntü özelliklerini belirlemek için okuyabilir meta veriler içerir. Örneğin, dijital bir fotoğraf marka ve model görüntüsünü yakalamak için kullanılan kamera belirlemek için okuyabilir meta verileri içerebilir. İle [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], var olan meta verileri okuyabilir ve resim dosyaları için yeni meta verileri de yazabilirsiniz.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]meta verilerde tek bir parçasını depolayan bir <xref:System.Drawing.Imaging.PropertyItem> nesnesi. Okuyabilirsiniz <xref:System.Drawing.Image.PropertyItems%2A> özelliği bir <xref:System.Drawing.Image> bir dosyanın tüm meta verilerini almak için nesne. <xref:System.Drawing.Image.PropertyItems%2A> Özelliği bir dizi döndürür <xref:System.Drawing.Imaging.PropertyItem> nesneleri.  
  
 A <xref:System.Drawing.Imaging.PropertyItem> nesnesi aşağıdaki dört özelliklere sahiptir: `Id`, `Value`, `Len`, ve `Type`.  
  
## <a name="id"></a>Kimliği  
 Meta veri öğesi tanımlayan etiket. Atanabilir bazı değerler <xref:System.Drawing.Imaging.PropertyItem.Id%2A> aşağıdaki tabloda gösterilmiştir.  
  
|Onaltılık değeri|Açıklama|  
|-----------------------|-----------------|  
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Görüntü başlığı<br /><br /> Donanım üreticisi<br /><br /> Donanım modeli<br /><br /> ExifDTOriginal<br /><br /> EXIF Etkilenme zamanı<br /><br /> Aydınlatma tablosu<br /><br /> Chrominance tablosu|  
  
## <a name="value"></a>Değer  
 Değerleri dizisi. Değerlerin biçimi tarafından belirlenen <xref:System.Drawing.Imaging.PropertyItem.Type%2A> özelliği.  
  
## <a name="len"></a>Len  
 Tarafından uzunluğu (bayt cinsinden) değerleri dizisi işaret için <xref:System.Drawing.Imaging.PropertyItem.Value%2A> özelliği.  
  
## <a name="type"></a>Tür  
 Tarafından dizideki veri türünü işaret için `Value` özelliği. Biçimler belirtilen tarafından `Type` özellik değerleri aşağıdaki tabloda gösterilen  
  
|Sayısal değer|Açıklama|  
|-------------------|-----------------|  
|1.|A`Byte`|  
|2|Bir dizi `Byte` ASCII olarak kodlanmış nesneleri|  
|3|Bir 16 bit tam sayı|  
|4|Bir 32 bit tamsayı|  
|5|İki bir dizi `Byte` rasyonel sayıyı temsil eden nesneler|  
|6|Kullanılan değil|  
|7|Tanımlanmamış|  
|8|Kullanılan değil|  
|9|`SLong`|  
|10|`SRational`|  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneğinde okur ve dosyadaki meta veriler yedi parçalarını görüntüler `FakePhoto.jpg`. Listede ikinci (dizin 1) özelliği öğesi var. <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (donanım üreticisi) ve <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII kodlu bayt dizesi). Kod örneği, bu özellik öğesinin değeri görüntüler.  
  
 Kod aşağıdakine benzer bir çıktı üretir:  
  
 `Property Item 0`  
  
 `id: 0x320`  
  
 `type: 2`  
  
 `length: 16 bytes`  
  
 `Property Item 1`  
  
 `id: 0x10f`  
  
 `type: 2`  
  
 `length: 17 bytes`  
  
 `Property Item 2`  
  
 `id: 0x110`  
  
 `type: 2`  
  
 `length: 7 bytes`  
  
 `Property Item 3`  
  
 `id: 0x9003`  
  
 `type: 2`  
  
 `length: 20 bytes`  
  
 `Property Item 4`  
  
 `id: 0x829a`  
  
 `type: 5`  
  
 `length: 8 bytes`  
  
 `Property Item 5`  
  
 `id: 0x5090`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `Property Item 6`  
  
 `id: 0x5091`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `The equipment make is Northwind Camera.`  
  
### <a name="code"></a>Kod  
 [!code-csharp[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Önceki örnekte Windows Forms ile kullanılmak üzere tasarlanmış ve gerektirip <xref:System.Windows.Forms.PaintEventArgs> `e`, parametre olarak olduğu <xref:System.Windows.Forms.Control.Paint> olay işleyicisi. Formun işlemek <xref:System.Windows.Forms.Control.Paint> olay ve bu kodu boyama olay işleyicisi yapıştırın. Değiştirmeniz gereken `FakePhoto.jpg` görüntü adı ve yolu, sistem ve içeri aktarma geçerli olan `System.Drawing.Imaging` ad alanı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Resimler, bit eşlemler ve meta dosyaları](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Resimler, bit eşlemler, simgeler ve meta dosyaları ile çalışma](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
