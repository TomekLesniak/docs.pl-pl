---
title: 'Instrukcje: używanie dostawcy roli menedżera autoryzacji platformy ASP.NET za pomocą usługi'
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: bbdafdd96a32b41d7c6892944ed872e3f8702f0e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280601"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>Instrukcje: używanie dostawcy roli menedżera autoryzacji platformy ASP.NET za pomocą usługi

Gdy usługa ASP.NET hostuje usługę sieci Web, można zintegrować Menedżera autoryzacji z aplikacją w celu zapewnienia autoryzacji usługi. Menedżer autoryzacji pozwala deweloperowi aplikacji definiować poszczególne operacje, które mogą być zgrupowane razem z zadaniami formularza. Administrator może następnie autoryzować role do wykonywania określonych zadań lub poszczególnych operacji. Menedżer autoryzacji udostępnia narzędzie administracyjne jako przystawkę programu Microsoft Management Console (MMC) do zarządzania rolami, zadaniami, operacjami i użytkownikami. Administratorzy konfigurują Magazyn zasad Menedżera autoryzacji w pliku XML, Active Directory lub w sklepie Active Directory Application Mode (ADAM).  
  
 Menedżer autoryzacji jest zintegrowany z aplikacją przez skonfigurowanie dostawcy roli ASP.NET Menedżera autoryzacji dla aplikacji ASP.NET, która obsługuje usługę sieci Web. Podobnie jak w przypadku innych dostawców ról ASP.NET, dostawca roli ASP.NET Menedżera autoryzacji jest konfigurowany przy użyciu `providers` elementu> <.  
  
 Poniższy przykład kodu jest częścią pliku konfiguracji usługi sieci Web, która integruje Menedżera autoryzacji z aplikacją.  
  
```xml  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 Aby uzyskać więcej informacji na temat integrowania dostawcy roli ASP.NET z aplikacją WCF, zobacz [How to: Use the ASP.NET role Provider with a Service](how-to-use-the-aspnet-role-provider-with-a-service.md). Aby uzyskać więcej informacji o korzystaniu z Menedżera autoryzacji z ASP.NET, zobacz [How to: use Menedżer autoryzacji (AzMan) z ASP.NET 2,0](/previous-versions/msp-n-p/ff649313(v=pandp.10)).  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: używanie dostawcy ról ASP.NET razem z usługą](how-to-use-the-aspnet-role-provider-with-a-service.md)
