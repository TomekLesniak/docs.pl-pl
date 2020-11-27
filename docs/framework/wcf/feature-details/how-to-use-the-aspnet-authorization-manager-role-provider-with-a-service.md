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
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a><span data-ttu-id="d633f-102">Instrukcje: używanie dostawcy roli menedżera autoryzacji platformy ASP.NET za pomocą usługi</span><span class="sxs-lookup"><span data-stu-id="d633f-102">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>

<span data-ttu-id="d633f-103">Gdy usługa ASP.NET hostuje usługę sieci Web, można zintegrować Menedżera autoryzacji z aplikacją w celu zapewnienia autoryzacji usługi.</span><span class="sxs-lookup"><span data-stu-id="d633f-103">When ASP.NET hosts a Web service, you can integrate Authorization Manager into the application to provide authorization to the service.</span></span> <span data-ttu-id="d633f-104">Menedżer autoryzacji pozwala deweloperowi aplikacji definiować poszczególne operacje, które mogą być zgrupowane razem z zadaniami formularza.</span><span class="sxs-lookup"><span data-stu-id="d633f-104">Authorization Manager enables an application developer to define individual operations, which can be grouped together to form tasks.</span></span> <span data-ttu-id="d633f-105">Administrator może następnie autoryzować role do wykonywania określonych zadań lub poszczególnych operacji.</span><span class="sxs-lookup"><span data-stu-id="d633f-105">An administrator can then authorize roles to perform specific tasks or individual operations.</span></span> <span data-ttu-id="d633f-106">Menedżer autoryzacji udostępnia narzędzie administracyjne jako przystawkę programu Microsoft Management Console (MMC) do zarządzania rolami, zadaniami, operacjami i użytkownikami.</span><span class="sxs-lookup"><span data-stu-id="d633f-106">Authorization Manager provides an administration tool as a Microsoft Management Console (MMC) snap-in to manage roles, tasks, operations, and users.</span></span> <span data-ttu-id="d633f-107">Administratorzy konfigurują Magazyn zasad Menedżera autoryzacji w pliku XML, Active Directory lub w sklepie Active Directory Application Mode (ADAM).</span><span class="sxs-lookup"><span data-stu-id="d633f-107">Administrators configure an Authorization Manager policy store in an XML file, Active Directory, or in an Active Directory Application Mode (ADAM) store.</span></span>  
  
 <span data-ttu-id="d633f-108">Menedżer autoryzacji jest zintegrowany z aplikacją przez skonfigurowanie dostawcy roli ASP.NET Menedżera autoryzacji dla aplikacji ASP.NET, która obsługuje usługę sieci Web.</span><span class="sxs-lookup"><span data-stu-id="d633f-108">Authorization Manager is Integrated into the application by configuring the Authorization Manager ASP.NET role provider for the ASP.NET application that is hosting the Web service.</span></span> <span data-ttu-id="d633f-109">Podobnie jak w przypadku innych dostawców ról ASP.NET, dostawca roli ASP.NET Menedżera autoryzacji jest konfigurowany przy użyciu `providers` elementu> <.</span><span class="sxs-lookup"><span data-stu-id="d633f-109">Like other ASP.NET role providers, the Authorization Manager ASP.NET role provider is configured using the <`providers`> element.</span></span>  
  
 <span data-ttu-id="d633f-110">Poniższy przykład kodu jest częścią pliku konfiguracji usługi sieci Web, która integruje Menedżera autoryzacji z aplikacją.</span><span class="sxs-lookup"><span data-stu-id="d633f-110">The following code example is a portion of a configuration file for a Web service that is integrating Authorization Manager into the application.</span></span>  
  
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
  
 <span data-ttu-id="d633f-111">Aby uzyskać więcej informacji na temat integrowania dostawcy roli ASP.NET z aplikacją WCF, zobacz [How to: Use the ASP.NET role Provider with a Service](how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="d633f-111">For more information about integrating an ASP.NET role provider with a WCF application, see [How to: Use the ASP.NET Role Provider with a Service](how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span> <span data-ttu-id="d633f-112">Aby uzyskać więcej informacji o korzystaniu z Menedżera autoryzacji z ASP.NET, zobacz [How to: use Menedżer autoryzacji (AzMan) z ASP.NET 2,0](/previous-versions/msp-n-p/ff649313(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="d633f-112">For more information about using Authorization Manager with ASP.NET, see [How to: Use Authorization Manager (AzMan) with ASP.NET 2.0](/previous-versions/msp-n-p/ff649313(v=pandp.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d633f-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d633f-113">See also</span></span>

- [<span data-ttu-id="d633f-114">Instrukcje: używanie dostawcy ról ASP.NET razem z usługą</span><span class="sxs-lookup"><span data-stu-id="d633f-114">How to: Use the ASP.NET Role Provider with a Service</span></span>](how-to-use-the-aspnet-role-provider-with-a-service.md)
