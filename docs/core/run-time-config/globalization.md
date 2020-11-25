---
title: Ustawienia konfiguracji globalizacji
description: Dowiedz się więcej o ustawieniach czasu wykonywania, które konfigurują aspekty globalizacji aplikacji .NET Core, na przykład analizując daty w języku japońskim.
ms.date: 05/18/2020
ms.topic: reference
ms.openlocfilehash: fc98e965093c28b75b9b66e4f1c9f147abd4680e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721920"
---
# <a name="run-time-configuration-options-for-globalization"></a>Opcje konfiguracji czasu wykonywania dla globalizacji

## <a name="invariant-mode"></a>Tryb niezmienny

- Określa, czy aplikacja .NET Core działa w trybie globalizacji-niezmiennym bez dostępu do danych i zachowań specyficznych dla kultury.
- Jeśli pominięto to ustawienie, aplikacja zostanie uruchomiona z dostępem do danych kultury. Jest to równoznaczne z ustawieniem wartości `false` .
- Aby uzyskać więcej informacji, zobacz [tryb niezmienny globalizacji platformy .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).

| | Nazwa ustawienia | Wartości |
| - | - | - |
| **runtimeconfig.jsna** | `System.Globalization.Invariant` | `false` — dostęp do danych kultury<br/>`true` -Uruchom w trybie niezmiennym |
| **Właściwość programu MSBuild** | `InvariantGlobalization` | `false` — dostęp do danych kultury<br/>`true` -Uruchom w trybie niezmiennym |
| **Zmienna środowiskowa** | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | `0` — dostęp do danych kultury<br/>`1` -Uruchom w trybie niezmiennym |

### <a name="examples"></a>Przykłady

*runtimeconfig.js* pliku:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

Plik projektu:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a>Zakresy lat era

- Określa, czy zakres sprawdza, czy kalendarze obsługujące wiele operacji wymazywania są swobodne, czy też wskazuje, czy daty, które przepełnią zakres dat era <xref:System.ArgumentOutOfRangeException> .
- W przypadku pominięcia tego ustawienia testy zakresu są swobodne. Jest to równoznaczne z ustawieniem wartości `false` .
- Aby uzyskać więcej informacji, zobacz [kalendarze, wymazywane i zakres dat: kontrole swobodnego zakresu](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).

| | Nazwa ustawienia | Wartości |
| - | - | - |
| **runtimeconfig.jsna** | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | `false` -swobodne kontrole zakresu<br/>`true` -nadprzepływy powodują wyjątek |
| **Zmienna środowiskowa** | NIE DOTYCZY | NIE DOTYCZY |

## <a name="japanese-date-parsing"></a>Japońska analiza daty

- Określa, czy ciąg, który zawiera "1" lub "Gannen", jest analizowany pomyślnie, czy jest obsługiwany tylko "1".
- Jeśli pominięto to ustawienie, ciągi zawierające wartość "1" lub "Gannen" w przypadku pomyślnego przeanalizowania roku. Jest to równoznaczne z ustawieniem wartości `false` .
- Aby uzyskać więcej informacji, zobacz [przedstawianie dat w kalendarzach z wieloma wymazywanymi](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Nazwa ustawienia | Wartości |
| - | - | - |
| **runtimeconfig.jsna** | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | `false` -Jest obsługiwana wartość "Gannen" lub "1"<br/>`true` -tylko "1" jest obsługiwana |
| **Zmienna środowiskowa** | NIE DOTYCZY | NIE DOTYCZY |

## <a name="japanese-year-format"></a>Japoński rok

- Określa, czy pierwszy rok dla ery w kalendarzu japońskim jest sformatowany jako "Gannen", czy jako liczba.
- Jeśli to ustawienie zostanie pominięte, pierwszy rok zostanie sformatowany jako "Gannen". Jest to równoznaczne z ustawieniem wartości `false` .
- Aby uzyskać więcej informacji, zobacz [przedstawianie dat w kalendarzach z wieloma wymazywanymi](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Nazwa ustawienia | Wartości |
| - | - | - |
| **runtimeconfig.jsna** | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | `false` -Format jako "Gannen"<br/>`true` -formatowanie jako liczba |
| **Zmienna środowiskowa** | NIE DOTYCZY | NIE DOTYCZY |

## <a name="nls"></a>NLS

- Określa, czy platforma .NET korzysta z interfejsu API globalizacji języka narodowego (NLS) lub składników międzynarodowych dla aplikacji systemu Windows (ICU). .NET 5,0 i nowsze wersje używają interfejsów API ICU globalizacji domyślnie w systemie Windows 10 maja 2019 Update i nowszych wersjach.
- W przypadku pominięcia tego ustawienia platforma .NET domyślnie używa interfejsów API ICU globalizacji. Jest to równoznaczne z ustawieniem wartości `false` .
- Aby uzyskać więcej informacji, zobacz [interfejsy API globalizacji korzystają z BIBLIOTEK ICU w systemie Windows](../compatibility/globalization/5.0/icu-globalization-api.md).

| | Nazwa ustawienia | Wartości | Wprowadzono |
| - | - | - | - |
| **runtimeconfig.jsna** | `System.Globalization.UseNls` | `false` -Korzystanie z interfejsów API ICU globalizacji<br/>`true` -Korzystanie z interfejsów API globalizacji NLS | .NET 5,0 |
| **Zmienna środowiskowa** | `DOTNET_SYSTEM_GLOBALIZATION_USENLS` | `false` -Korzystanie z interfejsów API ICU globalizacji<br/>`true` -Korzystanie z interfejsów API globalizacji NLS | .NET 5,0 |
