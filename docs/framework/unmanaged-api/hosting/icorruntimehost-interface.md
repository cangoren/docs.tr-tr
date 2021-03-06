---
title: ICorRuntimeHost Arabirimi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost
helpviewer_keywords: ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 844648cd2cfafc561e27bea870703ee3a55fb404
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehost-interface"></a>ICorRuntimeHost Arabirimi
Ortak dil çalışma zamanı (CLR) oluşturmak ve uygulama etki alanları, varsayılan etki alanı erişmek ve tüm etki alanları işlemde çalışan listeleme için yapılandırmak için açıkça durdurmak ve başlatmak ana bilgisayar sağlayan yöntemler sağlar.  
  
 .NET Framework sürüm 2. 0'da, bu arabirim tarafından kılınan [Iclrruntimehost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[CloseEnum yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|Bir etki alanı Numaralandırıcı geri etki alanı listesi başlangıç durumuna sıfırlar.|  
|[CreateDomain yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|Uygulama etki alanı oluşturur. Çağıran bir arabirim işaretçisi türü alan <xref:System._AppDomain> türünün bir örneği için <xref:System.AppDomain?displayProperty=nameWithType>.|  
|[CreateDomainEx yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|Uygulama etki alanı oluşturur. Bu yöntem döndürülen ek özelliklerini yapılandırmak için Iappdomainsetup örneği geçirmek arayan sağlar <xref:System._AppDomain> örneği.|  
|[CreateDomainSetup yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|Arabirim işaretçisi türü alır `IAppDomainSetup` için bir <xref:System.AppDomainSetup> örneği. `IAppDomainSetup`uygulama etki alanı yönlerini oluşturulmadan önce yapılandırmak için yöntemleri sağlar.|  
|[CreateEvidence yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|Arabirim işaretçisi türü alır <xref:System.Security.Principal.IIdentity>, geçirilecek güvenlik bulgu oluşturmak için ana sağlayan [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) veya [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).|  
|[CreateLogicalThreadState yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|Kullanmayın.|  
|[CurrentDomain yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|Arabirim işaretçisi türü alır <xref:System._AppDomain> geçerli iş parçacığı üzerinde yüklenen etki alanı temsil eder.|  
|[DeleteLogicalThreadState yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|Kullanmayın.|  
|[EnumDomains yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|Bir Numaralandırıcı geçerli işlem için etki alanları alır.|  
|[GetConfiguration yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|CLR geri çağırma yapılandırmasını belirtmek ana bilgisayar tanır bir nesneyi alır.|  
|[GetDefaultDomain yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|Arabirim işaretçisi türü alır <xref:System._AppDomain> , geçerli işlem için varsayılan etki alanını temsil eder.|  
|[LocksHeldByLogicalThread yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|Kullanmayın.|  
|[MapFile yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|Belirtilen dosya belleğe eşler. Bu yöntem artık kullanılmıyor.|  
|[NextDomain yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|Arabirim işaretçisi sonraki etki alanına numaralandırmada alır.|  
|[Start yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|CLR başlatır.|  
|[Stop yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|Geçerli işlem için çalışma zamanında kod yürütmeyi durdurur.|  
|[Switchınlogicalthreadstate yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|Kullanmayın.|  
|[SwitchOutLogicalThreadState yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|Kullanmayın.|  
|[UnloadDomain yöntemi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|Belirtilen uygulama etki alanından geçerli işlem kaldırır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:** 1.0, 1.1  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.AppDomain>  
 [Barındırma](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [Iclrruntimehost arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [Çalışma zamanı ana bilgisayarlar](http://msdn.microsoft.com/en-us/99d9246a-b994-4fe5-985c-8588d1d59998)  
 [Barındırma arabirimleri](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Corruntimehost ortak sınıfı](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
