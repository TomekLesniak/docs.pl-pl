---
title: <system.serviceModel.activation>
ms.date: 03/30/2017
ms.assetid: c0cae85f-56cb-4030-8807-6f96edff8d2d
ms.openlocfilehash: cbb12ce84f53f55f7d5b2dabd449a116969dc9b8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157138"
---
# \<system.serviceModel.activation>

<span data-ttu-id="b9d5c-102">Ta sekcja konfiguracji reprezentuje ustawienia konfiguracji narzędzia SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="b9d5c-102">This configuration section represents the configuration settings for the SMSvcHost.exe tool.</span></span> <span data-ttu-id="b9d5c-103">Elementy konfiguracji można skonfigurować w pliku SMSvcHost.exe.config.</span><span class="sxs-lookup"><span data-stu-id="b9d5c-103">The configuration elements can be configured in the SMSvcHost.exe.config file.</span></span> <span data-ttu-id="b9d5c-104">Obejmuje to wszystkie ustawienia dotyczące całego komputera, które należy skonfigurować.</span><span class="sxs-lookup"><span data-stu-id="b9d5c-104">Specifically, it includes all machine-wide settings that must be configured.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.serviceModel.activation>**  
  
## <a name="sample-configuration-file"></a><span data-ttu-id="b9d5c-105">Przykładowy plik konfiguracji</span><span class="sxs-lookup"><span data-stu-id="b9d5c-105">Sample Configuration File</span></span>  

 <span data-ttu-id="b9d5c-106">Poniżej znajduje się przykładowy plik konfiguracji (SMSvcHost.exe.config), który jest używany przez proces odbiornika SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="b9d5c-106">The following is a sample configuration file (SMSvcHost.exe.config), which is used by the listener process SMSvcHost.exe.</span></span>  
  
```xml  
<configuration>
  <runtime>
    <gcConcurrent enabled="false" />
  </runtime>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="10"
             maxPendingAccepts="2"
             maxPendingConnections="100"
             receiveTimeout="00:00:10"
             teredoEnabled="false">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
    <net.pipe maxConnectionsPendingDispatch="100"
              maxPendingAccepts="2"
              receiveTimeout="00:00:10">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
    <diagnostics performanceCountersEnabled="true" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="b9d5c-107">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b9d5c-107">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration>
