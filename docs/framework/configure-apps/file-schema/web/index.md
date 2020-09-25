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
# <a name="web-settings-schema"></a>Schemat ustawień sieci Web

Ustawienia sieci Web określają ustawienia ASP.NET procesora i wykonania, które mają zastosowanie do zachowania całego procesu zarządzanego przez warstwę hostingu ASP.NET. Te ustawienia różnią się od ustawień typu domeny aplikacji, które są określone w pliku Web.config aplikacji ASP.NET.  
  
Ustawienia sieci Web są zawarte w plikach Aspnet.config, które znajdują się w folderach instalacyjnych dla wersji .NET Framework. Na przykład plik Aspnet.config dla .NET Framework 2,0 znajduje się w następującym folderze:  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
Ustawienia sieci Web nie są używane w innych plikach konfiguracyjnych, takich jak plik machine.config, główny Web.config lub pliki Web.config na poziomie aplikacji.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<applicationPool>**](applicationpool-element-web-settings.md)

|Element|Opis|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|Zawiera informacje, które są używane przez warstwę hostingu ASP.NET.|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|Określa ustawienia ASP.NET na poziomie procesora i wykonania, które mają zastosowanie do zachowania całego procesu zarządzanego przez warstwę hostingu ASP.NET.|  
  
## <a name="see-also"></a>Zobacz też

- [Schemat pliku konfiguracji](../index.md)
