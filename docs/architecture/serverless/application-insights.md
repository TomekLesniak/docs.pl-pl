---
title: Application Insights — aplikacje bezserwerowe
description: Application Insights to platforma diagnostyki bezserwerowej, która pozwala deweloperom wykrywać, klasyfikacja i diagnozować problemy w aplikacjach sieci Web, aplikacjach mobilnych, aplikacjach klasycznych i mikrousługach.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 42791b052ebb068c9b7109291e66b30b47e5821f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173324"
---
# <a name="telemetry-with-application-insights"></a>Telemetria za pomocą usługi Application Insights

[Application Insights](/azure/application-insights) to platforma diagnostyki bezserwerowej, która pozwala deweloperom wykrywać, klasyfikacja i diagnozować problemy w aplikacjach sieci Web, aplikacjach mobilnych, aplikacjach klasycznych i mikrousługach. Application Insights dla aplikacji funkcji można włączyć, przełączając przełącznik w portalu. Application Insights zapewnia wszystkie te możliwości bez konieczności konfigurowania serwera ani konfigurowania własnej bazy danych. Wszystkie możliwości Application Insights "są udostępniane jako usługa, która jest automatycznie integrowana z aplikacjami.

![Logo Application Insights](./media/application-insights-logo.png)

Dodawanie Application Insights do istniejących aplikacji jest tak proste jak dodanie klucza instrumentacji do ustawień aplikacji. Za pomocą Application Insights można:

- Tworzenie niestandardowych wykresów i alertów na podstawie metryk, takich jak liczba wywołań funkcji, czas potrzebny do uruchomienia funkcji i wyjątków
- Analizowanie błędów i wyjątków serwera
- Przechodzenie do szczegółów wydajności według operacji i mierzenie czasu potrzebnego do wywołania zależności innych firm
- Monitoruj użycie procesora CPU, pamięci i szybkości na wszystkich serwerach, które obsługują aplikacje funkcji
- Wyświetl strumień na żywo metryk, w tym liczbę żądań i czas oczekiwania dla aplikacji funkcji
- Korzystanie z [analizy](/azure/application-insights/app-insights-analytics) do wyszukiwania, wykonywania zapytań i tworzenia niestandardowych wykresów za pośrednictwem danych funkcji

![Eksplorator metryk](./media/metrics-explorer.png)

Oprócz wbudowanej telemetrii możliwe jest również generowanie niestandardowych danych telemetrycznych. Poniższy fragment kodu tworzy niestandardowego klienta telemetrii przy użyciu zestawu kluczy Instrumentacji dla aplikacji funkcji:

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

Poniższy kod mierzy, jak długo trwa wstawianie nowego wiersza do wystąpienia [usługi Azure Table Storage](/azure/cosmos-db/table-storage-overview) :

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

Zostanie wyświetlony wynikowy Wykres wydajności:

![Telemetria niestandardowa](./media/custom-telemetry.png)

Niestandardowa Telemetria pokazuje średni czas wstawiania nowego wiersza wynosi 32,6 milisekund.

Application Insights zapewnia zaawansowany i wygodny sposób rejestrowania szczegółowej telemetrii dotyczącej aplikacji bezserwerowych. Masz pełną kontrolę nad poziomem śledzenia i udostępnianym rejestrowaniem. Można śledzić niestandardowe statystyki, takie jak zdarzenia, zależności i widok strony. Dzięki zaawansowanej analizie można napisać zapytania, które zadają ważne pytania i generować wykresy i szczegółowe informacje.

Aby uzyskać więcej informacji, zobacz [Monitor Azure Functions](/azure/azure-functions/functions-monitoring).

>[!div class="step-by-step"]
>[Poprzedni](azure-functions.md) 
> [Dalej](logic-apps.md)
