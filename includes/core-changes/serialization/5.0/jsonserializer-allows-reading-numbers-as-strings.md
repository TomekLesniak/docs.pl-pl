---
ms.openlocfilehash: a93856aac97af5c392a2e4698d2da42413cfc3c8
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434984"
---
### <a name="aspnet-core-apps-allow-deserializing-quoted-numbers"></a><span data-ttu-id="1c9cd-101">Aplikacje ASP.NET Core umożliwiają deserializacji liczby ujęte w cudzysłów</span><span class="sxs-lookup"><span data-stu-id="1c9cd-101">ASP.NET Core apps allow deserializing quoted numbers</span></span>

<span data-ttu-id="1c9cd-102">Począwszy od platformy .NET 5,0, ASP.NET Core aplikacje używają domyślnych opcji deserializacji określonych przez <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1c9cd-102">Starting in .NET 5.0, ASP.NET Core apps use the default deserialization options as specified by <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1c9cd-103"><xref:System.Text.Json.JsonSerializerDefaults.Web>Zestaw opcji zawiera ustawienie <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1c9cd-103">The <xref:System.Text.Json.JsonSerializerDefaults.Web> set of options includes setting <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> to <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1c9cd-104">Ta zmiana oznacza, że ASP.NET Core aplikacje pomogą pomyślnie deserializować liczby, które są reprezentowane jako ciągi JSON, zamiast zgłaszać wyjątek.</span><span class="sxs-lookup"><span data-stu-id="1c9cd-104">This change means that ASP.NET Core apps will successfully deserialize numbers that are represented as JSON strings, instead of throwing an exception.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1c9cd-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="1c9cd-105">Change description</span></span>

<span data-ttu-id="1c9cd-106">W przypadku programu .NET Core 3,0-3,1 system <xref:System.Text.Json.JsonSerializer> zgłasza <xref:System.Text.Json.JsonException> podczas deserializacji, jeśli napotka liczbę ujętą w cudzysłów w ładunku JSON.</span><span class="sxs-lookup"><span data-stu-id="1c9cd-106">In .NET Core 3.0 - 3.1, <xref:System.Text.Json.JsonSerializer> throws a <xref:System.Text.Json.JsonException> during deserialization if it encounters a quoted number in a JSON payload.</span></span> <span data-ttu-id="1c9cd-107">Liczby ujęte w cudzysłów są używane do mapowania z właściwościami liczb na wykresach obiektów.</span><span class="sxs-lookup"><span data-stu-id="1c9cd-107">The quoted numbers are used to map with number properties in object graphs.</span></span> <span data-ttu-id="1c9cd-108">W przypadku programu .NET Core 3,0-3,1 liczby są odczytywane tylko z <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType> tokenów.</span><span class="sxs-lookup"><span data-stu-id="1c9cd-108">In .NET Core 3.0 - 3.1, numbers are only read from <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType> tokens.</span></span>

<span data-ttu-id="1c9cd-109">Począwszy od platformy .NET 5,0, cytowane liczby w ładunków JSON są uznawane za prawidłowe domyślnie dla aplikacji ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1c9cd-109">Starting in .NET 5.0, quoted numbers in JSON payloads are considered valid, by default, for ASP.NET Core apps.</span></span> <span data-ttu-id="1c9cd-110">Podczas deserializacji liczby ujętych w cudzysłów nie jest zgłaszany żaden wyjątek.</span><span class="sxs-lookup"><span data-stu-id="1c9cd-110">No exception is thrown during deserialization of quoted numbers.</span></span>

