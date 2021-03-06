---
title: "缓解：minFreeMemoryPercentageToActiveService 配置设置 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7875f26-0da8-4afe-9846-7a21778f757b
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 783dd4fb28f1590722833ce9a456b9c2c76ecd80
ms.contentlocale: zh-cn
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-minfreememorypercentagetoactiveservice-configuration-setting"></a>缓解：minFreeMemoryPercentageToActiveService 配置设置
在 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 中，如果 Web 服务器上的可用内存小于 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 配置设置指定的百分比，则会导致异常抛出。 在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中，已忽略此设置。  
  
## <a name="impact"></a>影响  
 在大多数情况下，遵循 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 设置的影响是可取的：可防止在有内存约束的系统上启动 Windows Communication Foundation (WCF) 服务时导致 <xref:System.OutOfMemoryException> 异常抛出，从而提高系统稳定性。  
  
 但是在某些情况下，以前成功启动的服务可能会无法启动。 在这种情况下，会显示详细错误消息：  
  
```console
Memory gates checking failed because the free memory (nnnn bytes) is less than nn% of total memory. As a result, the service will not be available for incoming requests. To resolve this, either reduce the load on the machine or adjust the value of minFreeMemoryPercentageToActivateService on the serviceHostingEnvironment config element.
```
  
## <a name="mitigation"></a>缓解操作  
 若要还原为忽略 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 设置的旧行为，请按如下所示修改 web.config 文件：  
  
```xml
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"   
                           minFreeMemoryPercentageToActivateService="0">  
   <serviceActivations>  
   ...  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a>另请参阅  
 [运行时更改](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)

