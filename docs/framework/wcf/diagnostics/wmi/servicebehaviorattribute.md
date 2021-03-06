---
title: ServiceBehaviorAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0a3bc0116ec34a3370012472c31a9191cf26f720
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="servicebehaviorattribute"></a>ServiceBehaviorAttribute
ServiceBehaviorAttribute  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>Yöntemler  
 ServiceBehaviorAttribute sınıfı herhangi bir yöntem tanımlamıyor.  
  
## <a name="properties"></a>Özellikler  
 ServiceBehaviorAttribute sınıfı aşağıdaki özelliklere sahiptir:  
  
### <a name="automaticsessionshutdown"></a>AutomaticSessionShutdown  
 Veri türü: boolean  
  
 Erişim türüne: salt okunur  
  
 Otomatik olarak bir istemci bir çıktı oturumu kapattığı zaman oturumu kapatmaya gösterir.  
  
### <a name="concurrencymode"></a>ConcurrencyMode  
 Veri türü: dize  
Erişim türüne: salt okunur  
  
 Bir hizmet bir iş parçacığı, birden çok iş parçacığı veya desteklemeyeceğini aramalar destekleyip desteklemediğini belirtir.  
  
### <a name="configurationname"></a>ConfigurationName  
 Veri türü: dize  
  
 Erişim türüne: salt okunur  
  
 Hizmet yapılandırmasının adı.  
  
### <a name="ignoreextensiondataobject"></a>ignoreExtensionDataObject  
 Veri türü: boolean  
  
 Erişim türüne: salt okunur  
  
 Bilinmeyen seri hale getirme verilerinin gönderilip gönderilmeyeceğini belirtir.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 Veri türü: boolean  
  
 Erişim türüne: salt okunur  
  
 Hata ayıklama amacıyla istemcilere döndürülen SOAP hatalarının ayrıntılı yönetilen özel durum bilgileri dahil edilip edilmeyeceğini belirtir.  
  
### <a name="instancecontextmode"></a>InstanceContextMode  
 Veri türü: dize  
  
 Erişim türüne: salt okunur  
  
 Yeni bir hizmet nesnesi oluşturulduğunda belirtir.  
  
### <a name="maxitemsinobjectgraph"></a>MaxItemsInObjectGraph  
 Veri türü: SINT32  
  
 Erişim türüne: salt okunur  
  
 Serileştirilmiş nesne içinde izin verilen öğe maksimum sayısı.  
  
### <a name="name"></a>Ad  
 Veri türü: dize  
  
 Erişim türüne: salt okunur  
  
 WSDL hizmetinde name özniteliği.  
  
### <a name="namespace"></a>Ad Alanı  
 Veri türü: dize  
  
 Erişim türüne: salt okunur  
  
 WSDL hizmetinde hedef ad alanı.  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a>ReleaseServiceInstanceOnTransactionComplete  
 Veri türü: boolean  
  
 Erişim türüne: salt okunur  
  
 Geçerli işlem tamamlandıktan sonra hizmeti nesnesi geri dönüştürüldüğünde olup olmadığını belirtir.  
  
### <a name="transactionautocompleteonsessionclose"></a>TransactionAutoCompleteOnSessionClose  
 Veri türü: boolean  
  
 Erişim türüne: salt okunur  
  
 Geçerli oturumu kapattığında bekleyen işlem tamamlandı olup olmadığını belirtir.  
  
### <a name="transactionisolationlevel"></a>TransactionIsolationLevel  
 Veri türü: dize  
  
 Erişim türüne: salt okunur  
  
 İşlem yalıtım düzeyini belirtir.  
  
### <a name="transactiontimeout"></a>TransactionTimeout  
 Veri türü: datetime  
  
 Erişim türüne: salt okunur  
  
 İçinde bir işlemin tamamlanması gereken süre.  
  
### <a name="usesynchronizationcontext"></a>UseSynchronizationContext  
 Veri türü: boolean  
  
 Erişim türüne: salt okunur  
  
 Geçerli eşitleme bağlamı iş parçacığı yürütmeyi seçmek için kullanılıp kullanılmayacağını belirtir.  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  
 Veri türü: boolean  
  
 Erişim türüne: salt okunur  
  
 Sistem veya uygulama SOAP MustUnderstand üstbilgi işlemeyi zorunlu olup olmadığını belirtir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|MOF|Bildirilen Servicemodel.mof.|  
|---------|-----------------------------------|  
|Ad Alanı|İçinde tanımlanan root\ServiceModel|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>
