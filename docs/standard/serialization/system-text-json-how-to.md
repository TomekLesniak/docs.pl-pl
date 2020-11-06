---
title: Jak serializować i deserializować kod JSON przy użyciu języka C# — .NET
description: 'Dowiedz się, jak używać :::no-loc(System.Text.Json)::: przestrzeni nazw do serializacji i deserializacji z JSON w programie .NET. Zawiera przykładowy kod.'
ms.date: 11/05/2020
no-loc:
- ':::no-loc(System.Text.Json):::'
- ':::no-loc(Newtonsoft.Json):::'
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 2c1358b2b63a92cb50b853043adbfaae23ccd897
ms.sourcegitcommit: 6bef8abde346c59771a35f4f76bf037ff61c5ba3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2020
ms.locfileid: "94329875"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="671c3-104">Jak serializować i deserializować (Marshaling and unmarshaling) JSON w programie .NET</span><span class="sxs-lookup"><span data-stu-id="671c3-104">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="671c3-105">W tym artykule pokazano, jak używać <xref::::no-loc(System.Text.Json):::?displayProperty=fullName> przestrzeni nazw do serializacji i deserializacji z JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="671c3-105">This article shows how to use the <xref::::no-loc(System.Text.Json):::?displayProperty=fullName> namespace to serialize to and deserialize from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="671c3-106">W przypadku przenoszenia istniejącego kodu z programu `:::no-loc(Newtonsoft.Json):::` zapoznaj się z tematem [jak `:::no-loc(System.Text.Json):::` przeprowadzić migrację do programu ](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="671c3-106">If you're porting existing code from `:::no-loc(Newtonsoft.Json):::`, see [How to migrate to `:::no-loc(System.Text.Json):::`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="671c3-107">Instrukcje i przykładowy kod używają biblioteki bezpośrednio, a nie za pomocą struktury, takiej jak [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="671c3-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="671c3-108">Większość przykładowych kodów serializacji <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> do `true` "DB-Print" w formacie JSON (z wcięciem i białym znakiem).</span><span class="sxs-lookup"><span data-stu-id="671c3-108">Most of the serialization sample code sets <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="671c3-109">Do użycia w środowisku produkcyjnym zwykle przyjmuje się wartość domyślną `false` dla tego ustawienia.</span><span class="sxs-lookup"><span data-stu-id="671c3-109">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="671c3-110">Przykłady kodu odnoszą się do następującej klasy i wariantów:</span><span class="sxs-lookup"><span data-stu-id="671c3-110">The code examples refer to the following class and variants of it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a><span data-ttu-id="671c3-111">Przestrzenie nazw</span><span class="sxs-lookup"><span data-stu-id="671c3-111">Namespaces</span></span>

<span data-ttu-id="671c3-112"><xref::::no-loc(System.Text.Json):::>Przestrzeń nazw zawiera wszystkie punkty wejścia i typy główne.</span><span class="sxs-lookup"><span data-stu-id="671c3-112">The <xref::::no-loc(System.Text.Json):::> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="671c3-113"><xref::::no-loc(System.Text.Json):::.Serialization>Przestrzeń nazw zawiera atrybuty i interfejsy API dla zaawansowanych scenariuszy i dostosowań specyficznych dla serializacji i deserializacji.</span><span class="sxs-lookup"><span data-stu-id="671c3-113">The <xref::::no-loc(System.Text.Json):::.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="671c3-114">Przykłady kodu przedstawione w tym artykule wymagają `using` dyrektyw dla jednej lub obu tych przestrzeni nazw:</span><span class="sxs-lookup"><span data-stu-id="671c3-114">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using :::no-loc(System.Text.Json):::;
using :::no-loc(System.Text.Json):::.Serialization;
```

<span data-ttu-id="671c3-115">Atrybuty z <xref:System.Runtime.Serialization> przestrzeni nazw nie są obsługiwane w programie `:::no-loc(System.Text.Json):::` .</span><span class="sxs-lookup"><span data-stu-id="671c3-115">Attributes from the <xref:System.Runtime.Serialization> namespace aren't supported in `:::no-loc(System.Text.Json):::`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="671c3-116">Pisanie obiektów .NET w formacie JSON (Serializacja)</span><span class="sxs-lookup"><span data-stu-id="671c3-116">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="671c3-117">Aby zapisać dane JSON do ciągu lub do pliku, wywołaj <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A?displayProperty=nameWithType> metodę.</span><span class="sxs-lookup"><span data-stu-id="671c3-117">To write JSON to a string or to a file, call the <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="671c3-118">Poniższy przykład tworzy kod JSON jako ciąg:</span><span class="sxs-lookup"><span data-stu-id="671c3-118">The following example creates JSON as a string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="671c3-119">Poniższy przykład używa kodu synchronicznego do utworzenia pliku JSON:</span><span class="sxs-lookup"><span data-stu-id="671c3-119">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="671c3-120">W poniższym przykładzie jest tworzony plik JSON przy użyciu kodu asynchronicznego:</span><span class="sxs-lookup"><span data-stu-id="671c3-120">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="671c3-121">Powyższe przykłady używają wnioskowania typu dla serializowanego typu.</span><span class="sxs-lookup"><span data-stu-id="671c3-121">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="671c3-122">Przeciążenie `Serialize()` przyjmuje parametr typu ogólnego:</span><span class="sxs-lookup"><span data-stu-id="671c3-122">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="671c3-123">Przykład serializacji</span><span class="sxs-lookup"><span data-stu-id="671c3-123">Serialization example</span></span>

<span data-ttu-id="671c3-124">Oto przykładowa Klasa, która zawiera właściwości typu kolekcji i typ zdefiniowany przez użytkownika:</span><span class="sxs-lookup"><span data-stu-id="671c3-124">Here's an example class that contains collection-type properties and a user-defined type:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

> [!TIP]
> <span data-ttu-id="671c3-125">"POCO" oznacza dla [zwykłego starego obiektu CLR](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span><span class="sxs-lookup"><span data-stu-id="671c3-125">"POCO" stands for [plain old CLR object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span> <span data-ttu-id="671c3-126">POCO to typ .NET, który nie jest zależny od żadnych typów specyficznych dla platformy, na przykład przez dziedziczenie lub atrybuty.</span><span class="sxs-lookup"><span data-stu-id="671c3-126">A POCO is a .NET type that doesn't depend on any framework-specific types, for example, through inheritance or attributes.</span></span>

<span data-ttu-id="671c3-127">Dane wyjściowe JSON serializowania wystąpienia poprzedniego typu wyglądają podobnie jak w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="671c3-127">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="671c3-128">Dane wyjściowe JSON domyślnie są zminimalizowanego:</span><span class="sxs-lookup"><span data-stu-id="671c3-128">The JSON output is minified by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="671c3-129">W poniższym przykładzie przedstawiono ten sam kod JSON, ale sformatowany (to jest, całkiem wydruk z odstępami i wcięciami):</span><span class="sxs-lookup"><span data-stu-id="671c3-129">The following example shows the same JSON, but formatted (that is, pretty-printed with whitespace and indentation):</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": 20,
      "Low": -10
    },
    "Hot": {
      "High": 60,
      "Low": 20
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a><span data-ttu-id="671c3-130">Serializacja do UTF-8</span><span class="sxs-lookup"><span data-stu-id="671c3-130">Serialize to UTF-8</span></span>

<span data-ttu-id="671c3-131">Aby serializować do UTF-8, wywołaj <xref::::no-loc(System.Text.Json):::.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> metodę:</span><span class="sxs-lookup"><span data-stu-id="671c3-131">To serialize to UTF-8, call the <xref::::no-loc(System.Text.Json):::.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="671c3-132"><xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A>Dostępne jest również Przeciążenie, które trwa <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter> .</span><span class="sxs-lookup"><span data-stu-id="671c3-132">A <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A> overload that takes a <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="671c3-133">Serializacja do UTF-8 jest szybsza o 5-10% niż przy użyciu metod opartych na ciągach.</span><span class="sxs-lookup"><span data-stu-id="671c3-133">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="671c3-134">Różnica polega na tym, że bajty (w formacie UTF-8) nie muszą być konwertowane na ciągi (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="671c3-134">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="671c3-135">Zachowanie serializacji</span><span class="sxs-lookup"><span data-stu-id="671c3-135">Serialization behavior</span></span>
::: zone pivot="dotnet-5-0"

* <span data-ttu-id="671c3-136">Domyślnie wszystkie właściwości publiczne są serializowane.</span><span class="sxs-lookup"><span data-stu-id="671c3-136">By default, all public properties are serialized.</span></span> <span data-ttu-id="671c3-137">Można [określić właściwości do ignorowania](#ignore-properties).</span><span class="sxs-lookup"><span data-stu-id="671c3-137">You can [specify properties to ignore](#ignore-properties).</span></span>
* <span data-ttu-id="671c3-138">[Domyślny koder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) wyprowadza znaki nienależące do zestawu znaków ASCII, znaki z uwzględnieniem języka HTML w zakresie ASCII i znaków, które muszą zostać zmienione zgodnie z [specyfikacją JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="671c3-138">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="671c3-139">Domyślnie JSON jest zminimalizowanego.</span><span class="sxs-lookup"><span data-stu-id="671c3-139">By default, JSON is minified.</span></span> <span data-ttu-id="671c3-140">Można tu [wydrukować kod JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="671c3-140">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="671c3-141">Domyślnie wielkość liter w nazwach JSON jest zgodna z nazwami .NET.</span><span class="sxs-lookup"><span data-stu-id="671c3-141">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="671c3-142">Można [dostosować wielkość liter w nazwach JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="671c3-142">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="671c3-143">Domyślnie wykryto odwołania cykliczne i zostały zgłoszone wyjątki.</span><span class="sxs-lookup"><span data-stu-id="671c3-143">By default, circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="671c3-144">Można [zachować odwołania i obsłużyć odwołania cykliczne](#preserve-references-and-handle-circular-references).</span><span class="sxs-lookup"><span data-stu-id="671c3-144">You can [preserve references and handle circular references](#preserve-references-and-handle-circular-references).</span></span>
* <span data-ttu-id="671c3-145">Domyślnie [pola](../../csharp/programming-guide/classes-and-structs/fields.md) są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="671c3-145">By default, [fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span> <span data-ttu-id="671c3-146">Możesz [dołączyć pola](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="671c3-146">You can [include fields](#include-fields).</span></span>

<span data-ttu-id="671c3-147">Jeśli używasz :::no-loc(System.Text.Json)::: bezpośrednio w aplikacji ASP.NET Core, niektóre domyślne zachowania są inne.</span><span class="sxs-lookup"><span data-stu-id="671c3-147">When you use :::no-loc(System.Text.Json)::: indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="671c3-148">Aby uzyskać więcej informacji, zobacz [Ustawienia domyślne sieci Web dla JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="671c3-148">For more information, see [Web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="671c3-149">Domyślnie wszystkie właściwości publiczne są serializowane.</span><span class="sxs-lookup"><span data-stu-id="671c3-149">By default, all public properties are serialized.</span></span> <span data-ttu-id="671c3-150">Można [określić właściwości do ignorowania](#ignore-properties).</span><span class="sxs-lookup"><span data-stu-id="671c3-150">You can [specify properties to ignore](#ignore-properties).</span></span>
* <span data-ttu-id="671c3-151">[Domyślny koder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) wyprowadza znaki nienależące do zestawu znaków ASCII, znaki z uwzględnieniem języka HTML w zakresie ASCII i znaków, które muszą zostać zmienione zgodnie z [specyfikacją JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="671c3-151">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="671c3-152">Domyślnie JSON jest zminimalizowanego.</span><span class="sxs-lookup"><span data-stu-id="671c3-152">By default, JSON is minified.</span></span> <span data-ttu-id="671c3-153">Można tu [wydrukować kod JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="671c3-153">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="671c3-154">Domyślnie wielkość liter w nazwach JSON jest zgodna z nazwami .NET.</span><span class="sxs-lookup"><span data-stu-id="671c3-154">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="671c3-155">Można [dostosować wielkość liter w nazwach JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="671c3-155">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="671c3-156">Wykryto odwołania cykliczne i zostały zgłoszone wyjątki.</span><span class="sxs-lookup"><span data-stu-id="671c3-156">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="671c3-157">[Pola](../../csharp/programming-guide/classes-and-structs/fields.md) są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="671c3-157">[Fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span>
::: zone-end

<span data-ttu-id="671c3-158">Obsługiwane typy to:</span><span class="sxs-lookup"><span data-stu-id="671c3-158">Supported types include:</span></span>
::: zone pivot="dotnet-5-0"

* <span data-ttu-id="671c3-159">Elementy podstawowe platformy .NET, które są mapowane na elementy podstawowe języka JavaScript, takie jak typy liczbowe, ciągi i wartości logiczne.</span><span class="sxs-lookup"><span data-stu-id="671c3-159">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="671c3-160">Obiekty CLR zdefiniowane przez użytkownika [(POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span><span class="sxs-lookup"><span data-stu-id="671c3-160">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="671c3-161">Tablice jednowymiarowe i nieregularne ( `T[][]` ).</span><span class="sxs-lookup"><span data-stu-id="671c3-161">One-dimensional and jagged arrays (`T[][]`).</span></span>
* <span data-ttu-id="671c3-162">Kolekcje i słowniki z następujących przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="671c3-162">Collections and dictionaries from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="671c3-163">Elementy podstawowe platformy .NET, które są mapowane na elementy podstawowe języka JavaScript, takie jak typy liczbowe, ciągi i wartości logiczne.</span><span class="sxs-lookup"><span data-stu-id="671c3-163">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="671c3-164">Obiekty CLR zdefiniowane przez użytkownika [(POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span><span class="sxs-lookup"><span data-stu-id="671c3-164">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="671c3-165">Tablice jednowymiarowe i nieregularne ( `ArrayName[][]` ).</span><span class="sxs-lookup"><span data-stu-id="671c3-165">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="671c3-166">`Dictionary<string,TValue>` gdzie `TValue` is to `object` , `JsonElement` lub poco.</span><span class="sxs-lookup"><span data-stu-id="671c3-166">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="671c3-167">Kolekcje z następujących przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="671c3-167">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

<span data-ttu-id="671c3-168">Można [zaimplementować niestandardowe konwertery](system-text-json-converters-how-to.md) w celu obsługi dodatkowych typów lub zapewnienia funkcjonalności, która nie jest obsługiwana przez wbudowane konwertery.</span><span class="sxs-lookup"><span data-stu-id="671c3-168">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="671c3-169">Jak odczytywać dane JSON do obiektów .NET (deserializacji)</span><span class="sxs-lookup"><span data-stu-id="671c3-169">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="671c3-170">Aby zdeserializować z ciągu lub pliku, wywołaj <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> metodę.</span><span class="sxs-lookup"><span data-stu-id="671c3-170">To deserialize from a string or a file, call the <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="671c3-171">Poniższy przykład odczytuje dane JSON z ciągu i tworzy wystąpienie `WeatherForecastWithPOCOs` klasy pokazanej wcześniej dla [przykładu serializacji](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="671c3-171">The following example reads JSON from a string and creates an instance of the `WeatherForecastWithPOCOs` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="671c3-172">Aby zdeserializować z pliku przy użyciu kodu synchronicznego, Odczytaj plik do ciągu, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-172">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="671c3-173">Aby zdeserializować z pliku przy użyciu kodu asynchronicznego, wywołaj <xref::::no-loc(System.Text.Json):::.JsonSerializer.DeserializeAsync%2A> metodę:</span><span class="sxs-lookup"><span data-stu-id="671c3-173">To deserialize from a file by using asynchronous code, call the <xref::::no-loc(System.Text.Json):::.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="671c3-174">Deserializacja z UTF-8</span><span class="sxs-lookup"><span data-stu-id="671c3-174">Deserialize from UTF-8</span></span>

<span data-ttu-id="671c3-175">Aby zdeserializować z UTF-8, wywołaj <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> Przeciążenie, które pobiera `Utf8JsonReader` lub a `ReadOnlySpan<byte>` , jak pokazano w poniższych przykładach.</span><span class="sxs-lookup"><span data-stu-id="671c3-175">To deserialize from UTF-8, call a <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="671c3-176">W przykładach założono, że kod JSON znajduje się w tablicy bajtów o nazwie jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="671c3-176">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="671c3-177">Zachowanie deserializacji</span><span class="sxs-lookup"><span data-stu-id="671c3-177">Deserialization behavior</span></span>

<span data-ttu-id="671c3-178">Podczas deserializacji kodu JSON stosowane są następujące zachowania:</span><span class="sxs-lookup"><span data-stu-id="671c3-178">The following behaviors apply when deserializing JSON:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="671c3-179">Domyślnie w dopasowaniu nazw właściwości rozróżniana jest wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="671c3-179">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="671c3-180">Można [określić wielkość liter](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="671c3-180">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="671c3-181">Jeśli kod JSON zawiera wartość właściwości tylko do odczytu, wartość jest ignorowana i nie jest zgłaszany żaden wyjątek.</span><span class="sxs-lookup"><span data-stu-id="671c3-181">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="671c3-182">Konstruktory niepubliczne są ignorowane przez serializator.</span><span class="sxs-lookup"><span data-stu-id="671c3-182">Non-public constructors are ignored by the serializer.</span></span>
* <span data-ttu-id="671c3-183">Obsługa deserializacji do niemodyfikowalnych obiektów lub właściwości tylko do odczytu jest obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="671c3-183">Deserialization to immutable objects or read-only properties is supported.</span></span> <span data-ttu-id="671c3-184">Zobacz [zmienne typy i rekordy](#immutable-types-and-records).</span><span class="sxs-lookup"><span data-stu-id="671c3-184">See [Immutable types and Records](#immutable-types-and-records).</span></span>
* <span data-ttu-id="671c3-185">Domyślnie wyliczenia są obsługiwane jako liczby.</span><span class="sxs-lookup"><span data-stu-id="671c3-185">By default, enums are supported as numbers.</span></span> <span data-ttu-id="671c3-186">[Nazwy wyliczenia można serializować jako ciągi](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="671c3-186">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="671c3-187">Domyślnie pola są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="671c3-187">By default, fields are ignored.</span></span> <span data-ttu-id="671c3-188">Możesz [dołączyć pola](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="671c3-188">You can [include fields](#include-fields).</span></span>
* <span data-ttu-id="671c3-189">Domyślnie komentarze lub końcowe przecinki w wyjątkach throw JSON.</span><span class="sxs-lookup"><span data-stu-id="671c3-189">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="671c3-190">Można [zezwolić na komentarze i końcowe przecinki](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="671c3-190">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="671c3-191">[Domyślna głębokość maksymalna](xref::::no-loc(System.Text.Json):::.JsonReaderOptions.MaxDepth) to 64.</span><span class="sxs-lookup"><span data-stu-id="671c3-191">The [default maximum depth](xref::::no-loc(System.Text.Json):::.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="671c3-192">Jeśli używasz :::no-loc(System.Text.Json)::: bezpośrednio w aplikacji ASP.NET Core, niektóre domyślne zachowania są inne.</span><span class="sxs-lookup"><span data-stu-id="671c3-192">When you use :::no-loc(System.Text.Json)::: indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="671c3-193">Aby uzyskać więcej informacji, zobacz [Ustawienia domyślne sieci Web dla JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="671c3-193">For more information, see [Web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="671c3-194">Domyślnie w dopasowaniu nazw właściwości rozróżniana jest wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="671c3-194">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="671c3-195">Można [określić wielkość liter](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="671c3-195">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span> <span data-ttu-id="671c3-196">Aplikacje ASP.NET Core [Domyślnie określają wielkość liter](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="671c3-196">ASP.NET Core apps [specify case-insensitivity by default](#web-defaults-for-jsonserializeroptions).</span></span>
* <span data-ttu-id="671c3-197">Jeśli kod JSON zawiera wartość właściwości tylko do odczytu, wartość jest ignorowana i nie jest zgłaszany żaden wyjątek.</span><span class="sxs-lookup"><span data-stu-id="671c3-197">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="671c3-198">Konstruktor bez parametrów, który może być publiczny, wewnętrzny lub prywatny, jest używany do deserializacji.</span><span class="sxs-lookup"><span data-stu-id="671c3-198">A parameterless constructor, which can be public, internal, or private, is used for deserialization.</span></span>
* <span data-ttu-id="671c3-199">Deserializacja z niezmiennymi obiektami lub właściwościami tylko do odczytu nie jest obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="671c3-199">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="671c3-200">Domyślnie wyliczenia są obsługiwane jako liczby.</span><span class="sxs-lookup"><span data-stu-id="671c3-200">By default, enums are supported as numbers.</span></span> <span data-ttu-id="671c3-201">[Nazwy wyliczenia można serializować jako ciągi](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="671c3-201">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="671c3-202">Pola nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="671c3-202">Fields aren't supported.</span></span>
* <span data-ttu-id="671c3-203">Domyślnie komentarze lub końcowe przecinki w wyjątkach throw JSON.</span><span class="sxs-lookup"><span data-stu-id="671c3-203">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="671c3-204">Można [zezwolić na komentarze i końcowe przecinki](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="671c3-204">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="671c3-205">[Domyślna głębokość maksymalna](xref::::no-loc(System.Text.Json):::.JsonReaderOptions.MaxDepth) to 64.</span><span class="sxs-lookup"><span data-stu-id="671c3-205">The [default maximum depth](xref::::no-loc(System.Text.Json):::.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="671c3-206">Jeśli używasz :::no-loc(System.Text.Json)::: bezpośrednio w aplikacji ASP.NET Core, niektóre domyślne zachowania są inne.</span><span class="sxs-lookup"><span data-stu-id="671c3-206">When you use :::no-loc(System.Text.Json)::: indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="671c3-207">Aby uzyskać więcej informacji, zobacz [Ustawienia domyślne sieci Web dla JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="671c3-207">For more information, see [Web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

<span data-ttu-id="671c3-208">[Konwertery niestandardowe można zaimplementować](system-text-json-converters-how-to.md) w celu zapewnienia funkcjonalności, która nie jest obsługiwana przez wbudowane konwertery.</span><span class="sxs-lookup"><span data-stu-id="671c3-208">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="671c3-209">Serializacja do sformatowanego pliku JSON</span><span class="sxs-lookup"><span data-stu-id="671c3-209">Serialize to formatted JSON</span></span>

<span data-ttu-id="671c3-210">Aby całkiem wydrukować dane wyjściowe JSON, ustaw wartość <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> `true` :</span><span class="sxs-lookup"><span data-stu-id="671c3-210">To pretty-print the JSON output, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="671c3-211">Oto przykład typu do serializacji i całkiem wydrukowanych danych wyjściowych JSON:</span><span class="sxs-lookup"><span data-stu-id="671c3-211">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="include-fields"></a><span data-ttu-id="671c3-212">Dołącz pola</span><span class="sxs-lookup"><span data-stu-id="671c3-212">Include fields</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="671c3-213">Użyj <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> Ustawienia globalnego lub atrybutu [[JsonInclude]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIncludeAttribute) , aby dołączyć pola podczas serializacji lub deserializacji, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-213">Use the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> global setting or the [[JsonInclude]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIncludeAttribute) attribute to include fields when serializing or deserializing, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="15,17,19,31":::

<span data-ttu-id="671c3-214">Aby zignorować pola tylko do odczytu, użyj <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> Ustawienia globalnego.</span><span class="sxs-lookup"><span data-stu-id="671c3-214">To ignore read-only fields, use the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="671c3-215">Pola nie są obsługiwane w :::no-loc(System.Text.Json)::: programie .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="671c3-215">Fields are not supported in :::no-loc(System.Text.Json)::: in .NET Core 3.1.</span></span> <span data-ttu-id="671c3-216">Te funkcje mogą zapewniać [konwertery niestandardowe](system-text-json-converters-how-to.md) .</span><span class="sxs-lookup"><span data-stu-id="671c3-216">[Custom converters](system-text-json-converters-how-to.md) can provide this functionality.</span></span>
::: zone-end

## <a name="customize-json-names-and-values"></a><span data-ttu-id="671c3-217">Dostosowywanie nazw i wartości JSON</span><span class="sxs-lookup"><span data-stu-id="671c3-217">Customize JSON names and values</span></span>

<span data-ttu-id="671c3-218">Domyślnie nazwy właściwości i klucze słownika nie są zmieniane w danych wyjściowych JSON, włącznie z wielkością liter.</span><span class="sxs-lookup"><span data-stu-id="671c3-218">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="671c3-219">Wartości wyliczeniowe są reprezentowane jako liczby.</span><span class="sxs-lookup"><span data-stu-id="671c3-219">Enum values are represented as numbers.</span></span> <span data-ttu-id="671c3-220">W tej sekcji wyjaśniono, jak:</span><span class="sxs-lookup"><span data-stu-id="671c3-220">This section explains how to:</span></span>

* [<span data-ttu-id="671c3-221">Dostosowywanie poszczególnych nazw właściwości</span><span class="sxs-lookup"><span data-stu-id="671c3-221">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="671c3-222">Konwertuj wszystkie nazwy właściwości na notacji CamelCase przypadku</span><span class="sxs-lookup"><span data-stu-id="671c3-222">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="671c3-223">Implementowanie zasad nazewnictwa właściwości niestandardowych</span><span class="sxs-lookup"><span data-stu-id="671c3-223">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="671c3-224">Konwertuj klucze słownika na notacji CamelCase</span><span class="sxs-lookup"><span data-stu-id="671c3-224">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="671c3-225">Konwertuj wyliczenia na ciągi i notacji CamelCase wielkość liter</span><span class="sxs-lookup"><span data-stu-id="671c3-225">Convert enums to strings and camel case</span></span>](#enums-as-strings)

<span data-ttu-id="671c3-226">W przypadku innych scenariuszy, które wymagają specjalnej obsługi nazw i wartości właściwości JSON, można [zaimplementować konwertery niestandardowe](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="671c3-226">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="671c3-227">Dostosowywanie poszczególnych nazw właściwości</span><span class="sxs-lookup"><span data-stu-id="671c3-227">Customize individual property names</span></span>

<span data-ttu-id="671c3-228">Aby ustawić nazwę poszczególnych właściwości, Użyj atrybutu [[JsonPropertyName]](xref::::no-loc(System.Text.Json):::.Serialization.JsonPropertyNameAttribute) .</span><span class="sxs-lookup"><span data-stu-id="671c3-228">To set the name of individual properties, use the [[JsonPropertyName]](xref::::no-loc(System.Text.Json):::.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="671c3-229">Oto przykład typu do serializacji i powstającego JSON:</span><span class="sxs-lookup"><span data-stu-id="671c3-229">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="671c3-230">Nazwa właściwości ustawiona przez ten atrybut:</span><span class="sxs-lookup"><span data-stu-id="671c3-230">The property name set by this attribute:</span></span>

* <span data-ttu-id="671c3-231">Stosuje się w obu kierunkach dla serializacji i deserializacji.</span><span class="sxs-lookup"><span data-stu-id="671c3-231">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="671c3-232">Ma pierwszeństwo przed zasadami nazewnictwa właściwości.</span><span class="sxs-lookup"><span data-stu-id="671c3-232">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="671c3-233">Użyj notacji CamelCase przypadku dla wszystkich nazw właściwości JSON</span><span class="sxs-lookup"><span data-stu-id="671c3-233">Use camel case for all JSON property names</span></span>

<span data-ttu-id="671c3-234">Aby użyć notacji CamelCase przypadku wszystkich nazw właściwości JSON, ustaw wartość <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> `JsonNamingPolicy.CamelCase` tak, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-234">To use camel case for all JSON property names, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="671c3-235">Oto przykładowa Klasa do serializacji i danych wyjściowych JSON:</span><span class="sxs-lookup"><span data-stu-id="671c3-235">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="671c3-236">Zasady nazewnictwa właściwości przypadku notacji CamelCase:</span><span class="sxs-lookup"><span data-stu-id="671c3-236">The camel case property naming policy:</span></span>

* <span data-ttu-id="671c3-237">Dotyczy serializacji i deserializacji.</span><span class="sxs-lookup"><span data-stu-id="671c3-237">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="671c3-238">Jest zastępowany przez `[JsonPropertyName]` atrybuty.</span><span class="sxs-lookup"><span data-stu-id="671c3-238">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="671c3-239">Jest to dlatego, że nazwa właściwości JSON `Wind` w przykładzie nie jest notacji CamelCase.</span><span class="sxs-lookup"><span data-stu-id="671c3-239">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="671c3-240">Użyj niestandardowych zasad nazewnictwa właściwości JSON</span><span class="sxs-lookup"><span data-stu-id="671c3-240">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="671c3-241">Aby użyć niestandardowych zasad nazewnictwa właściwości JSON, Utwórz klasę, która pochodzi od <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy> i przesłania <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy.ConvertName%2A> metodę, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-241">To use a custom JSON property naming policy, create a class that derives from <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy> and override the <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="671c3-242">Następnie ustaw <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> Właściwość na wystąpienie klasy zasad nazewnictwa:</span><span class="sxs-lookup"><span data-stu-id="671c3-242">Then set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="671c3-243">Oto przykładowa Klasa do serializacji i danych wyjściowych JSON:</span><span class="sxs-lookup"><span data-stu-id="671c3-243">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="671c3-244">Zasady nazewnictwa właściwości JSON:</span><span class="sxs-lookup"><span data-stu-id="671c3-244">The JSON property naming policy:</span></span>

* <span data-ttu-id="671c3-245">Dotyczy serializacji i deserializacji.</span><span class="sxs-lookup"><span data-stu-id="671c3-245">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="671c3-246">Jest zastępowany przez `[JsonPropertyName]` atrybuty.</span><span class="sxs-lookup"><span data-stu-id="671c3-246">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="671c3-247">Jest to dlatego, że nazwa właściwości JSON `Wind` w przykładzie nie jest wielką literą.</span><span class="sxs-lookup"><span data-stu-id="671c3-247">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="671c3-248">Klucze słownika przypadku notacji CamelCase</span><span class="sxs-lookup"><span data-stu-id="671c3-248">Camel case dictionary keys</span></span>

<span data-ttu-id="671c3-249">Jeśli właściwość obiektu, który ma zostać Zserializowany, jest typu `Dictionary<string,TValue>` , `string` klucze mogą być konwertowane na notacji CamelCase przypadku.</span><span class="sxs-lookup"><span data-stu-id="671c3-249">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="671c3-250">W tym celu ustaw wartość <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DictionaryKeyPolicy> `JsonNamingPolicy.CamelCase` , jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-250">To do that, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="671c3-251">Serializacja obiektu ze słownikiem o nazwie `TemperatureRanges` , który ma pary klucz-wartość `"ColdMinTemp", 20` i `"HotMinTemp", 40` spowodowałaby wyjście JSON podobne do poniższego przykładu:</span><span class="sxs-lookup"><span data-stu-id="671c3-251">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="671c3-252">Zasady nazewnictwa przypadków notacji CamelCase dla kluczy słownika mają zastosowanie tylko do serializacji.</span><span class="sxs-lookup"><span data-stu-id="671c3-252">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="671c3-253">W przypadku deserializacji słownika klucze będą zgodne z plikiem JSON nawet w przypadku określenia `JsonNamingPolicy.CamelCase` dla `DictionaryKeyPolicy` .</span><span class="sxs-lookup"><span data-stu-id="671c3-253">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="671c3-254">Wyliczenia jako ciągi</span><span class="sxs-lookup"><span data-stu-id="671c3-254">Enums as strings</span></span>

<span data-ttu-id="671c3-255">Domyślnie wyliczenia są serializowane jako liczby.</span><span class="sxs-lookup"><span data-stu-id="671c3-255">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="671c3-256">Aby serializować nazwy wyliczenia jako ciągi, użyj <xref::::no-loc(System.Text.Json):::.Serialization.JsonStringEnumConverter> .</span><span class="sxs-lookup"><span data-stu-id="671c3-256">To serialize enum names as strings, use the <xref::::no-loc(System.Text.Json):::.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="671c3-257">Załóżmy na przykład, że trzeba serializować następujące klasy, które mają Wyliczenie:</span><span class="sxs-lookup"><span data-stu-id="671c3-257">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="671c3-258">Jeśli podsumowanie jest `Hot` , domyślnie serializowany kod JSON ma wartość liczbową 3:</span><span class="sxs-lookup"><span data-stu-id="671c3-258">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="671c3-259">Następujący przykładowy kod serializować nazwy wyliczenia zamiast wartości liczbowych i konwertuje nazwy na notacji CamelCase:</span><span class="sxs-lookup"><span data-stu-id="671c3-259">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="671c3-260">Wynikowy kod JSON wygląda podobnie do poniższego przykładu:</span><span class="sxs-lookup"><span data-stu-id="671c3-260">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="671c3-261">Można również deserializować nazwy ciągów wyliczenia, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-261">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="ignore-properties"></a><span data-ttu-id="671c3-262">Ignoruj właściwości</span><span class="sxs-lookup"><span data-stu-id="671c3-262">Ignore properties</span></span>

<span data-ttu-id="671c3-263">Domyślnie wszystkie właściwości publiczne są serializowane.</span><span class="sxs-lookup"><span data-stu-id="671c3-263">By default, all public properties are serialized.</span></span> <span data-ttu-id="671c3-264">Jeśli nie chcesz, aby niektóre z nich pojawiały się w danych wyjściowych JSON, masz kilka opcji.</span><span class="sxs-lookup"><span data-stu-id="671c3-264">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="671c3-265">W tej sekcji opisano sposób ignorowania:</span><span class="sxs-lookup"><span data-stu-id="671c3-265">This section explains how to ignore:</span></span>

::: zone pivot="dotnet-5-0"

* [<span data-ttu-id="671c3-266">Poszczególne właściwości</span><span class="sxs-lookup"><span data-stu-id="671c3-266">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="671c3-267">Wszystkie właściwości tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="671c3-267">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="671c3-268">Wszystkie właściwości o wartości null</span><span class="sxs-lookup"><span data-stu-id="671c3-268">All null-value properties</span></span>](#ignore-all-null-value-properties)
* [<span data-ttu-id="671c3-269">Wszystkie właściwości domyślne wartości</span><span class="sxs-lookup"><span data-stu-id="671c3-269">All default-value properties</span></span>](#ignore-all-default-value-properties)
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [<span data-ttu-id="671c3-270">Poszczególne właściwości</span><span class="sxs-lookup"><span data-stu-id="671c3-270">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="671c3-271">Wszystkie właściwości tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="671c3-271">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="671c3-272">Wszystkie właściwości o wartości null</span><span class="sxs-lookup"><span data-stu-id="671c3-272">All null-value properties</span></span>](#ignore-all-null-value-properties)
::: zone-end

### <a name="ignore-individual-properties"></a><span data-ttu-id="671c3-273">Ignoruj poszczególne właściwości</span><span class="sxs-lookup"><span data-stu-id="671c3-273">Ignore individual properties</span></span>

<span data-ttu-id="671c3-274">Aby zignorować poszczególne właściwości, Użyj atrybutu [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute) .</span><span class="sxs-lookup"><span data-stu-id="671c3-274">To ignore individual properties, use the [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="671c3-275">Oto przykład typu do serializacji i danych wyjściowych JSON:</span><span class="sxs-lookup"><span data-stu-id="671c3-275">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

::: zone pivot="dotnet-5-0"
<span data-ttu-id="671c3-276">Aby określić wykluczenie warunkowe, należy ustawić właściwość [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute) atrybutu `Condition` .</span><span class="sxs-lookup"><span data-stu-id="671c3-276">You can specify conditional exclusion by setting the [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute) attribute's `Condition` property.</span></span> <span data-ttu-id="671c3-277"><xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition>Wyliczenie zapewnia następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="671c3-277">The <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition> enum provides the following options:</span></span>

* <span data-ttu-id="671c3-278">`Always` -Właściwość jest zawsze ignorowana.</span><span class="sxs-lookup"><span data-stu-id="671c3-278">`Always` - The property is always ignored.</span></span> <span data-ttu-id="671c3-279">Jeśli `Condition` wartość nie jest określona, założono, że ta opcja jest.</span><span class="sxs-lookup"><span data-stu-id="671c3-279">If no `Condition` is specified, this option is assumed.</span></span>
* <span data-ttu-id="671c3-280">`Never` -Właściwość jest zawsze serializowana i deserializowana, niezależnie od `DefaultIgnoreCondition` `IgnoreReadOnlyProperties` `IgnoreReadOnlyFields` ustawień globalnych, i.</span><span class="sxs-lookup"><span data-stu-id="671c3-280">`Never` - The property is always serialized and deserialized, regardless of the `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties`, and `IgnoreReadOnlyFields` global settings.</span></span>
* <span data-ttu-id="671c3-281">`WhenWritingDefault` -Właściwość jest ignorowana podczas serializacji, jeśli jest typem referencyjnym `null` lub typem wartości `default` .</span><span class="sxs-lookup"><span data-stu-id="671c3-281">`WhenWritingDefault` - The property is ignored on serialization if it's a reference type `null` or a value type `default`.</span></span>
* <span data-ttu-id="671c3-282">`WhenWritingNull` -Właściwość jest ignorowana podczas serializacji, jeśli jest typem referencyjnym `null` .</span><span class="sxs-lookup"><span data-stu-id="671c3-282">`WhenWritingNull` - The property is ignored on serialization if it's a reference type `null`.</span></span>

<span data-ttu-id="671c3-283">Poniższy przykład ilustruje użycie właściwości [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute) atrybutu `Condition` :</span><span class="sxs-lookup"><span data-stu-id="671c3-283">The following example illustrates use of the [[JsonIgnore]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreAttribute) attribute's `Condition` property:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

### <a name="ignore-all-read-only-properties"></a><span data-ttu-id="671c3-284">Ignoruj wszystkie właściwości tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="671c3-284">Ignore all read-only properties</span></span>

<span data-ttu-id="671c3-285">Właściwość jest tylko do odczytu, jeśli zawiera publiczną metodę pobierającą, ale nie do publicznej metody ustawiającej.</span><span class="sxs-lookup"><span data-stu-id="671c3-285">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="671c3-286">Aby zignorować wszystkie właściwości tylko do odczytu podczas serializacji, ustaw wartość <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> na `true` , jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-286">To ignore all read-only properties when serializing, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="671c3-287">Oto przykład typu do serializacji i danych wyjściowych JSON:</span><span class="sxs-lookup"><span data-stu-id="671c3-287">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="671c3-288">Ta opcja ma zastosowanie tylko do serializacji.</span><span class="sxs-lookup"><span data-stu-id="671c3-288">This option applies only to serialization.</span></span> <span data-ttu-id="671c3-289">Podczas deserializacji właściwości tylko do odczytu są domyślnie ignorowane.</span><span class="sxs-lookup"><span data-stu-id="671c3-289">During deserialization, read-only properties are ignored by default.</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="671c3-290">Ta opcja ma zastosowanie tylko do właściwości.</span><span class="sxs-lookup"><span data-stu-id="671c3-290">This option applies only to properties.</span></span> <span data-ttu-id="671c3-291">Aby zignorować pola tylko do odczytu podczas [serializacji pól](#include-fields), użyj <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> Ustawienia globalnego.</span><span class="sxs-lookup"><span data-stu-id="671c3-291">To ignore read-only fields when [serializing fields](#include-fields), use the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

### <a name="ignore-all-null-value-properties"></a><span data-ttu-id="671c3-292">Ignoruj wszystkie właściwości o wartości null</span><span class="sxs-lookup"><span data-stu-id="671c3-292">Ignore all null-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="671c3-293">Aby zignorować wszystkie właściwości wartości null, należy ustawić <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DefaultIgnoreCondition> Właściwość na <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition.WhenWritingNull> , jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-293">To ignore all null-value properties, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition.WhenWritingNull>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="671c3-294">Aby ignorować wszystkie właściwości null wartości podczas serializacji, należy ustawić <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreNullValues> Właściwość na `true` , jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-294">To ignore all null-value properties when serializing, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="671c3-295">Oto przykład obiektu do serializacji i danych wyjściowych JSON:</span><span class="sxs-lookup"><span data-stu-id="671c3-295">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="671c3-296">Właściwość</span><span class="sxs-lookup"><span data-stu-id="671c3-296">Property</span></span> |<span data-ttu-id="671c3-297">Wartość</span><span class="sxs-lookup"><span data-stu-id="671c3-297">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="671c3-298">Date</span><span class="sxs-lookup"><span data-stu-id="671c3-298">Date</span></span>    | <span data-ttu-id="671c3-299">8/1/2019 12:00:00 AM – 07:00</span><span class="sxs-lookup"><span data-stu-id="671c3-299">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="671c3-300">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="671c3-300">TemperatureCelsius</span></span>| <span data-ttu-id="671c3-301">25</span><span class="sxs-lookup"><span data-stu-id="671c3-301">25</span></span> |
| <span data-ttu-id="671c3-302">Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="671c3-302">Summary</span></span>| <span data-ttu-id="671c3-303">wartość null</span><span class="sxs-lookup"><span data-stu-id="671c3-303">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

### <a name="ignore-all-default-value-properties"></a><span data-ttu-id="671c3-304">Ignoruj wszystkie właściwości domyślne wartości</span><span class="sxs-lookup"><span data-stu-id="671c3-304">Ignore all default-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="671c3-305">Aby zapobiec serializacji wartości domyślnych we właściwościach typu wartości, ustaw <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DefaultIgnoreCondition> Właściwość na <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition.WhenWritingDefault> , jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-305">To prevent serialization of default values in value type properties, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref::::no-loc(System.Text.Json):::.Serialization.JsonIgnoreCondition.WhenWritingDefault>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

<span data-ttu-id="671c3-306">To `WhenWritingDefault` ustawienie uniemożliwia również serializację właściwości typu odwołania o wartości null.</span><span class="sxs-lookup"><span data-stu-id="671c3-306">The `WhenWritingDefault` setting also prevents serialization of null-value reference type properties.</span></span>

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="671c3-307">Nie ma wbudowanego sposobu, aby zapobiec serializacji właściwości z wartościami domyślnymi typu wartości w :::no-loc(System.Text.Json)::: programie .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="671c3-307">There is no built-in way to prevent serialization of properties with value type defaults in :::no-loc(System.Text.Json)::: in .NET Core 3.1.</span></span>
::: zone-end

## <a name="customize-character-encoding"></a><span data-ttu-id="671c3-308">Dostosuj kodowanie znaków</span><span class="sxs-lookup"><span data-stu-id="671c3-308">Customize character encoding</span></span>

<span data-ttu-id="671c3-309">Domyślnie serializator wyprowadza wszystkie znaki nienależące do zestawu znaków ASCII.</span><span class="sxs-lookup"><span data-stu-id="671c3-309">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="671c3-310">Oznacza to, że zastępuje je, `\uxxxx` gdzie `xxxx` jest kodem Unicode znaku.</span><span class="sxs-lookup"><span data-stu-id="671c3-310">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="671c3-311">Na przykład, jeśli `Summary` Właściwość jest ustawiona na wartość cyrylicy жарко, `WeatherForecast` obiekt jest serializowany, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-311">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="671c3-312">Serializowanie zestawów znaków języka</span><span class="sxs-lookup"><span data-stu-id="671c3-312">Serialize language character sets</span></span>

<span data-ttu-id="671c3-313">Aby serializować zestawy znaków z co najmniej jednego języka bez ucieczki, określ [zakresy Unicode](xref:System.Text.Unicode.UnicodeRanges) podczas tworzenia wystąpienia <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> , jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-313">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="671c3-314">Ten kod nie ma ucieczki znaków cyrylicy lub greckich.</span><span class="sxs-lookup"><span data-stu-id="671c3-314">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="671c3-315">Jeśli `Summary` Właściwość jest ustawiona na wartość cyrylicy жарко, `WeatherForecast` obiekt jest serializowany, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-315">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="671c3-316">Aby serializować wszystkie zestawy językowe bez ucieczki, użyj <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="671c3-316">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="671c3-317">Serializacja określonych znaków</span><span class="sxs-lookup"><span data-stu-id="671c3-317">Serialize specific characters</span></span>

<span data-ttu-id="671c3-318">Alternatywą jest określenie pojedynczych znaków, które mają być dozwolone, bez konieczności ucieczki.</span><span class="sxs-lookup"><span data-stu-id="671c3-318">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="671c3-319">Poniższy przykład serializacji tylko dwa pierwsze znaki жарко:</span><span class="sxs-lookup"><span data-stu-id="671c3-319">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="671c3-320">Oto przykład kodu JSON utworzonego przez poprzedni kod:</span><span class="sxs-lookup"><span data-stu-id="671c3-320">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="671c3-321">Serializować wszystkie znaki</span><span class="sxs-lookup"><span data-stu-id="671c3-321">Serialize all characters</span></span>

<span data-ttu-id="671c3-322">Aby zminimalizować liczbę ucieczki, można użyć <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> , jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-322">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="671c3-323">W porównaniu z domyślnym koderem `UnsafeRelaxedJsonEscaping` koder jest bardziej ograniczając, aby umożliwić przekazywanie znaków przez niezmieniony:</span><span class="sxs-lookup"><span data-stu-id="671c3-323">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="671c3-324">Nie ucieczk znaków w języku HTML, takich jak `<` , `>` , `&` , i `'` .</span><span class="sxs-lookup"><span data-stu-id="671c3-324">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="671c3-325">Nie oferuje żadnej dodatkowej ochrony przed atakami na ataki typu XSS lub ujawnienie informacji, takich jak te, które mogą wynikać z klienta i serwera bez zgody na *zestaw znaków*.</span><span class="sxs-lookup"><span data-stu-id="671c3-325">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="671c3-326">Używaj niebezpiecznego kodera tylko wtedy, gdy wiadomo, że klient będzie interpretować otrzymany ładunek jako zakodowany w formacie JSON UTF-8.</span><span class="sxs-lookup"><span data-stu-id="671c3-326">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="671c3-327">Można na przykład użyć go, jeśli serwer wysyła nagłówek odpowiedzi `Content-Type: application/json; charset=utf-8` .</span><span class="sxs-lookup"><span data-stu-id="671c3-327">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="671c3-328">Nigdy nie Zezwalaj na `UnsafeRelaxedJsonEscaping` emitowanie nieprzetworzonych danych wyjściowych do strony HTML lub `<script>` elementu.</span><span class="sxs-lookup"><span data-stu-id="671c3-328">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="671c3-329">Serializowanie właściwości klas pochodnych</span><span class="sxs-lookup"><span data-stu-id="671c3-329">Serialize properties of derived classes</span></span>

<span data-ttu-id="671c3-330">Serializacja hierarchii typów polimorficznych nie jest obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="671c3-330">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="671c3-331">Na przykład, jeśli właściwość jest zdefiniowana jako interfejs lub Klasa abstrakcyjna, tylko właściwości zdefiniowane w interfejsie lub klasie abstrakcyjnej są serializowane, nawet jeśli typ środowiska uruchomieniowego ma dodatkowe właściwości.</span><span class="sxs-lookup"><span data-stu-id="671c3-331">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="671c3-332">Wyjątki dotyczące tego zachowania zostały omówione w tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="671c3-332">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="671c3-333">Załóżmy na przykład, że masz `WeatherForecast` klasę i klasę pochodną `WeatherForecastDerived` :</span><span class="sxs-lookup"><span data-stu-id="671c3-333">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="671c3-334">I Załóżmy, że argument typu `Serialize` metody w czasie kompilacji to `WeatherForecast` :</span><span class="sxs-lookup"><span data-stu-id="671c3-334">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="671c3-335">W tym scenariuszu `WindSpeed` Właściwość nie jest serializowana, nawet jeśli `weatherForecast` obiekt jest rzeczywiście `WeatherForecastDerived` obiektem.</span><span class="sxs-lookup"><span data-stu-id="671c3-335">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="671c3-336">Tylko właściwości klasy bazowej są serializowane:</span><span class="sxs-lookup"><span data-stu-id="671c3-336">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="671c3-337">Takie zachowanie ma na celu zapobieganie przypadkowemu narażeniu danych w pochodnym typie tworzonym przez środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="671c3-337">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="671c3-338">Aby serializować właściwości typu pochodnego w poprzednim przykładzie, należy użyć jednej z następujących metod:</span><span class="sxs-lookup"><span data-stu-id="671c3-338">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="671c3-339">Wywołaj Przeciążenie <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A> , które pozwala określić typ w czasie wykonywania:</span><span class="sxs-lookup"><span data-stu-id="671c3-339">Call an overload of <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A> that lets you specify the type at run time:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="671c3-340">Zadeklaruj obiekt, który ma zostać Zserializowany jako `object` .</span><span class="sxs-lookup"><span data-stu-id="671c3-340">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="671c3-341">W poprzednim przykładowym scenariuszu oba podejścia powodują, że `WindSpeed` Właściwość powinna zostać uwzględniona w danych wyjściowych JSON:</span><span class="sxs-lookup"><span data-stu-id="671c3-341">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="671c3-342">Te podejścia zapewniają serializację polimorficzne tylko dla obiektu głównego, który ma być serializowany, a nie dla właściwości tego obiektu głównego.</span><span class="sxs-lookup"><span data-stu-id="671c3-342">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="671c3-343">Można uzyskać serializację polimorficzny dla obiektów niższego poziomu, jeśli zdefiniujesz je jako typ `object` .</span><span class="sxs-lookup"><span data-stu-id="671c3-343">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="671c3-344">Na przykład załóżmy, `WeatherForecast` że Klasa ma właściwość o nazwie `PreviousForecast` , która może być zdefiniowana jako typ `WeatherForecast` lub `object` :</span><span class="sxs-lookup"><span data-stu-id="671c3-344">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="671c3-345">Jeśli `PreviousForecast` Właściwość zawiera wystąpienie `WeatherForecastDerived` :</span><span class="sxs-lookup"><span data-stu-id="671c3-345">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="671c3-346">Dane wyjściowe JSON z serializacji `WeatherForecastWithPrevious` **nie obejmują** `WindSpeed` .</span><span class="sxs-lookup"><span data-stu-id="671c3-346">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="671c3-347">Dane wyjściowe JSON z serializacji `WeatherForecastWithPreviousAsObject` **obejmują** `WindSpeed` .</span><span class="sxs-lookup"><span data-stu-id="671c3-347">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="671c3-348">Aby serializować `WeatherForecastWithPreviousAsObject` , nie jest konieczne wywołanie `Serialize<object>` lub `GetType` ponieważ obiekt główny nie jest tym, który może znajdować się w typie pochodnym.</span><span class="sxs-lookup"><span data-stu-id="671c3-348">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="671c3-349">Poniższy przykład kodu nie wywołuje `Serialize<object>` lub `GetType` :</span><span class="sxs-lookup"><span data-stu-id="671c3-349">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="671c3-350">Powyższy kod poprawnie serializować `WeatherForecastWithPreviousAsObject` :</span><span class="sxs-lookup"><span data-stu-id="671c3-350">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "PreviousForecast": {
    "WindSpeed": 35,
    "Date": "2019-08-01T00:00:00-07:00",
    "TemperatureCelsius": 25,
    "Summary": "Hot"
  }
}
```

<span data-ttu-id="671c3-351">To samo podejście do definiowania właściwości jako `object` współdziałanie z interfejsami.</span><span class="sxs-lookup"><span data-stu-id="671c3-351">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="671c3-352">Załóżmy, że masz następujący interfejs i implementacja, i chcesz serializować klasę o właściwościach zawierających wystąpienia implementacji:</span><span class="sxs-lookup"><span data-stu-id="671c3-352">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

<span data-ttu-id="671c3-353">Podczas serializacji wystąpienia elementu `Forecasts` , `Tuesday` wyświetlana `WindSpeed` jest tylko właściwość, ponieważ `Tuesday` jest zdefiniowana jako `object` :</span><span class="sxs-lookup"><span data-stu-id="671c3-353">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="671c3-354">Poniższy przykład pokazuje kod JSON, który wynika z poprzedniego kodu:</span><span class="sxs-lookup"><span data-stu-id="671c3-354">The following example shows the JSON that results from the preceding code:</span></span>

```json
{
  "Monday": {
    "Date": "2020-01-06T00:00:00-08:00",
    "TemperatureCelsius": 10,
    "Summary": "Cool"
  },
  "Tuesday": {
    "Date": "2020-01-07T00:00:00-08:00",
    "TemperatureCelsius": 11,
    "Summary": "Rainy",
    "WindSpeed": 10
  }
}
```

<span data-ttu-id="671c3-355">Aby uzyskać więcej informacji na temat **serializacji** polimorficznej i informacje o **deserializacji** , zobacz [Jak przeprowadzić migrację z :::no-loc(Newtonsoft.Json)::: do :::no-loc(System.Text.Json):::](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span><span class="sxs-lookup"><span data-stu-id="671c3-355">For more information about polymorphic **serialization** , and for information about **deserialization** , see [How to migrate from :::no-loc(Newtonsoft.Json)::: to :::no-loc(System.Text.Json):::](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="671c3-356">Zezwalaj na komentarze i końcowe przecinki</span><span class="sxs-lookup"><span data-stu-id="671c3-356">Allow comments and trailing commas</span></span>

<span data-ttu-id="671c3-357">Domyślnie Komentarze i końcowe przecinki są niedozwolone w notacji JSON.</span><span class="sxs-lookup"><span data-stu-id="671c3-357">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="671c3-358">Aby zezwolić na komentarze w formacie JSON, ustaw <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> Właściwość na `JsonCommentHandling.Skip` .</span><span class="sxs-lookup"><span data-stu-id="671c3-358">To allow comments in the JSON, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="671c3-359">I aby zezwolić na końcowe przecinki, należy ustawić <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> Właściwość na `true` .</span><span class="sxs-lookup"><span data-stu-id="671c3-359">And to allow trailing commas, set the <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="671c3-360">Poniższy przykład pokazuje, jak:</span><span class="sxs-lookup"><span data-stu-id="671c3-360">The following example shows how to allow both:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="671c3-361">Oto przykładowy kod JSON z komentarzami i końcowym przecinkiem:</span><span class="sxs-lookup"><span data-stu-id="671c3-361">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="671c3-362">Dopasowanie właściwości bez uwzględniania wielkości liter</span><span class="sxs-lookup"><span data-stu-id="671c3-362">Case-insensitive property matching</span></span>

<span data-ttu-id="671c3-363">Domyślnie deserializacja wyszukuje dopasowania nazw właściwości z uwzględnieniem wielkości liter między formatem JSON a właściwościami obiektu docelowego.</span><span class="sxs-lookup"><span data-stu-id="671c3-363">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="671c3-364">Aby zmienić to zachowanie, ustaw opcję <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> na `true` :</span><span class="sxs-lookup"><span data-stu-id="671c3-364">To change that behavior, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="671c3-365">Oto przykład JSON z nazwami właściwości przypadku notacji CamelCase.</span><span class="sxs-lookup"><span data-stu-id="671c3-365">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="671c3-366">Można ją zdeserializować do następującego typu, który ma nazwy właściwości przypadku języka Pascal.</span><span class="sxs-lookup"><span data-stu-id="671c3-366">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="671c3-367">Obsługa przepełnienia kodu JSON</span><span class="sxs-lookup"><span data-stu-id="671c3-367">Handle overflow JSON</span></span>

<span data-ttu-id="671c3-368">Podczas deserializacji można odbierać dane w formacie JSON, które nie są reprezentowane przez właściwości typu docelowego.</span><span class="sxs-lookup"><span data-stu-id="671c3-368">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="671c3-369">Załóżmy na przykład, że typ docelowy to:</span><span class="sxs-lookup"><span data-stu-id="671c3-369">For example, suppose your target type is this:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="671c3-370">I kod JSON do deserializacji jest następujący:</span><span class="sxs-lookup"><span data-stu-id="671c3-370">And the JSON to be deserialized is this:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="671c3-371">W przypadku deserializacji kodu JSON pokazanego w pokazanym typie, `DatesAvailable` `SummaryWords` właściwości i mają wartość Nowhere to go i są tracone.</span><span class="sxs-lookup"><span data-stu-id="671c3-371">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="671c3-372">Aby przechwycić dodatkowe dane, takie jak te właściwości, zastosuj atrybut [[JsonExtensionData]](xref::::no-loc(System.Text.Json):::.Serialization.JsonExtensionDataAttribute) do właściwości typu `Dictionary<string,object>` lub `Dictionary<string,JsonElement>` :</span><span class="sxs-lookup"><span data-stu-id="671c3-372">To capture extra data such as these properties, apply the [[JsonExtensionData]](xref::::no-loc(System.Text.Json):::.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="671c3-373">Podczas deserializacji kodu JSON pokazanego wcześniej w tym typie próbkowania dodatkowe dane staną się parami klucz-wartość `ExtensionData` Właściwości:</span><span class="sxs-lookup"><span data-stu-id="671c3-373">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="671c3-374">Właściwość</span><span class="sxs-lookup"><span data-stu-id="671c3-374">Property</span></span> |<span data-ttu-id="671c3-375">Wartość</span><span class="sxs-lookup"><span data-stu-id="671c3-375">Value</span></span>  |<span data-ttu-id="671c3-376">Uwagi</span><span class="sxs-lookup"><span data-stu-id="671c3-376">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="671c3-377">Date</span><span class="sxs-lookup"><span data-stu-id="671c3-377">Date</span></span>    | <span data-ttu-id="671c3-378">8/1/2019 12:00:00 AM – 07:00</span><span class="sxs-lookup"><span data-stu-id="671c3-378">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="671c3-379">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="671c3-379">TemperatureCelsius</span></span>| <span data-ttu-id="671c3-380">0</span><span class="sxs-lookup"><span data-stu-id="671c3-380">0</span></span> | <span data-ttu-id="671c3-381">Niezgodność z rozróżnianiem wielkości liter ( `temperatureCelsius` w formacie JSON), więc właściwość nie jest ustawiona.</span><span class="sxs-lookup"><span data-stu-id="671c3-381">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="671c3-382">Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="671c3-382">Summary</span></span> | <span data-ttu-id="671c3-383">Gorąca</span><span class="sxs-lookup"><span data-stu-id="671c3-383">Hot</span></span> ||
| <span data-ttu-id="671c3-384">ExtensionData —</span><span class="sxs-lookup"><span data-stu-id="671c3-384">ExtensionData</span></span> | <span data-ttu-id="671c3-385">temperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="671c3-385">temperatureCelsius: 25</span></span> |<span data-ttu-id="671c3-386">Ponieważ przypadek nie jest zgodny, ta właściwość JSON jest dodatkową i jest parą klucz-wartość w słowniku.</span><span class="sxs-lookup"><span data-stu-id="671c3-386">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="671c3-387">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="671c3-387">DatesAvailable:</span></span><br>  <span data-ttu-id="671c3-388">8/1/2019 12:00:00 AM – 07:00</span><span class="sxs-lookup"><span data-stu-id="671c3-388">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="671c3-389">8/2/2019 12:00:00 AM – 07:00</span><span class="sxs-lookup"><span data-stu-id="671c3-389">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="671c3-390">Dodatkowa Właściwość JSON zmieni się na parę klucz-wartość, z tablicą jako obiektem wartości.</span><span class="sxs-lookup"><span data-stu-id="671c3-390">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="671c3-391">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="671c3-391">SummaryWords:</span></span><br><span data-ttu-id="671c3-392">Chłodna</span><span class="sxs-lookup"><span data-stu-id="671c3-392">Cool</span></span><br><span data-ttu-id="671c3-393">Wiatr</span><span class="sxs-lookup"><span data-stu-id="671c3-393">Windy</span></span><br><span data-ttu-id="671c3-394">Humid</span><span class="sxs-lookup"><span data-stu-id="671c3-394">Humid</span></span> |<span data-ttu-id="671c3-395">Dodatkowa Właściwość JSON zmieni się na parę klucz-wartość, z tablicą jako obiektem wartości.</span><span class="sxs-lookup"><span data-stu-id="671c3-395">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="671c3-396">Gdy obiekt docelowy jest serializowany, pary wartości klucza danych rozszerzenia stają się właściwościami JSON tak samo jak w przychodzących danych JSON:</span><span class="sxs-lookup"><span data-stu-id="671c3-396">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="671c3-397">Zauważ, że `ExtensionData` Nazwa właściwości nie pojawia się w formacie JSON.</span><span class="sxs-lookup"><span data-stu-id="671c3-397">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="671c3-398">Takie zachowanie umożliwia wykonywanie operacji okrężnych przez kod JSON bez utraty jakichkolwiek dodatkowych danych, które w przeciwnym razie nie zostały odszeregowane.</span><span class="sxs-lookup"><span data-stu-id="671c3-398">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="preserve-references-and-handle-circular-references"></a><span data-ttu-id="671c3-399">Zachowaj odwołania i dojścia cykliczne odwołania</span><span class="sxs-lookup"><span data-stu-id="671c3-399">Preserve references and handle circular references</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="671c3-400">Aby zachować odwołania i obsłużyć odwołania cykliczne, ustaw wartość <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.ReferenceHandler%2A> <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceHandler.Preserve%2A> .</span><span class="sxs-lookup"><span data-stu-id="671c3-400">To preserve references and handle circular references, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.ReferenceHandler%2A> to <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceHandler.Preserve%2A>.</span></span> <span data-ttu-id="671c3-401">To ustawienie powoduje następujące zachowanie:</span><span class="sxs-lookup"><span data-stu-id="671c3-401">This setting causes the following behavior:</span></span>

* <span data-ttu-id="671c3-402">Podczas serializacji:</span><span class="sxs-lookup"><span data-stu-id="671c3-402">On serialize:</span></span>

  <span data-ttu-id="671c3-403">Podczas pisania typów złożonych, serializator również zapisuje właściwości metadanych ( `$id` , `$values` i `$ref` ).</span><span class="sxs-lookup"><span data-stu-id="671c3-403">When writing complex types, the serializer also writes metadata properties (`$id`, `$values`, and `$ref`).</span></span>

* <span data-ttu-id="671c3-404">Przy deserializacji:</span><span class="sxs-lookup"><span data-stu-id="671c3-404">On deserialize:</span></span>

  <span data-ttu-id="671c3-405">Oczekiwana jest wartość metadanych (choć nie jest obowiązkowa), a Deserializator próbuje zrozumieć ten element.</span><span class="sxs-lookup"><span data-stu-id="671c3-405">Metadata is expected (although not mandatory), and the deserializer tries to understand it.</span></span>

<span data-ttu-id="671c3-406">Poniższy kod ilustruje użycie tego `Preserve` Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="671c3-406">The following code illustrates use of the `Preserve` setting.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

<span data-ttu-id="671c3-407">Tej funkcji nie można używać do zachowywania typów wartości lub niezmiennych typów.</span><span class="sxs-lookup"><span data-stu-id="671c3-407">This feature can't be used to preserve value types or immutable types.</span></span> <span data-ttu-id="671c3-408">Podczas deserializacji wystąpienie niezmiennego typu jest tworzone po odczytaniu całego ładunku.</span><span class="sxs-lookup"><span data-stu-id="671c3-408">On deserialization, the instance of an immutable type is created after the entire payload is read.</span></span> <span data-ttu-id="671c3-409">W związku z tym może być niemożliwe deserializacja tego samego wystąpienia, jeśli odwołanie do niego pojawia się w ramach ładunku JSON.</span><span class="sxs-lookup"><span data-stu-id="671c3-409">So it would be impossible to deserialize the same instance if a reference to it appears within the JSON payload.</span></span>

<span data-ttu-id="671c3-410">W przypadku typów wartości, niemodyfikowalnych typów i tablic nie są serializowane żadne metadane odwołania.</span><span class="sxs-lookup"><span data-stu-id="671c3-410">For value types, immutable types, and arrays, no reference metadata is serialized.</span></span> <span data-ttu-id="671c3-411">Podczas deserializacji wyjątek jest zgłaszany, jeśli `$ref` lub `$id` zostanie znaleziony.</span><span class="sxs-lookup"><span data-stu-id="671c3-411">On deserialization, an exception is thrown if `$ref` or `$id` is found.</span></span> <span data-ttu-id="671c3-412">Jednak typy wartości ignorują `$id` (i `$values` w przypadku kolekcji), aby umożliwić deserializacji ładunków, które zostały zserializowane przy użyciu :::no-loc(Newtonsoft.Json)::: .</span><span class="sxs-lookup"><span data-stu-id="671c3-412">However, value types ignore `$id` (and `$values` in the case of collections) to make it possible to deserialize payloads that were serialized by using :::no-loc(Newtonsoft.Json):::.</span></span>  <span data-ttu-id="671c3-413">:::no-loc(Newtonsoft.Json)::: wykonuje serializacji metadanych dla takich typów.</span><span class="sxs-lookup"><span data-stu-id="671c3-413">:::no-loc(Newtonsoft.Json)::: does serialize metadata for such types.</span></span>

<span data-ttu-id="671c3-414">Aby określić, czy obiekty są równe, :::no-loc(System.Text.Json)::: używa <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType> , który używa równości odwołań ( <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType> ) zamiast równości wartości ( <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> podczas porównywania dwóch wystąpień obiektów.</span><span class="sxs-lookup"><span data-stu-id="671c3-414">To determine if objects are equal, :::no-loc(System.Text.Json)::: uses <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, which uses reference equality (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) instead of value equality (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> when comparing two object instances.</span></span>

<span data-ttu-id="671c3-415">Aby uzyskać więcej informacji o tym, jak odwołania są serializowane i deserializowane, zobacz <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="671c3-415">For more information about how references are serialized and deserialized, see <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="671c3-416"><xref::::no-loc(System.Text.Json):::.Serialization.ReferenceResolver>Klasa definiuje zachowanie zachowywania odwołań podczas serializacji i deserializacji.</span><span class="sxs-lookup"><span data-stu-id="671c3-416">The <xref::::no-loc(System.Text.Json):::.Serialization.ReferenceResolver> class defines the behavior of preserving references on serialization and deserialization.</span></span> <span data-ttu-id="671c3-417">Utwórz klasę pochodną, aby określić zachowanie niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="671c3-417">Create a derived class to specify custom behavior.</span></span> <span data-ttu-id="671c3-418">Aby zapoznać się z przykładem, zobacz [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span><span class="sxs-lookup"><span data-stu-id="671c3-418">For an example, see [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span></span>

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="671c3-419">:::no-loc(System.Text.Json)::: w programie .NET Core 3,1 obsługuje Serializacja przez wartość i zgłasza wyjątek dla odwołań cyklicznych.</span><span class="sxs-lookup"><span data-stu-id="671c3-419">:::no-loc(System.Text.Json)::: in .NET Core 3.1 only supports serialization by value and throws an exception for circular references.</span></span>
::: zone-end

## <a name="allow-or-write-numbers-in-quotes"></a><span data-ttu-id="671c3-420">Zezwalaj lub zapisuj liczby w cudzysłowach</span><span class="sxs-lookup"><span data-stu-id="671c3-420">Allow or write numbers in quotes</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="671c3-421">Niektóre serializatory kodują liczby jako ciągi JSON (ujęte w cudzysłowy).</span><span class="sxs-lookup"><span data-stu-id="671c3-421">Some serializers encode numbers as JSON strings (surrounded by quotes).</span></span> <span data-ttu-id="671c3-422">Na przykład: `{"DegreesCelsius":"23"}` zamiast `{"DegreesCelsius":23}` .</span><span class="sxs-lookup"><span data-stu-id="671c3-422">For example: `{"DegreesCelsius":"23"}` instead of `{"DegreesCelsius":23}`.</span></span> <span data-ttu-id="671c3-423">Aby serializować liczby w cudzysłowach lub zaakceptować liczby cudzysłowów w całym grafie obiektów wejściowych, ustaw <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-423">To serialize numbers in quotes or accept numbers in quotes across the entire input object graph, set <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-28":::

<span data-ttu-id="671c3-424">W przypadku użycia :::no-loc(System.Text.Json)::: pośrednio za pomocą ASP.NET Core, w przypadku deserializacji są dozwolone liczby ujęte w cudzysłów, ponieważ ASP.NET Core określa [domyślne opcje sieci Web](xref::::no-loc(System.Text.Json):::.JsonSerializerDefaults.Web).</span><span class="sxs-lookup"><span data-stu-id="671c3-424">When you use :::no-loc(System.Text.Json)::: indirectly through ASP.NET Core, quoted numbers are allowed when deserializing because ASP.NET Core specifies [web default options](xref::::no-loc(System.Text.Json):::.JsonSerializerDefaults.Web).</span></span>

<span data-ttu-id="671c3-425">Aby dopuszczać lub zapisywać liczby ujęte w cudzysłów dla określonych właściwości, pól lub typów, Użyj atrybutu [[JsonNumberHandling]](xref::::no-loc(System.Text.Json):::.Serialization.JsonNumberHandlingAttribute) .</span><span class="sxs-lookup"><span data-stu-id="671c3-425">To allow or write quoted numbers for specific properties, fields, or types, use the [[JsonNumberHandling]](xref::::no-loc(System.Text.Json):::.Serialization.JsonNumberHandlingAttribute) attribute.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="671c3-426">:::no-loc(System.Text.Json)::: w programie .NET Core 3,1 nie obsługuje serializacji ani deserializacji numerów ujętych w cudzysłów.</span><span class="sxs-lookup"><span data-stu-id="671c3-426">:::no-loc(System.Text.Json)::: in .NET Core 3.1 doesn't support serializing or deserializing numbers surrounded by quotation marks.</span></span> <span data-ttu-id="671c3-427">Aby uzyskać więcej informacji, zobacz [dopuszczanie lub zapisywanie numerów w cudzysłowach](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span><span class="sxs-lookup"><span data-stu-id="671c3-427">For more information, see [Allow or write numbers in quotes](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span></span>
::: zone-end

## <a name="immutable-types-and-records"></a><span data-ttu-id="671c3-428">Niezmienne typy i rekordy</span><span class="sxs-lookup"><span data-stu-id="671c3-428">Immutable types and Records</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="671c3-429">:::no-loc(System.Text.Json)::: można użyć sparametryzowanego konstruktora, który umożliwia deserializacja niezmiennej klasy lub struktury.</span><span class="sxs-lookup"><span data-stu-id="671c3-429">:::no-loc(System.Text.Json)::: can use a parameterized constructor, which makes it possible to deserialize an immutable class or struct.</span></span> <span data-ttu-id="671c3-430">W przypadku klasy, jeśli jedynym konstruktorem jest sparametryzowane, ten Konstruktor zostanie użyty.</span><span class="sxs-lookup"><span data-stu-id="671c3-430">For a class, if the only constructor is a parameterized one, that constructor will be used.</span></span> <span data-ttu-id="671c3-431">Dla struktury lub klasy z wieloma konstruktorami Określ tę, która ma być używana przez zastosowanie atrybutu [[JsonConstructor]](xref::::no-loc(System.Text.Json):::.Serialization.JsonConstructorAttribute.%23ctor%2A) .</span><span class="sxs-lookup"><span data-stu-id="671c3-431">For a struct, or a class with multiple constructors, specify the one to use by applying the [[JsonConstructor]](xref::::no-loc(System.Text.Json):::.Serialization.JsonConstructorAttribute.%23ctor%2A) attribute.</span></span> <span data-ttu-id="671c3-432">Gdy atrybut nie jest używany, w przypadku obecności jest zawsze używany publiczny Konstruktor bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="671c3-432">When the attribute is not used, a public parameterless constructor is always used if present.</span></span> <span data-ttu-id="671c3-433">Atrybutu można używać tylko z konstruktorami publicznymi.</span><span class="sxs-lookup"><span data-stu-id="671c3-433">The attribute can only be used with public constructors.</span></span> <span data-ttu-id="671c3-434">W poniższym przykładzie zastosowano `[JsonConstructor]` atrybut:</span><span class="sxs-lookup"><span data-stu-id="671c3-434">The following example uses the `[JsonConstructor]` attribute:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

<span data-ttu-id="671c3-435">Rekordy w języku C# 9 są również obsługiwane, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-435">Records in C# 9 are also supported, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

<span data-ttu-id="671c3-436">W przypadku typów, które są niezmienne, ponieważ wszystkie ich metody ustawiające właściwości są niepubliczne, zapoznaj się z następującą sekcją dotyczącą [metod dostępu do właściwości niepublicznych](#non-public-property-accessors).</span><span class="sxs-lookup"><span data-stu-id="671c3-436">For types that are immutable because all their property setters are non-public, see the following section about [non-public property accessors](#non-public-property-accessors).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="671c3-437">`JsonConstructorAttribute` Obsługa rekordów w języku C# 9 nie jest dostępna w programie .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="671c3-437">`JsonConstructorAttribute` and C# 9 Record support aren't available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="non-public-property-accessors"></a><span data-ttu-id="671c3-438">Metody dostępu do właściwości niepublicznych</span><span class="sxs-lookup"><span data-stu-id="671c3-438">Non-public property accessors</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="671c3-439">Aby włączyć użycie niepublicznego dostępu do właściwości, Użyj atrybutu [[JsonInclude]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIncludeAttribute) , jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-439">To enable use of a non-public property accessor, use the [[JsonInclude]](xref::::no-loc(System.Text.Json):::.Serialization.JsonIncludeAttribute) attribute, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="671c3-440">Metody dostępu do właściwości niepublicznych nie są obsługiwane w programie .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="671c3-440">Non-public property accessors are not supported in .NET Core 3.1.</span></span> <span data-ttu-id="671c3-441">Aby uzyskać więcej informacji, zobacz [Migrowanie z :::no-loc(Newtonsoft.Json)::: artykułu](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span><span class="sxs-lookup"><span data-stu-id="671c3-441">For more information, see [the Migrate from :::no-loc(Newtonsoft.Json)::: article](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span></span>
::: zone-end

## <a name="copy-jsonserializeroptions"></a><span data-ttu-id="671c3-442">Kopiuj JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="671c3-442">Copy JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="671c3-443">Istnieje Konstruktor [JsonSerializerOptions] (linki XREF: :::no-loc(System.Text.Json)::: . JsonSerializerOptions .% 23ctor ( :::no-loc(System.Text.Json)::: . JsonSerializerOptions)), która umożliwia utworzenie nowego wystąpienia z takimi samymi opcjami jak istniejące wystąpienie, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-443">There is a [JsonSerializerOptions constructor](xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.%23ctor(:::no-loc(System.Text.Json):::.JsonSerializerOptions)) that lets you create a new instance with the same options as an existing instance, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="671c3-444">`JsonSerializerOptions`Konstruktor, który pobiera istniejące wystąpienie, nie jest dostępny w programie .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="671c3-444">A `JsonSerializerOptions` constructor that takes an existing instance is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a><span data-ttu-id="671c3-445">Ustawienia domyślne sieci Web dla JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="671c3-445">Web defaults for JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="671c3-446">Poniżej przedstawiono opcje, które mają różne wartości domyślne dla usługi Web Apps:</span><span class="sxs-lookup"><span data-stu-id="671c3-446">Here are the options that have different defaults for web apps:</span></span>

* <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy> = <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy.CamelCase>
* <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.NumberHandling%2A> = <xref::::no-loc(System.Text.Json):::.Serialization.JsonNumberHandling.AllowReadingFromString>

<span data-ttu-id="671c3-447">Istnieje Konstruktor [JsonSerializerOptions] (linki XREF: :::no-loc(System.Text.Json)::: . JsonSerializerOptions .% 23ctor ( :::no-loc(System.Text.Json)::: . JsonSerializerDefaults)? View = NET-5,0&Preserve-View = true), która umożliwia utworzenie nowego wystąpienia z opcjami domyślnymi, które ASP.NET Core używane przez aplikacje sieci Web, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-447">There's a [JsonSerializerOptions constructor](xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.%23ctor(:::no-loc(System.Text.Json):::.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) that lets you create a new instance with the default options that ASP.NET Core uses for web apps, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="671c3-448">Poniżej przedstawiono opcje, które mają różne wartości domyślne dla usługi Web Apps:</span><span class="sxs-lookup"><span data-stu-id="671c3-448">Here are the options that have different defaults for web apps:</span></span>

* <xref::::no-loc(System.Text.Json):::.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy> = <xref::::no-loc(System.Text.Json):::.JsonNamingPolicy.CamelCase>

<span data-ttu-id="671c3-449">`JsonSerializerOptions`Konstruktor, który określa zestaw ustawień domyślnych, nie jest dostępny w programie .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="671c3-449">A `JsonSerializerOptions` constructor that specifies a set of defaults is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a><span data-ttu-id="671c3-450">Metody rozszerzenia HttpClient i HttpContent</span><span class="sxs-lookup"><span data-stu-id="671c3-450">HttpClient and HttpContent extension methods</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="671c3-451">Serializowanie i deserializacja ładunków JSON z sieci to typowe operacje.</span><span class="sxs-lookup"><span data-stu-id="671c3-451">Serializing and deserializing JSON payloads from the network are common operations.</span></span> <span data-ttu-id="671c3-452">Metody rozszerzające w [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) i [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) umożliwiają wykonywanie tych operacji w jednym wierszu kodu.</span><span class="sxs-lookup"><span data-stu-id="671c3-452">Extension methods on [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) and [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) let you do these operations in a single line of code.</span></span> <span data-ttu-id="671c3-453">Te metody rozszerzające używają [ustawień domyślnych sieci Web dla JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="671c3-453">These extension methods use [web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>

<span data-ttu-id="671c3-454">Poniższy przykład ilustruje użycie <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> i <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType> :</span><span class="sxs-lookup"><span data-stu-id="671c3-454">The following example illustrates use of <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="23,30":::

<span data-ttu-id="671c3-455">Istnieją również metody rozszerzające dla :::no-loc(System.Text.Json)::: [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span><span class="sxs-lookup"><span data-stu-id="671c3-455">There are also extension methods for :::no-loc(System.Text.Json)::: on [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="671c3-456">Metody rozszerzające w systemach `HttpClient` i `HttpContent` nie są dostępne w :::no-loc(System.Text.Json)::: programie .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="671c3-456">Extension methods on `HttpClient` and `HttpContent` are not available in :::no-loc(System.Text.Json)::: in .NET Core 3.1.</span></span>
::: zone-end

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="671c3-457">Utf8JsonReader, Utf8JsonWriter i JsonDocument</span><span class="sxs-lookup"><span data-stu-id="671c3-457">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="671c3-458"><xref::::no-loc(System.Text.Json):::.Utf8JsonReader?displayProperty=fullName> jest wysoką wydajnością, niskim alokacją, czytnikiem tylko do przodu dla tekstu JSON zakodowanego w formacie UTF-8, Odczytaj z `ReadOnlySpan<byte>` lub `ReadOnlySequence<byte>` .</span><span class="sxs-lookup"><span data-stu-id="671c3-458"><xref::::no-loc(System.Text.Json):::.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="671c3-459">`Utf8JsonReader`Jest typem niskiego poziomu, który może służyć do tworzenia niestandardowych analizatorów i deserializacji.</span><span class="sxs-lookup"><span data-stu-id="671c3-459">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="671c3-460"><xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>Metoda używa `Utf8JsonReader` w obszarze okładki.</span><span class="sxs-lookup"><span data-stu-id="671c3-460">The <xref::::no-loc(System.Text.Json):::.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="671c3-461"><xref::::no-loc(System.Text.Json):::.Utf8JsonWriter?displayProperty=fullName> jest wysoce wydajnym sposobem pisania zakodowanego tekstu JSON w formacie UTF-8 ze wspólnych typów platformy .NET, takich jak `String` , `Int32` , i `DateTime` .</span><span class="sxs-lookup"><span data-stu-id="671c3-461"><xref::::no-loc(System.Text.Json):::.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="671c3-462">Składnik zapisywania jest typu niskiego poziomu, który może służyć do tworzenia serializatorów niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="671c3-462">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="671c3-463"><xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A?displayProperty=nameWithType>Metoda używa `Utf8JsonWriter` w obszarze okładki.</span><span class="sxs-lookup"><span data-stu-id="671c3-463">The <xref::::no-loc(System.Text.Json):::.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="671c3-464"><xref::::no-loc(System.Text.Json):::.JsonDocument?displayProperty=fullName> zapewnia możliwość tworzenia Document Object Model tylko do odczytu (DOM) za pomocą programu `Utf8JsonReader` .</span><span class="sxs-lookup"><span data-stu-id="671c3-464"><xref::::no-loc(System.Text.Json):::.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="671c3-465">DOM zapewnia losowy dostęp do danych w ładunku JSON.</span><span class="sxs-lookup"><span data-stu-id="671c3-465">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="671c3-466">Do elementów JSON, które tworzą ładunek, można uzyskać dostęp za pośrednictwem <xref::::no-loc(System.Text.Json):::.JsonElement> typu.</span><span class="sxs-lookup"><span data-stu-id="671c3-466">The JSON elements that compose the payload can be accessed via the <xref::::no-loc(System.Text.Json):::.JsonElement> type.</span></span> <span data-ttu-id="671c3-467">`JsonElement`Typ udostępnia moduł wyliczający tablic i obiektów oraz interfejsy API służące do konwertowania tekstu JSON na popularne typy .NET.</span><span class="sxs-lookup"><span data-stu-id="671c3-467">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="671c3-468">`JsonDocument` uwidacznia <xref::::no-loc(System.Text.Json):::.JsonDocument.RootElement> Właściwość.</span><span class="sxs-lookup"><span data-stu-id="671c3-468">`JsonDocument` exposes a <xref::::no-loc(System.Text.Json):::.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="671c3-469">W poniższych sekcjach pokazano, jak używać tych narzędzi do odczytywania i pisania danych JSON.</span><span class="sxs-lookup"><span data-stu-id="671c3-469">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="671c3-470">Korzystanie z JsonDocument do uzyskiwania dostępu do danych</span><span class="sxs-lookup"><span data-stu-id="671c3-470">Use JsonDocument for access to data</span></span>

<span data-ttu-id="671c3-471">Poniższy przykład pokazuje, jak używać <xref::::no-loc(System.Text.Json):::.JsonDocument> klasy do losowego dostępu do danych w ciągu JSON:</span><span class="sxs-lookup"><span data-stu-id="671c3-471">The following example shows how to use the <xref::::no-loc(System.Text.Json):::.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="671c3-472">Powyższy kod ma następujące działanie:</span><span class="sxs-lookup"><span data-stu-id="671c3-472">The preceding code:</span></span>

* <span data-ttu-id="671c3-473">Przyjęto, że kod JSON do analizy jest w ciągu o nazwie `jsonString` .</span><span class="sxs-lookup"><span data-stu-id="671c3-473">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="671c3-474">Oblicza średnią ocenę dla obiektów w `Students` tablicy, która ma `Grade` Właściwość.</span><span class="sxs-lookup"><span data-stu-id="671c3-474">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="671c3-475">Przypisuje domyślną ocenę 70 dla studentów, którzy nie posiadają klasy.</span><span class="sxs-lookup"><span data-stu-id="671c3-475">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="671c3-476">Zlicza uczniów przez zwiększenie `count` zmiennej przy każdej iteracji.</span><span class="sxs-lookup"><span data-stu-id="671c3-476">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="671c3-477">Alternatywą jest wywołanie <xref::::no-loc(System.Text.Json):::.JsonElement.GetArrayLength%2A> , jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="671c3-477">An alternative is to call <xref::::no-loc(System.Text.Json):::.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="671c3-478">Oto przykład pliku JSON, który jest przetwarzany przez ten kod:</span><span class="sxs-lookup"><span data-stu-id="671c3-478">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="671c3-479">Użyj JsonDocument, aby zapisać kod JSON</span><span class="sxs-lookup"><span data-stu-id="671c3-479">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="671c3-480">Poniższy przykład pokazuje, jak napisać kod JSON z <xref::::no-loc(System.Text.Json):::.JsonDocument> :</span><span class="sxs-lookup"><span data-stu-id="671c3-480">The following example shows how to write JSON from a <xref::::no-loc(System.Text.Json):::.JsonDocument>:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="671c3-481">Powyższy kod ma następujące działanie:</span><span class="sxs-lookup"><span data-stu-id="671c3-481">The preceding code:</span></span>

* <span data-ttu-id="671c3-482">Odczytuje plik JSON, ładuje dane do `JsonDocument` i zapisuje sformatowany plik JSON w formacie.</span><span class="sxs-lookup"><span data-stu-id="671c3-482">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="671c3-483">Używa <xref::::no-loc(System.Text.Json):::.JsonDocumentOptions> do określenia, czy komentarze w wejściowym formacie JSON są dozwolone, ale ignorowane.</span><span class="sxs-lookup"><span data-stu-id="671c3-483">Uses <xref::::no-loc(System.Text.Json):::.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="671c3-484">Po zakończeniu wywołania <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter.Flush%2A> na składniku zapisywania.</span><span class="sxs-lookup"><span data-stu-id="671c3-484">When finished, calls <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="671c3-485">Alternatywą jest umożliwienie składnika zapisywania AutoFlush, gdy zostanie on usunięty.</span><span class="sxs-lookup"><span data-stu-id="671c3-485">An alternative is to let the writer autoflush when it's disposed.</span></span>

<span data-ttu-id="671c3-486">Oto przykład danych wejściowych JSON do przetworzenia przez przykładowy kod:</span><span class="sxs-lookup"><span data-stu-id="671c3-486">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

<span data-ttu-id="671c3-487">Wynikiem są następujące niedrukowane dane wyjściowe JSON:</span><span class="sxs-lookup"><span data-stu-id="671c3-487">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="671c3-488">Użyj Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="671c3-488">Use Utf8JsonWriter</span></span>

<span data-ttu-id="671c3-489">Poniższy przykład pokazuje, jak używać <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter> klasy:</span><span class="sxs-lookup"><span data-stu-id="671c3-489">The following example shows how to use the <xref::::no-loc(System.Text.Json):::.Utf8JsonWriter> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="671c3-490">Użyj Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="671c3-490">Use Utf8JsonReader</span></span>

<span data-ttu-id="671c3-491">Poniższy przykład pokazuje, jak używać <xref::::no-loc(System.Text.Json):::.Utf8JsonReader> klasy:</span><span class="sxs-lookup"><span data-stu-id="671c3-491">The following example shows how to use the <xref::::no-loc(System.Text.Json):::.Utf8JsonReader> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="671c3-492">Poprzedni kod założono, że `jsonUtf8` zmienna jest tablicą bajtową, która zawiera prawidłowy kod JSON zakodowany jako UTF-8.</span><span class="sxs-lookup"><span data-stu-id="671c3-492">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="671c3-493">Filtrowanie danych za pomocą Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="671c3-493">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="671c3-494">Poniższy przykład pokazuje, jak odczytywać plik synchronicznie i wyszukiwać wartość:</span><span class="sxs-lookup"><span data-stu-id="671c3-494">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="671c3-495">Powyższy kod ma następujące działanie:</span><span class="sxs-lookup"><span data-stu-id="671c3-495">The preceding code:</span></span>

* <span data-ttu-id="671c3-496">Przyjęto, że kod JSON zawiera tablicę obiektów, a każdy obiekt może zawierać właściwość "name" typu String.</span><span class="sxs-lookup"><span data-stu-id="671c3-496">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="671c3-497">Zlicza obiekty i wartości właściwości "name", które kończą się znakiem "University".</span><span class="sxs-lookup"><span data-stu-id="671c3-497">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="671c3-498">Przyjęto założenie, że plik jest zakodowany jako UTF-16 i transkoduje go do UTF-8.</span><span class="sxs-lookup"><span data-stu-id="671c3-498">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="671c3-499">Plik zakodowany jako UTF-8 może być odczytywany bezpośrednio do programu `ReadOnlySpan<byte>` , przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="671c3-499">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="671c3-500">Jeśli plik zawiera znacznik kolejności bajtów UTF-8, usuń go przed przekazaniem bajtów do `Utf8JsonReader` , ponieważ czytnik oczekuje tekstu.</span><span class="sxs-lookup"><span data-stu-id="671c3-500">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="671c3-501">W przeciwnym razie BOM jest traktowany jako nieprawidłowy kod JSON, a czytelnik zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="671c3-501">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="671c3-502">Oto przykład JSON, który może odczytać poprzedzający kod.</span><span class="sxs-lookup"><span data-stu-id="671c3-502">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="671c3-503">Otrzymany komunikat podsumowujący to "2 z 4 mają nazwy kończące się na" University ":</span><span class="sxs-lookup"><span data-stu-id="671c3-503">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a><span data-ttu-id="671c3-504">Odczytaj ze strumienia przy użyciu Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="671c3-504">Read from a stream using Utf8JsonReader</span></span>

<span data-ttu-id="671c3-505">W przypadku odczytywania dużego pliku (na przykład gigabajta lub więcej) można uniknąć konieczności załadowania całego pliku do pamięci jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="671c3-505">When reading a large file (a gigabyte or more in size, for example), you might want to avoid having to load the entire file into memory at once.</span></span> <span data-ttu-id="671c3-506">W tym scenariuszu można użyć <xref:System.IO.FileStream> .</span><span class="sxs-lookup"><span data-stu-id="671c3-506">For this scenario, you can use a <xref:System.IO.FileStream>.</span></span>

<span data-ttu-id="671c3-507">W przypadku `Utf8JsonReader` odczytywania ze strumienia przy użyciu programu, obowiązują następujące reguły:</span><span class="sxs-lookup"><span data-stu-id="671c3-507">When using the `Utf8JsonReader` to read from a stream, the following rules apply:</span></span>

* <span data-ttu-id="671c3-508">Bufor zawierający częściowy ładunek JSON musi być co najmniej tak duży jak największy token JSON w nim, tak aby czytelnik mógł postępować dalej.</span><span class="sxs-lookup"><span data-stu-id="671c3-508">The buffer containing the partial JSON payload must be at least as large as the largest JSON token within it so that the reader can make forward progress.</span></span>
* <span data-ttu-id="671c3-509">Bufor musi być co najmniej tak duże, jak największą sekwencję białych znaków w formacie JSON.</span><span class="sxs-lookup"><span data-stu-id="671c3-509">The buffer must be at least as large as the largest sequence of white space within the JSON.</span></span>
* <span data-ttu-id="671c3-510">Czytnik nie śledzi danych, które zostały odczytane, dopóki nie zostaną całkowicie odczytane dalej <xref::::no-loc(System.Text.Json):::.Utf8JsonReader.TokenType%2A> w ładunku JSON.</span><span class="sxs-lookup"><span data-stu-id="671c3-510">The reader doesn't keep track of the data it has read until it completely reads the next <xref::::no-loc(System.Text.Json):::.Utf8JsonReader.TokenType%2A> in the JSON payload.</span></span> <span data-ttu-id="671c3-511">Tak więc, gdy bajty są pozostawione w buforze, należy ponownie przekazać je do czytnika.</span><span class="sxs-lookup"><span data-stu-id="671c3-511">So when there are bytes left over in the buffer, you have to pass them to the reader again.</span></span> <span data-ttu-id="671c3-512">Możesz użyć, <xref::::no-loc(System.Text.Json):::.Utf8JsonReader.BytesConsumed%2A> Aby określić, ile bajtów pozostało.</span><span class="sxs-lookup"><span data-stu-id="671c3-512">You can use <xref::::no-loc(System.Text.Json):::.Utf8JsonReader.BytesConsumed%2A> to determine how many bytes are left over.</span></span>

<span data-ttu-id="671c3-513">Poniższy kod ilustruje sposób odczytywania ze strumienia.</span><span class="sxs-lookup"><span data-stu-id="671c3-513">The following code illustrates how to read from a stream.</span></span> <span data-ttu-id="671c3-514">Przykład pokazuje <xref:System.IO.MemoryStream> .</span><span class="sxs-lookup"><span data-stu-id="671c3-514">The example shows a <xref:System.IO.MemoryStream>.</span></span> <span data-ttu-id="671c3-515">Podobny kod będzie działał z <xref:System.IO.FileStream> , z wyjątkiem sytuacji, gdy `FileStream` zawiera BOM w formacie UTF-8.</span><span class="sxs-lookup"><span data-stu-id="671c3-515">Similar code will work with a <xref:System.IO.FileStream>, except when the `FileStream` contains a UTF-8 BOM at the start.</span></span> <span data-ttu-id="671c3-516">W takim przypadku należy rozdzielić te trzy bajty z buforu przed przekazaniem pozostałych bajtów do `Utf8JsonReader` .</span><span class="sxs-lookup"><span data-stu-id="671c3-516">In that case, you need to strip those three bytes from the buffer before passing the remaining bytes to the `Utf8JsonReader`.</span></span> <span data-ttu-id="671c3-517">W przeciwnym razie czytelnik zgłosi wyjątek, ponieważ BOM nie jest traktowany jako prawidłowa część JSON.</span><span class="sxs-lookup"><span data-stu-id="671c3-517">Otherwise the reader would throw an exception, since the BOM is not considered a valid part of the JSON.</span></span>

<span data-ttu-id="671c3-518">Przykładowy kod rozpoczyna się od buforu 4 KB i podwaja rozmiar buforu za każdym razem, gdy okaże się, że rozmiar nie jest wystarczająco duży, aby dopasować pełny token JSON, który jest wymagany, aby czytnik mógł postępować w ładunku JSON.</span><span class="sxs-lookup"><span data-stu-id="671c3-518">The sample code starts with a 4KB buffer and doubles the buffer size each time it finds that the size is not large enough to fit a complete JSON token, which is required for the reader to make forward progress on the JSON payload.</span></span> <span data-ttu-id="671c3-519">Przykład JSON podany w fragmencie kodu wyzwala zwiększenie rozmiaru buforu tylko wtedy, gdy ustawisz bardzo mały początkowy rozmiar buforu, na przykład 10 bajtów.</span><span class="sxs-lookup"><span data-stu-id="671c3-519">The JSON sample provided in the snippet triggers a buffer size increase only if you set a very small initial buffer size, for example, 10 bytes.</span></span> <span data-ttu-id="671c3-520">Jeśli ustawisz początkowy rozmiar buforu na 10, `Console.WriteLine` instrukcje ilustrują przyczynę i wpływ rozmiaru buforu.</span><span class="sxs-lookup"><span data-stu-id="671c3-520">If you set the initial buffer size to 10, the `Console.WriteLine` statements illustrate the cause and effect of buffer size increases.</span></span> <span data-ttu-id="671c3-521">W początkowym rozmiarze bufora 4 KB cały przykładowy kod JSON jest pokazywany przez każdy z nich `Console.WriteLine` , a rozmiar buforu nigdy nie musi zostać zwiększony.</span><span class="sxs-lookup"><span data-stu-id="671c3-521">At the 4KB initial buffer size, the entire sample JSON is shown by each `Console.WriteLine`, and the buffer size never has to be increased.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

<span data-ttu-id="671c3-522">W powyższym przykładzie nie ustawiono limitu rozmiaru buforu.</span><span class="sxs-lookup"><span data-stu-id="671c3-522">The preceding example sets no limit to how large the buffer can grow.</span></span> <span data-ttu-id="671c3-523">Jeśli rozmiar tokenu jest zbyt duży, kod może zakończyć się niepowodzeniem z <xref:System.OutOfMemoryException> wyjątkiem.</span><span class="sxs-lookup"><span data-stu-id="671c3-523">If the token size is too large, the code could fail with an <xref:System.OutOfMemoryException> exception.</span></span> <span data-ttu-id="671c3-524">Taka sytuacja może wystąpić, jeśli kod JSON zawiera token o rozmiarze około 1 GB lub więcej, ponieważ Podwajanie rozmiaru 1 GB spowoduje, że rozmiar jest zbyt duży, aby zmieścił się w `int32` buforze.</span><span class="sxs-lookup"><span data-stu-id="671c3-524">This can happen if the JSON contains a token that is around 1 GB or more in size, because doubling the 1 GB size results in a size that is too large to fit into an `int32` buffer.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="671c3-525">Zasoby dodatkowe</span><span class="sxs-lookup"><span data-stu-id="671c3-525">Additional resources</span></span>

* [<span data-ttu-id="671c3-526">:::no-loc(System.Text.Json)::: Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="671c3-526">:::no-loc(System.Text.Json)::: overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="671c3-527">Jak pisać konwertery niestandardowe</span><span class="sxs-lookup"><span data-stu-id="671c3-527">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="671c3-528">Jak przeprowadzić migrację z :::no-loc(Newtonsoft.Json):::</span><span class="sxs-lookup"><span data-stu-id="671c3-528">How to migrate from :::no-loc(Newtonsoft.Json):::</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="671c3-529">Obsługa DateTime i DateTimeOffset w :::no-loc(System.Text.Json):::</span><span class="sxs-lookup"><span data-stu-id="671c3-529">DateTime and DateTimeOffset support in :::no-loc(System.Text.Json):::</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="671c3-530">[:::no-loc(System.Text.Json)::: Dokumentacja interfejsu API](xref::::no-loc(System.Text.Json):::)</span><span class="sxs-lookup"><span data-stu-id="671c3-530">[:::no-loc(System.Text.Json)::: API reference](xref::::no-loc(System.Text.Json):::)</span></span>
<!-- * [:::no-loc(System.Text.Json)::: roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/:::no-loc(System.Text.Json):::/roadmap/README.md)-->
