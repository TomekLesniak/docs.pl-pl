---
ms.openlocfilehash: 0dfe04ba1313480f15a8e7a7e26da613799180b2
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2020
ms.locfileid: "92332887"
---
### <a name="aspnet-core-apps-allow-deserializing-quoted-numbers"></a>Aplikacje ASP.NET Core umożliwiają deserializacji liczby ujęte w cudzysłów

Począwszy od platformy .NET 5,0, ASP.NET Core aplikacje używają domyślnych opcji deserializacji określonych przez <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> . <xref:System.Text.Json.JsonSerializerDefaults.Web>Zestaw opcji zawiera ustawienie <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType> . Ta zmiana oznacza, że ASP.NET Core aplikacje pomogą pomyślnie deserializować liczby, które są reprezentowane jako ciągi JSON, zamiast zgłaszać wyjątek.

#### <a name="change-description"></a>Zmień opis

W przypadku programu .NET Core 3,0-3,1 system <xref:System.Text.Json.JsonSerializer> zgłasza <xref:System.Text.Json.JsonException> podczas deserializacji, jeśli napotka liczbę ujętą w cudzysłów w ładunku JSON. Liczby ujęte w cudzysłów są używane do mapowania z właściwościami liczb na wykresach obiektów. W przypadku programu .NET Core 3,0-3,1 liczby są odczytywane tylko z <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType> tokenów.

Począwszy od platformy .NET 5,0, cytowane liczby w ładunków JSON są uznawane za prawidłowe domyślnie dla aplikacji ASP.NET Core. Podczas deserializacji liczby ujętych w cudzysłów nie jest zgłaszany żaden wyjątek.

> [!TIP]
>
> - Nie ma żadnej zmiany zachowania dla domyślnej, autonomicznej <xref:System.Text.Json.JsonSerializer> lub <xref:System.Text.Json.JsonSerializerOptions> .
> - Nie jest to technicznie istotna zmiana, ponieważ sprawia, że scenariusz jest bardziej ograniczany, a nie bardziej restrykcyjny (to oznacza, że powiodło się przekształcenie numeru z ciągu JSON zamiast zgłaszania wyjątku). Jednak ponieważ jest to znacząca zmiana behawioralna wpływająca na wiele aplikacji ASP.NET Core, zostanie ona udokumentowana w tym miejscu.
> - <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A> <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A> Metody rozszerzające również używają <xref:System.Text.Json.JsonSerializerDefaults.Web> zestawu opcji serializacji.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0

#### <a name="reason-for-change"></a>Przyczyna zmiany

Wielu użytkowników zażądał opcji w celu uzyskania bardziej ograniczającej liczby <xref:System.Text.Json.JsonSerializer> . Ta opinia wskazuje, że wielu producentów JSON (na przykład usług w sieci Web) emitują liczby ujęte w cudzysłów. Dzięki umożliwieniu odczytywania liczby ujętych w cudzysłów (deserializacji) aplikacje .NET mogą pomyślnie analizować te ładunki, domyślnie w kontekstach sieci Web. Konfiguracja jest udostępniana przez program, <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> Aby można było określić te same opcje w różnych warstwach aplikacji, na przykład klient, serwer i udostępnione.

#### <a name="recommended-action"></a>Zalecana akcja

Jeśli ta zmiana będzie zakłócać działanie, na przykład w zależności od obsługi ścisłej liczby na potrzeby walidacji, można ponownie włączyć poprzednie zachowanie. Ustaw <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> opcję na <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType> .

W przypadku aplikacji ASP.NET Core MVC i Web API Apps można skonfigurować opcję w programie przy `Startup` użyciu następującego kodu:

```csharp
services.AddControllers()
   .AddJsonOptions(options.NumberHandling = JsonNumberHandling.Strict);
```

#### <a name="category"></a>Kategoria

- ASP.NET Core
- Serializacja

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
