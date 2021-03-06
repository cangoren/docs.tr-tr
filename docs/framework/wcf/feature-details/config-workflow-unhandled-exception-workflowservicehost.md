---
title: "Nasıl yapılır: WorkflowServiceHost ile İş Akışı Tarafından İşlenmeyen Özel Durum Davranışını Yapılandırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9e85f8010528d18133ccd9d98de8479ea0de343d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a>Nasıl yapılır: WorkflowServiceHost ile İş Akışı Tarafından İşlenmeyen Özel Durum Davranışını Yapılandırma
<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> Barındırılan bir iş akışı içinde işlenmeyen bir özel durum oluşursa, gerçekleştirilecek eylemi belirtmenize olanak tanıyan bir davranıştır <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Bu konuda, bir yapılandırma dosyasında bu davranışı yapılandırmak gösterilmiştir.  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a>WorkflowUnhandledExceptionBehavior yapılandırmak için  
  
1.  Ekleme bir <`workflowUnhandledException`> öğesinde bir <`behavior`> öğesi içinde bir <`serviceBehaviors`> öğesini kullanarak `action` özniteliği aşağıdaki örnekte gösterildiği gibi işlenmeyen bir özel durum meydana geldiğinde eylemi belirtin.  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    >  Önceki yapılandırma örneği Basitleştirilmiş yapılandırma kullanıyor. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Basitleştirilmiş yapılandırma](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     Bu davranış, aşağıdaki örnekte gösterildiği gibi kodda yapılandırılabilir.  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     `action` Özniteliği <`workflowUnhandledException`> öğesi aşağıdaki değerlerden birine ayarlanabilir:  
  
     **İptal Et**  
     (Bu son kalan noktasına geri olan) kalıcı örneği durumu dokunmadan bellek örneğinde durdurur.  
  
     **abandonAndSuspend**  
     Bellek örneğinde durdurur ve askıya alınmasına kalıcı örneğini güncelleştirir.  
  
     **İptal**  
     İptal işleyicileri için örneği çağırır ve ayrıca örneği Mağazası'ndan kaldırabilir bellek örneğinde tamamlar  
  
     **sonlandırma**  
     Bellek örneğinde tamamlanır ve örnek deposundan kaldırır.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, bkz: [iş akışı hizmeti konak genişletilebilirliği](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş akışı hizmeti konak genişletilebilirliği](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [İş akışı Hizmetleri](../../../../docs/framework/wcf/feature-details/workflow-services.md)
