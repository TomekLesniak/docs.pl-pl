---
title: <forcePerformanceCounterUniqueSharedMemoryReads> Element
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 719448ba3de2aca0621fc17b9fadbdd3b8588f2e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178245"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<forcePerformanceCounterUniqueSharedMemoryReads> Element

Określa, czy PerfCounter.dll używa ustawienia rejestru CategoryOptions w aplikacji .NET Framework w wersji 1,1, aby określić, czy dane liczników wydajności mają być ładowane z pamięci współdzielonej określonej dla kategorii, czy z pamięci globalnej.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`enabled`|Atrybut wymagany.<br /><br /> Wskazuje, czy PerfCounter.dll używa ustawienia rejestru CategoryOptions, aby określić, czy załadować dane liczników wydajności z pamięci współdzielonej określonej dla kategorii lub pamięci globalnej.|  
  
## <a name="enabled-attribute"></a>Atrybut włączony  
  
|Wartość|Opis|  
|-----------|-----------------|  
|`false`|PerfCounter.dll nie używa ustawienia rejestru CategoryOptions. jest to ustawienie domyślne.|  
|`true`|PerfCounter.dll używa ustawienia rejestru CategoryOptions.|  
  
### <a name="child-elements"></a>Elementy podrzędne  

 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|`configuration`|Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.|  
|`runtime`|Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.|  
  
## <a name="remarks"></a>Uwagi  

 W wersjach .NET Framework przed .NET Framework 4, załadowana wersja PerfCounter.dll odnosi się do środowiska uruchomieniowego, które zostało załadowane w procesie. Jeśli na komputerze zainstalowano zarówno .NET Framework w wersji 1,1, jak i .NET Framework 2,0, aplikacja .NET Framework 1,1 załaduje .NET Framework 1,1 wersja PerfCounter.dll. Począwszy od .NET Framework 4 Najnowsza zainstalowana wersja PerfCounter.dll zostanie załadowana. Oznacza to, że aplikacja .NET Framework 1,1 będzie ładować wersję PerfCounter.dll .NET Framework 4, jeśli na komputerze zainstalowano .NET Framework 4.  
  
 Począwszy od .NET Framework 4, podczas zużywania liczników wydajności, PerfCounter.dll sprawdza wpis rejestru CategoryOptions dla każdego dostawcy, aby określić, czy powinien on zostać odczytany z udostępnionej pamięci lub globalnej pamięci współdzielonej według kategorii. PerfCounter.dll .NET Framework 1,1 nie odczytuje tego wpisu rejestru, ponieważ nie ma on informacji o pamięci współdzielonej określonej dla kategorii; zawsze odczytuje z globalnej pamięci współdzielonej.  
  
 W celu zapewnienia zgodności z poprzednimi wersjami PerfCounter.dll .NET Framework 4 nie sprawdza wpisu rejestru CategoryOptions podczas uruchamiania w aplikacji .NET Framework 1,1. Po prostu używa globalnej pamięci współdzielonej, podobnie jak .NET Framework 1,1 PerfCounter.dll. Można jednak wydać polecenie .NET Framework 4 PerfCounter.dll do sprawdzenia ustawienia rejestru przez włączenie `<forcePerformanceCounterUniqueSharedMemoryReads>` elementu.  
  
> [!NOTE]
> Włączenie `<forcePerformanceCounterUniqueSharedMemoryReads>` elementu nie gwarantuje, że zostanie użyta udostępniona pamięć określona w kategorii. Ustawienie Enabled `true` tylko powoduje, że PerfCounter.dll odwołujące się do ustawienia rejestru CategoryOptions. Ustawieniem domyślnym dla CategoryOptions jest użycie pamięci współużytkowanej określonej dla kategorii; można jednak zmienić CategoryOptions, aby wskazać, że powinna być używana globalna pamięć współdzielona.  
  
 Klucz rejestru, który zawiera ustawienie CategoryOptions, to HKEY_LOCAL_MACHINE \System\CurrentControlSet\Services \\<CategoryName \> \Performance. Domyślnie CategoryOptions jest ustawiony na 3, który instruuje PerfCounter.dll, aby użyć udostępnionej pamięci specyficznej dla kategorii. Jeśli wartość CategoryOptions jest równa 0, PerfCounter.dll używa globalnej pamięci współdzielonej. Dane wystąpienia będą ponownie używane tylko wtedy, gdy nazwa tworzonego wystąpienia jest identyczna z ponownie używanym wystąpieniem. Wszystkie wersje będą mogły zapisywać w kategorii. Jeśli CategoryOptions jest ustawiona na 1, używana jest globalna pamięć współdzielona, ale dane wystąpienia mogą być ponownie używane, jeśli nazwa kategorii ma taką samą długość jak kategoria używana ponownie.  
  
 Ustawienia 0 i 1 mogą prowadzić do przecieków pamięci i wypełniania pamięci licznika wydajności.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak określić, że PerfCounter.dll powinien odwoływać się do wpisu rejestru CategoryOptions, aby określić, czy powinien on używać pamięci współdzielonej specyficznej dla kategorii.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz też

- [Schemat ustawień środowiska uruchomieniowego](index.md)
- [Schemat pliku konfiguracji](../index.md)