> [!TIP]
>
> - <span data-ttu-id="1c9cd-111">Nie ma żadnej zmiany zachowania dla domyślnej, autonomicznej <xref:System.Text.Json.JsonSerializer> lub <xref:System.Text.Json.JsonSerializerOptions> .</span><span class="sxs-lookup"><span data-stu-id="1c9cd-111">There is no behavior change for the default, standalone <xref:System.Text.Json.JsonSerializer> or <xref:System.Text.Json.JsonSerializerOptions>.</span></span>
> - <span data-ttu-id="1c9cd-112">Nie jest to technicznie istotna zmiana, ponieważ sprawia, że scenariusz jest bardziej ograniczany, a nie bardziej restrykcyjny (to oznacza, że powiodło się przekształcenie numeru z ciągu JSON zamiast zgłaszania wyjątku).</span><span class="sxs-lookup"><span data-stu-id="1c9cd-112">This is technically not a breaking change, since it makes a scenario more permissive instead of more restrictive (that is, it succeeds in coercing a number from a JSON string instead of throwing an exception).</span></span> <span data-ttu-id="1c9cd-113">Jednak ponieważ jest to znacząca zmiana behawioralna wpływająca na wiele aplikacji ASP.NET Core, zostanie ona udokumentowana w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="1c9cd-113">However, since this is a significant behavioral change that affects many ASP.NET Core apps, it is documented here.</span></span>
> - <span data-ttu-id="1c9cd-114"><xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> Metody rozszerzające również używają <xref:System.Text.Json.JsonSerializerDefaults.Web> zestawu opcji serializacji.</span><span class="sxs-lookup"><span data-stu-id="1c9cd-114">The <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> extension methods also use the <xref:System.Text.Json.JsonSerializerDefaults.Web> set of serialization options.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1c9cd-115">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="1c9cd-115">Version introduced</span></span>

<span data-ttu-id="1c9cd-116">5,0</span><span class="sxs-lookup"><span data-stu-id="1c9cd-116">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1c9cd-117">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="1c9cd-117">Reason for change</span></span>

<span data-ttu-id="1c9cd-118">Wielu użytkowników zażądał opcji w celu uzyskania bardziej ograniczającej liczby <xref:System.Text.Json.JsonSerializer> .</span><span class="sxs-lookup"><span data-stu-id="1c9cd-118">Multiple users have requested an option for more permissive number handling in <xref:System.Text.Json.JsonSerializer>.</span></span> <span data-ttu-id="1c9cd-119">Ta opinia wskazuje, że wielu producentów JSON (na przykład usług w sieci Web) emitują liczby ujęte w cudzysłów.</span><span class="sxs-lookup"><span data-stu-id="1c9cd-119">This feedback indicates that many JSON producers (for example, services across the web) emit quoted numbers.</span></span> <span data-ttu-id="1c9cd-120">Dzięki umożliwieniu odczytywania liczby ujętych w cudzysłów (deserializacji) aplikacje .NET mogą pomyślnie analizować te ładunki, domyślnie w kontekstach sieci Web.</span><span class="sxs-lookup"><span data-stu-id="1c9cd-120">By allowing quoted numbers to be read (deserialized), .NET apps can successfully parse these payloads, by default, in web contexts.</span></span> <span data-ttu-id="1c9cd-121">Konfiguracja jest udostępniana przez program, <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> Aby można było określić te same opcje w różnych warstwach aplikacji, na przykład klient, serwer i udostępnione.</span><span class="sxs-lookup"><span data-stu-id="1c9cd-121">The configuration is exposed via <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> so that you can specify the same options across different application layers, for example, client, server, and shared.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1c9cd-122">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="1c9cd-122">Recommended action</span></span>

<span data-ttu-id="1c9cd-123">Jeśli ta zmiana będzie zakłócać działanie, na przykład w zależności od obsługi ścisłej liczby na potrzeby walidacji, można ponownie włączyć poprzednie zachowanie.</span><span class="sxs-lookup"><span data-stu-id="1c9cd-123">If this change is disruptive, for example, if you depend on the strict number handling for validation, you can re-enable the previous behavior.</span></span> <span data-ttu-id="1c9cd-124">Ustaw <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> opcję na <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1c9cd-124">Set the <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> option to <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="1c9cd-125">W przypadku aplikacji ASP.NET Core MVC i Web API Apps można skonfigurować opcję w programie przy `Startup` użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="1c9cd-125">For ASP.NET Core MVC and web API apps, you can configure the option in `Startup` by using the following code:</span></span>

```csharp
services.AddControllers()
   .AddJsonOptions(options.NumberHandling = JsonNumberHandling.Strict);
```

#### <a name="category"></a><span data-ttu-id="1c9cd-126">Kategoria</span><span class="sxs-lookup"><span data-stu-id="1c9cd-126">Category</span></span>

- <span data-ttu-id="1c9cd-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1c9cd-127">ASP.NET Core</span></span>
- <span data-ttu-id="1c9cd-128">Serializacja</span><span class="sxs-lookup"><span data-stu-id="1c9cd-128">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1c9cd-129">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="1c9cd-129">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
