---
title: "Nasıl yapılır: Hizmet Uç Noktalarından Meta Verileri Dışarı Aktarma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b6c4dfd0-f270-43ec-961a-e16eb6af2f2c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 684d9bcf2e4787457a6ef3251e0202e1559561b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-export-metadata-from-service-endpoints"></a>Nasıl yapılır: Hizmet Uç Noktalarından Meta Verileri Dışarı Aktarma
Bu konu hizmet uç noktalarından meta verileri dışarı aktarma açıklar.  
  
### <a name="to-export-metadata-from-service-endpoints"></a>Hizmet uç noktalarından meta verileri dışarı aktarmak için  
  
1.  Yeni Visual Studio konsol uygulama projesi oluşturun. Aşağıdaki adımlarda main() yönteminin içinde oluşturulan Program.cs dosyasında gösterilen kodu ekleyin.  
  
2.  Oluşturma bir <xref:System.ServiceModel.Description.WsdlExporter>.  
  
     [!code-csharp[S_UEWsdlExporter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#1)]
     [!code-vb[S_UEWsdlExporter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#1)]  
  
3.  Ayarlama <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> özelliğini değerlerinden birine <xref:System.ServiceModel.Description.PolicyVersion> numaralandırması. Bu örnek değeri ayarlar <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> WS-Policy 1.5 karşılık gelir.  
  
     [!code-csharp[S_UEWsdlExporter#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#2)]
     [!code-vb[S_UEWsdlExporter#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#2)]  
  
4.  Bir dizi oluşturmak <xref:System.ServiceModel.Description.ServiceEndpoint> nesneleri.  
  
     [!code-csharp[S_UEWsdlExporter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#3)]
     [!code-vb[S_UEWsdlExporter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#3)]  
  
5.  Her hizmet uç noktası için meta verileri dışa aktarın.  
  
     [!code-csharp[S_UEWsdlExporter#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#4)]
     [!code-vb[S_UEWsdlExporter#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#4)]  
  
6.  Verme işlemi sırasında bir hata oluşmamıştır emin olun ve meta verilerini almak için denetleyin.  
  
     [!code-csharp[S_UEWsdlExporter#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#5)]
     [!code-vb[S_UEWsdlExporter#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#5)]  
  
7.  Artık meta çağırarak bir dosyaya yazmak gibi kullanabilirsiniz <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29> yöntemi.  
  
## <a name="example"></a>Örnek  
 Bu örnek için listeleme tam kod aşağıda verilmiştir.  
  
 [!code-csharp[S_UEWsdlExporter#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#0)]
 [!code-vb[S_UEWsdlExporter#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#0)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Program.cs başvuru System.ServiceModel.dll derlerken.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Meta veri mimarisi genel bakış](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)  
 [Meta verilerini kullanma](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [Uç noktalar: Adresler, bağlamalar ve sözleşmeler](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
