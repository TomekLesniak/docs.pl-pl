---
title: 'Istotna zmiana: aplikacje ASP.NET Core umożliwiają deserializacji liczby ujęte w cudzysłów'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, w której ASP.NET Core aplikacje pomyślnie dekodują liczby, które są reprezentowane jako ciągi JSON, zamiast zgłaszać wyjątek.
ms.date: 10/21/2020
ms.openlocfilehash: fc8a4c6638be391c22c7cfb2fc7c216c88377f29
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761420"
---
# <a name="aspnet-core-apps-allow-deserializing-quoted-numbers"></a><span data-ttu-id="7a6a5-103">Aplikacje ASP.NET Core umożliwiają deserializacji liczby ujęte w cudzysłów</span><span class="sxs-lookup"><span data-stu-id="7a6a5-103">ASP.NET Core apps allow deserializing quoted numbers</span></span>

<span data-ttu-id="7a6a5-104">Począwszy od platformy .NET 5,0, ASP.NET Core aplikacje używają domyślnych opcji deserializacji określonych przez <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="7a6a5-104">Starting in .NET 5.0, ASP.NET Core apps use the default deserialization options as specified by <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7a6a5-105"><xref:System.Text.Json.JsonSerializerDefaults.Web>Zestaw opcji zawiera ustawienie <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="7a6a5-105">The <xref:System.Text.Json.JsonSerializerDefaults.Web> set of options includes setting <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> to <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7a6a5-106">Ta zmiana oznacza, że ASP.NET Core aplikacje będą pomyślnie deserializować liczby, które są reprezentowane jako ciągi JSON, zamiast zgłaszać wyjątek.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-106">This change means that ASP.NET Core apps will successfully deserialize numbers that are represented as JSON strings instead of throwing an exception.</span></span>

## <a name="change-description"></a><span data-ttu-id="7a6a5-107">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="7a6a5-107">Change description</span></span>

<span data-ttu-id="7a6a5-108">W przypadku programu .NET Core 3,0-3,1 system <xref:System.Text.Json.JsonSerializer> zgłasza <xref:System.Text.Json.JsonException> podczas deserializacji, jeśli napotka liczbę ujętą w cudzysłów w ładunku JSON.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-108">In .NET Core 3.0 - 3.1, <xref:System.Text.Json.JsonSerializer> throws a <xref:System.Text.Json.JsonException> during deserialization if it encounters a quoted number in a JSON payload.</span></span> <span data-ttu-id="7a6a5-109">Liczby ujęte w cudzysłów są używane do mapowania z właściwościami liczb na wykresach obiektów.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-109">The quoted numbers are used to map with number properties in object graphs.</span></span> <span data-ttu-id="7a6a5-110">W przypadku programu .NET Core 3,0-3,1 liczby są odczytywane tylko z <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType> tokenów.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-110">In .NET Core 3.0 - 3.1, numbers are only read from <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType> tokens.</span></span>

<span data-ttu-id="7a6a5-111">Począwszy od platformy .NET 5,0, cytowane liczby w ładunków JSON są uznawane za prawidłowe domyślnie dla aplikacji ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-111">Starting in .NET 5.0, quoted numbers in JSON payloads are considered valid, by default, for ASP.NET Core apps.</span></span> <span data-ttu-id="7a6a5-112">Podczas deserializacji liczby ujętych w cudzysłów nie jest zgłaszany żaden wyjątek.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-112">No exception is thrown during deserialization of quoted numbers.</span></span>

