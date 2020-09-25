---
title: Schemat ustawień sieci Web
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- ASP.NET configuration system, Web settings schema
- schema Web settings
- Web settings, schema [ASP.NET]
- configuration files [ASP.NET]
- configuration schema [.NET Framework], Web settings
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
ms.openlocfilehash: c3ac9b42aeff3f7b26f0b36480bc75ceda39e7e6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185603"
---
# <a name="web-settings-schema"></a><span data-ttu-id="e304f-102">Schemat ustawień sieci Web</span><span class="sxs-lookup"><span data-stu-id="e304f-102">Web Settings Schema</span></span>

<span data-ttu-id="e304f-103">Ustawienia sieci Web określają ustawienia ASP.NET procesora i wykonania, które mają zastosowanie do zachowania całego procesu zarządzanego przez warstwę hostingu ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e304f-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="e304f-104">Te ustawienia różnią się od ustawień typu domeny aplikacji, które są określone w pliku Web.config aplikacji ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e304f-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
<span data-ttu-id="e304f-105">Ustawienia sieci Web są zawarte w plikach Aspnet.config, które znajdują się w folderach instalacyjnych dla wersji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e304f-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="e304f-106">Na przykład plik Aspnet.config dla .NET Framework 2,0 znajduje się w następującym folderze:</span><span class="sxs-lookup"><span data-stu-id="e304f-106">For example, the Aspnet.config file for .NET Framework 2.0 is in the following folder:</span></span>  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
<span data-ttu-id="e304f-107">Ustawienia sieci Web nie są używane w innych plikach konfiguracyjnych, takich jak plik machine.config, główny Web.config lub pliki Web.config na poziomie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e304f-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<applicationPool>**](applicationpool-element-web-settings.md)

|<span data-ttu-id="e304f-108">Element</span><span class="sxs-lookup"><span data-stu-id="e304f-108">Element</span></span>|<span data-ttu-id="e304f-109">Opis</span><span class="sxs-lookup"><span data-stu-id="e304f-109">Description</span></span>|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|<span data-ttu-id="e304f-110">Zawiera informacje, które są używane przez warstwę hostingu ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e304f-110">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|<span data-ttu-id="e304f-111">Określa ustawienia ASP.NET na poziomie procesora i wykonania, które mają zastosowanie do zachowania całego procesu zarządzanego przez warstwę hostingu ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e304f-111">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e304f-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e304f-112">See also</span></span>

- [<span data-ttu-id="e304f-113">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="e304f-113">Configuration File Schema</span></span>](../index.md)
