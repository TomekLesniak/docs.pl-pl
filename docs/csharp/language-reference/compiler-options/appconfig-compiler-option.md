---
description: -AppConfig (opcje kompilatora C#)
title: -AppConfig (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /appconfig
helpviewer_keywords:
- /appconfig compiler option [C#]
- -appconfig compiler option [C#]
- appconfig compiler option [C#]
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
ms.openlocfilehash: 8ee481851dc02bed5eb0a7c26fa8893e52d54a9f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157970"
---
# <a name="-appconfig-c-compiler-options"></a>-AppConfig (opcje kompilatora C#)

Opcja kompilatora **-AppConfig** umożliwia aplikacji języka C# Określanie lokalizacji pliku konfiguracji aplikacji zestawu (app.config) do środowiska uruchomieniowego języka wspólnego (CLR) w czasie powiązania zestawu.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-appconfig:file  
```  
  
## <a name="arguments"></a>Argumenty  

 `file`  
 Wymagany. Plik konfiguracji aplikacji, który zawiera ustawienia powiązania zestawu.  
  
## <a name="remarks"></a>Uwagi  

 Jednym z zastosowań **-AppConfig** jest zaawansowane scenariusze, w których zestaw musi odwoływać się zarówno do wersji .NET Framework, jak i .NET Framework dla wersji Silverlight określonego zestawu odwołania w tym samym czasie. Na przykład Projektant XAML zapisany w Windows Presentation Foundation (WPF) może potrzebować odwoływać się zarówno do pulpitu WPF, interfejsu użytkownika projektanta, jak i podzbioru WPF, który jest dołączony do Silverlight. Ten sam zestaw projektanta ma dostęp do obu zestawów. Domyślnie oddzielne odwołania powodują wystąpienie błędu kompilatora, ponieważ powiązanie zestawu widzi dwa zestawy jako równoważne.  
  
 Opcja kompilatora **-AppConfig** umożliwia określenie lokalizacji pliku app.config, który wyłącza zachowanie domyślne przy użyciu `<supportPortability>` znacznika, jak pokazano w poniższym przykładzie.  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 Kompilator przekazuje lokalizację pliku do logiki powiązania zestawu środowiska CLR.  
  
> [!NOTE]
> Jeśli używasz Microsoft Build Engine (MSBuild) do kompilowania aplikacji, możesz ustawić opcję kompilatora **-AppConfig** przez dodanie znacznika właściwości do pliku. csproj. Aby użyć pliku app.config, który jest już ustawiony w projekcie, Dodaj tag właściwości `<UseAppConfigForCompiler>` do pliku. csproj i ustaw jego wartość na `true` . Aby określić inny plik app.config, Dodaj tag właściwości `<AppConfigForCompiler>` i ustaw jego wartość na lokalizację pliku.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje plik app.config, który umożliwia aplikacji posiadanie odwołań zarówno do implementacji .NET Framework, jak i .NET Framework dla implementacji Silverlight dowolnego zestawu .NET Framework, który istnieje w obu implementacjach. Opcja kompilatora **-AppConfig** określa lokalizację tego pliku app.config.  
  
```xml  
<configuration>  
      <runtime>  
      <assemblyBinding>  
            <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
            <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
      </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz też

- [\<supportPortability> Postaci](../../../framework/configure-apps/file-schema/runtime/supportportability-element.md)
- [Opcje kompilatora C# w porządku alfabetycznym](./listed-alphabetically.md)
