---
title: Implementowanie niestandardowego dostawcy konfiguracji w programie .NET
description: Dowiedz się, jak zaimplementować niestandardowego dostawcę konfiguracji w aplikacjach .NET.
author: IEvangelist
ms.author: dapine
ms.date: 09/16/2020
ms.topic: how-to
ms.openlocfilehash: 968bf202eeea32742444681260d5ab0b27b403f9
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720808"
---
# <a name="implement-a-custom-configuration-provider-in-net"></a>Implementowanie niestandardowego dostawcy konfiguracji w programie .NET

Istnieje wielu [dostawców konfiguracji](configuration-providers.md) dostępnych dla wspólnych źródeł konfiguracji, takich jak pliki JSON, XML i ini. Może być konieczne zaimplementowanie niestandardowego dostawcy konfiguracji, gdy jeden z dostępnych dostawców nie odpowiada wymaganiom Twojej aplikacji. W tym artykule dowiesz się, jak zaimplementować niestandardowego dostawcę konfiguracji, który korzysta z bazy danych jako źródła konfiguracji.

## <a name="custom-configuration-provider"></a>Niestandardowy dostawca konfiguracji

Przykładowa aplikacja pokazuje, jak utworzyć podstawowego dostawcę konfiguracji, który odczytuje pary klucz-wartość konfiguracji z bazy danych przy użyciu narzędzia [Entity Framework (EF) Core](/ef/core).

Dostawca ma następującą charakterystykę:

- Baza danych EF w pamięci jest używana w celach demonstracyjnych. Aby użyć bazy danych, która wymaga parametrów połączenia, zaimplementuj dodatkową wartość w `ConfigurationBuilder` celu dostarczenia parametrów połączenia od innego dostawcy konfiguracji.
- Dostawca odczytuje tabelę bazy danych w konfiguracji podczas uruchamiania. Dostawca nie wykonuje zapytania do bazy danych w oparciu o klucz.
- Ponowne załadowanie nie zostało zaimplementowane, więc aktualizacja bazy danych po uruchomieniu aplikacji nie ma wpływu na konfigurację aplikacji.

Zdefiniuj `Settings` jednostkę typu rekordu do przechowywania wartości konfiguracji w bazie danych. Można na przykład dodać plik *Settings.cs* do folderu *models* :

:::code language="csharp" source="snippets/configuration/custom-provider/Models/Settings.cs":::

Aby uzyskać informacje na temat typów rekordów, zobacz [typy rekordów w języku C# 9](../../csharp/whats-new/csharp-9.md#record-types).

Dodaj `EntityConfigurationContext` do magazynu i uzyskaj dostęp do skonfigurowanych wartości.

*Dostawcy/EntityConfigurationContext. cs*:

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationContext.cs":::

Utwórz klasę implementującą <xref:Microsoft.Extensions.Configuration.IConfigurationSource> .

*Dostawcy/EntityConfigurationSource. cs*:

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationSource.cs":::

Utwórz niestandardowego dostawcę konfiguracji, dziedziczących od <xref:Microsoft.Extensions.Configuration.ConfigurationProvider> . Dostawca konfiguracji inicjuje bazę danych, gdy jest pusta. Ponieważ w kluczach konfiguracji jest rozróżniana wielkość liter, słownik używany do inicjowania bazy danych jest tworzony przy użyciu funkcji porównującej bez uwzględniania wielkości liter ([StringComparer. OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase)).

*Dostawcy/EntityConfigurationProvider. cs*:

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationProvider.cs":::

`AddEntityConfiguration`Metoda rozszerzająca zezwala na Dodawanie źródła konfiguracji do <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder> wystąpienia.

*Rozszerzenia/ConfigurationBuilderExtensions. cs*:

:::code language="csharp" source="snippets/configuration/custom-provider/Extensions/ConfigurationBuilderExtensions.cs":::

Poniższy kod pokazuje, jak używać niestandardowych `EntityConfigurationProvider` w *program.cs*:

:::code language="csharp" source="snippets/configuration/custom-provider/Program.cs" highlight="21-22":::

## <a name="see-also"></a>Zobacz też

- [Konfiguracja w programie .NET](configuration.md)
- [Dostawcy konfiguracji w programie .NET](configuration-providers.md)