> [!TIP]
>
> - <span data-ttu-id="7a6a5-113">Nie ma żadnej zmiany zachowania dla domyślnej, autonomicznej <xref:System.Text.Json.JsonSerializer> lub <xref:System.Text.Json.JsonSerializerOptions> .</span><span class="sxs-lookup"><span data-stu-id="7a6a5-113">There is no behavior change for the default, standalone <xref:System.Text.Json.JsonSerializer> or <xref:System.Text.Json.JsonSerializerOptions>.</span></span>
> - <span data-ttu-id="7a6a5-114">Nie jest to technicznie istotna zmiana, ponieważ sprawia, że scenariusz jest bardziej ograniczany, a nie bardziej restrykcyjny (to oznacza, że powiodło się przekształcenie numeru z ciągu JSON zamiast zgłaszania wyjątku).</span><span class="sxs-lookup"><span data-stu-id="7a6a5-114">This is technically not a breaking change, since it makes a scenario more permissive instead of more restrictive (that is, it succeeds in coercing a number from a JSON string instead of throwing an exception).</span></span> <span data-ttu-id="7a6a5-115">Jednak ponieważ jest to znacząca zmiana behawioralna wpływająca na wiele aplikacji ASP.NET Core, zostanie ona udokumentowana w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-115">However, since this is a significant behavioral change that affects many ASP.NET Core apps, it is documented here.</span></span>
> - <span data-ttu-id="7a6a5-116"><xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> Metody rozszerzające również używają <xref:System.Text.Json.JsonSerializerDefaults.Web> zestawu opcji serializacji.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-116">The <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> extension methods also use the <xref:System.Text.Json.JsonSerializerDefaults.Web> set of serialization options.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="7a6a5-117">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="7a6a5-117">Version introduced</span></span>

<span data-ttu-id="7a6a5-118">5,0</span><span class="sxs-lookup"><span data-stu-id="7a6a5-118">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="7a6a5-119">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="7a6a5-119">Reason for change</span></span>

<span data-ttu-id="7a6a5-120">Wielu użytkowników zażądał opcji w celu uzyskania bardziej ograniczającej liczby <xref:System.Text.Json.JsonSerializer> .</span><span class="sxs-lookup"><span data-stu-id="7a6a5-120">Multiple users have requested an option for more permissive number handling in <xref:System.Text.Json.JsonSerializer>.</span></span> <span data-ttu-id="7a6a5-121">Ta opinia wskazuje, że wielu producentów JSON (na przykład usług w sieci Web) emitują liczby ujęte w cudzysłów.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-121">This feedback indicates that many JSON producers (for example, services across the web) emit quoted numbers.</span></span> <span data-ttu-id="7a6a5-122">Dzięki umożliwieniu odczytywania liczby ujętych w cudzysłów (deserializacji) aplikacje .NET mogą pomyślnie analizować te ładunki, domyślnie w kontekstach sieci Web.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-122">By allowing quoted numbers to be read (deserialized), .NET apps can successfully parse these payloads, by default, in web contexts.</span></span> <span data-ttu-id="7a6a5-123">Konfiguracja jest udostępniana przez program, <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> Aby można było określić te same opcje w różnych warstwach aplikacji, na przykład klient, serwer i udostępnione.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-123">The configuration is exposed via <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> so that you can specify the same options across different application layers, for example, client, server, and shared.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="7a6a5-124">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="7a6a5-124">Recommended action</span></span>

<span data-ttu-id="7a6a5-125">Jeśli ta zmiana będzie zakłócać działanie, na przykład w zależności od obsługi ścisłej liczby na potrzeby walidacji, można ponownie włączyć poprzednie zachowanie.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-125">If this change is disruptive, for example, if you depend on the strict number handling for validation, you can re-enable the previous behavior.</span></span> <span data-ttu-id="7a6a5-126">Ustaw <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> opcję na <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="7a6a5-126">Set the <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> option to <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="7a6a5-127">W przypadku aplikacji ASP.NET Core MVC i Web API Apps można skonfigurować opcję w programie przy `Startup` użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="7a6a5-127">For ASP.NET Core MVC and web API apps, you can configure the option in `Startup` by using the following code:</span></span>

```csharp
services.AddControllers()
   .AddJsonOptions(options.NumberHandling = JsonNumberHandling.Strict);
```

## <a name="affected-apis"></a><span data-ttu-id="7a6a5-128">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="7a6a5-128">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

### Category

- ASP.NET Core
- Serialization

-->
