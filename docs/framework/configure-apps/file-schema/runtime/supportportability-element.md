---
title: <supportPortability> Element
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
ms.openlocfilehash: 05ce6943b9456d4fd380ea8d6cf354d197b92f96
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183952"
---
# <a name="supportportability-element"></a>\<supportPortability> Element

Określa, że aplikacja może odwoływać się do tego samego zestawu w dwóch różnych implementacjach .NET Framework, przez wyłączenie domyślnego zachowania, które traktuje zestawy jako równoważne do celów przenośności aplikacji.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<supportPortability>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|PKT|Atrybut wymagany.<br /><br /> Określa token klucza publicznego zestawu, którego to dotyczy, jako ciąg znaków.|  
|enabled|Atrybut opcjonalny.<br /><br /> Określa, czy obsługa przenośności między implementacjami określonego zestawu .NET Framework powinna być włączona.|  
  
## <a name="enabled-attribute"></a>Atrybut włączony  
  
|Wartość|Opis|  
|-----------|-----------------|  
|true|Włącz obsługę przenośności między implementacjami określonego zestawu .NET Framework. Jest to opcja domyślna.|  
|fałsz|Wyłącz obsługę przenośności między implementacjami określonego zestawu .NET Framework. Dzięki temu aplikacja może mieć odwołania do wielu implementacji określonego zestawu.|  
  
### <a name="child-elements"></a>Elementy podrzędne  

Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|`configuration`|Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.|  
|`runtime`|Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.|  
|`assemblyBinding`|Zawiera informacje o przekierowaniu wersji zestawu i lokalizacji zestawów.|  
  
## <a name="remarks"></a>Uwagi  

Począwszy od .NET Framework 4, pomoc techniczna jest świadczona automatycznie dla aplikacji, które mogą korzystać z jednej z dwóch implementacji .NET Framework, na przykład implementacji .NET Framework lub .NET Framework dla implementacji Silverlight. Dwie implementacje określonego zestawu .NET Framework są uważane za równoważne przez spinacz zestawu. W kilku scenariuszach ta funkcja przenośności aplikacji powoduje problemy. W tych scenariuszach `<supportPortability>` element może być używany do wyłączania tej funkcji.  
  
Taki scenariusz jest zestawem, który musi odwoływać się zarówno do implementacji .NET Framework, jak i .NET Framework do implementacji Silverlight dla określonego zestawu odwołania. Na przykład Projektant XAML zapisany w Windows Presentation Foundation (WPF) może potrzebować odwoływać się zarówno do implementacji pulpitu WPF, interfejsu użytkownika projektanta, jak i podzbioru WPF, który jest zawarty w implementacji Silverlight. Domyślnie oddzielne odwołania powodują wystąpienie błędu kompilatora, ponieważ powiązanie zestawu widzi dwa zestawy jako równoważne. Ten element wyłącza zachowanie domyślne i zezwala na pomyślne Kompilowanie.  
  
> [!IMPORTANT]
> Aby kompilator przeszedł informacje do logiki wiązania zestawu środowiska uruchomieniowego języka wspólnego, należy użyć `/appconfig` opcji kompilatora, aby określić lokalizację pliku app.config zawierającego ten element.  
  
## <a name="example"></a>Przykład  

Poniższy przykład umożliwia aplikacji odwoływanie się do implementacji .NET Framework i .NET Framework dla implementacji Silverlight dowolnego zestawu .NET Framework, który istnieje w obu implementacjach. `/appconfig`Aby określić lokalizację tego pliku app.config, należy użyć opcji kompilatora.  
  
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

- [-AppConfig (opcje kompilatora C#)](../../../../csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- [Przegląd dezjednoczenia zestawu .NET Framework](/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))
