---
title: <gcAllowVeryLargeObjects> Element
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 78a42596aae6c3ea0d94ac759d11ed52d0ace539
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178232"
---
# <a name="gcallowverylargeobjects-element"></a>\<gcAllowVeryLargeObjects> Element

Na platformach 64-bitowych program umożliwia korzystanie z tablic o rozmiarze większym niż 2 gigabajty (GB).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<gcAllowVeryLargeObjects
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`enabled`|Atrybut wymagany.<br /><br /> Określa, czy tablice o rozmiarze większym niż 2 GB są włączone na platformach 64-bitowych.|  
  
## <a name="enabled-attribute"></a>Atrybut włączony  
  
|Wartość|Opis|  
|-----------|-----------------|  
|`false`|Tablice o rozmiarze większym niż 2 GB nie są włączone. Jest to opcja domyślna.|  
|`true`|Tablice o rozmiarze większym niż 2 GB są włączone na platformach 64-bitowych.|  
  
### <a name="child-elements"></a>Elementy podrzędne  

 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|`configuration`|Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.|  
|`runtime`|Zawiera informacje dotyczące opcji inicjowania środowiska uruchomieniowego.|  
  
## <a name="remarks"></a>Uwagi  

 Użycie tego elementu w pliku konfiguracji aplikacji umożliwia korzystanie z tablic o rozmiarze większym niż 2 GB, ale nie powoduje zmiany innych limitów rozmiaru obiektu lub rozmiaru tablicy:  
  
- Maksymalna liczba elementów w tablicy to <xref:System.UInt32.MaxValue?displayProperty=nameWithType> .  
  
- Maksymalny indeks w dowolnym pojedynczym wymiarze to 2 147 483 591 (0x7FFFFFC7) dla tablic bajtowych i tablic jednobajtowych struktur oraz 2 146 435 071 (0X7FEFFFFF) dla innych typów.  
  
- Maksymalny rozmiar ciągów i innych obiektów niebędących tablicami jest niezmieniony.  
  
> [!CAUTION]
> Przed włączeniem tej funkcji upewnij się, że aplikacja nie zawiera niebezpiecznego kodu, który zakłada, że wszystkie tablice mają rozmiar mniejszy niż 2 GB. Na przykład kod niebezpieczny używający tablic jako bufory może być podatny na przepełnienia buforu, jeśli zostanie zapisany w założeniu, że tablice nie przekroczą 2 GB.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak włączyć tę funkcję dla aplikacji.  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a>Obsługiwane w

.NET Framework 4,5 i nowsze wersje

## <a name="see-also"></a>Zobacz też

- [Schemat ustawień środowiska uruchomieniowego](index.md)
- [Schemat pliku konfiguracji](../index.md)
