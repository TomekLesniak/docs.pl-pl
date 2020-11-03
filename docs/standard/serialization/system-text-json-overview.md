---
title: Serializowanie i deserializacja JSON przy użyciu języka C# — .NET
description: 'To omówienie zawiera opis :::no-loc(System.Text.Json)::: funkcji przestrzeni nazw do serializacji do i deserializacji z JSON w programie .NET.'
ms.date: 01/10/2020
no-loc:
- ':::no-loc(System.Text.Json):::'
- ':::no-loc(Newtonsoft.Json):::'
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: d8bd5bcf78db534bd722972db01253cbd13a7a06
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282407"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="41cd9-103">Serializacja i deserializacja kodu JSON (kierowanie i cofanie) w programie .NET — Omówienie</span><span class="sxs-lookup"><span data-stu-id="41cd9-103">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="41cd9-104">`:::no-loc(System.Text.Json):::`Przestrzeń nazw zawiera funkcje serializacji do i deserializacji z JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="41cd9-104">The `:::no-loc(System.Text.Json):::` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="41cd9-105">Projekt biblioteki wyróżnia wysoką wydajność i małą alokację pamięci w ramach rozbudowanego zestawu funkcji.</span><span class="sxs-lookup"><span data-stu-id="41cd9-105">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="41cd9-106">Wbudowana obsługa UTF-8 optymalizuje proces odczytywania i pisania tekstu JSON zakodowanego w formacie UTF-8, który jest najbardziej rozpowszechnionym kodowaniem danych w sieci Web i plikach na dysku.</span><span class="sxs-lookup"><span data-stu-id="41cd9-106">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="41cd9-107">Biblioteka zawiera również klasy umożliwiające pracę z modelem DOM (Document objecting) w pamięci.</span><span class="sxs-lookup"><span data-stu-id="41cd9-107">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="41cd9-108">Ta funkcja włącza losowy dostęp tylko do odczytu do elementów w pliku JSON lub ciągu.</span><span class="sxs-lookup"><span data-stu-id="41cd9-108">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="41cd9-109">Jak uzyskać bibliotekę</span><span class="sxs-lookup"><span data-stu-id="41cd9-109">How to get the library</span></span>

* <span data-ttu-id="41cd9-110">Biblioteka jest wbudowana w ramach współdzielonej struktury dla platformy .NET Core 3,0 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="41cd9-110">The library is built-in as part of the shared framework for .NET Core 3.0 and later versions.</span></span>
* <span data-ttu-id="41cd9-111">W przypadku wcześniejszych wersji platformy zainstaluj [:::no-loc(System.Text.Json):::](https://www.nuget.org/packages/:::no-loc(System.Text.Json):::) pakiet NuGet.</span><span class="sxs-lookup"><span data-stu-id="41cd9-111">For earlier framework versions, install the [:::no-loc(System.Text.Json):::](https://www.nuget.org/packages/:::no-loc(System.Text.Json):::) NuGet package.</span></span> <span data-ttu-id="41cd9-112">Pakiet obsługuje:</span><span class="sxs-lookup"><span data-stu-id="41cd9-112">The package supports:</span></span>

  * <span data-ttu-id="41cd9-113">.NET Standard 2,0 i nowsze wersje</span><span class="sxs-lookup"><span data-stu-id="41cd9-113">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="41cd9-114">.NET Framework 4.7.2 i nowsze wersje</span><span class="sxs-lookup"><span data-stu-id="41cd9-114">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="41cd9-115">.NET Core 2,0, 2,1 i 2,2</span><span class="sxs-lookup"><span data-stu-id="41cd9-115">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="41cd9-116">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="41cd9-116">Additional resources</span></span>

* [<span data-ttu-id="41cd9-117">Jak używać biblioteki</span><span class="sxs-lookup"><span data-stu-id="41cd9-117">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="41cd9-118">Jak przeprowadzić migrację z :::no-loc(Newtonsoft.Json):::</span><span class="sxs-lookup"><span data-stu-id="41cd9-118">How to migrate from :::no-loc(Newtonsoft.Json):::</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="41cd9-119">Jak pisać konwertery</span><span class="sxs-lookup"><span data-stu-id="41cd9-119">How to write converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="41cd9-120">[:::no-loc(System.Text.Json)::: kod źródłowy](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/:::no-loc(System.Text.Json):::)</span><span class="sxs-lookup"><span data-stu-id="41cd9-120">[:::no-loc(System.Text.Json)::: source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/:::no-loc(System.Text.Json):::)</span></span>
* <span data-ttu-id="41cd9-121">[:::no-loc(System.Text.Json)::: Dokumentacja interfejsu API](xref::::no-loc(System.Text.Json):::)</span><span class="sxs-lookup"><span data-stu-id="41cd9-121">[:::no-loc(System.Text.Json)::: API reference](xref::::no-loc(System.Text.Json):::)</span></span>
* <span data-ttu-id="41cd9-122">[:::no-loc(System.Text.Json):::. Dokumentacja interfejsu API serializacji](xref::::no-loc(System.Text.Json):::.Serialization)</span><span class="sxs-lookup"><span data-stu-id="41cd9-122">[:::no-loc(System.Text.Json):::.Serialization API reference](xref::::no-loc(System.Text.Json):::.Serialization)</span></span>
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/:::no-loc(System.Text.Json):::/roadmap/README.md)-->
