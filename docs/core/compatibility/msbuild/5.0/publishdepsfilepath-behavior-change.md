---
title: 'Istotna zmiana: PublishDepsFilePath zmiana zachowania'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, w której właściwość MSBuild PublishDepsFilePath jest pusta dla aplikacji jednoplikowych.
ms.date: 09/17/2020
ms.openlocfilehash: 70631beff31aa3388e59f3b79875ef437351451a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761734"
---
# <a name="publishdepsfilepath-behavior-change"></a><span data-ttu-id="ea996-103">PublishDepsFilePath zmiana zachowania</span><span class="sxs-lookup"><span data-stu-id="ea996-103">PublishDepsFilePath behavior change</span></span>

<span data-ttu-id="ea996-104">`PublishDepsFilePath`Właściwość programu MSBuild jest pusta dla aplikacji jednoplikowych.</span><span class="sxs-lookup"><span data-stu-id="ea996-104">The `PublishDepsFilePath` MSBuild property is empty for single-file applications.</span></span> <span data-ttu-id="ea996-105">Ponadto w przypadku aplikacji innych niż Jednoplikowe *deps.jsw* pliku nie mogą być kopiowane do katalogu wyjściowego do późniejszej kompilacji.</span><span class="sxs-lookup"><span data-stu-id="ea996-105">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory until later in the build.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ea996-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="ea996-106">Version introduced</span></span>

<span data-ttu-id="ea996-107">5,0</span><span class="sxs-lookup"><span data-stu-id="ea996-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="ea996-108">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="ea996-108">Change description</span></span>

<span data-ttu-id="ea996-109">W poprzednich wersjach programu .NET `PublishDepsFilePath` Właściwość programu MSBuild jest ścieżką do *deps.jsaplikacji w* pliku w katalogu wyjściowym dla aplikacji nienależących do jednego pliku i ścieżka w katalogu pośrednim dla aplikacji jednoplikowych.</span><span class="sxs-lookup"><span data-stu-id="ea996-109">In previous .NET versions, the `PublishDepsFilePath` MSBuild property is the path to the app's *deps.json* file in the output directory for non single-file applications, and a path in the intermediate directory for single-file apps.</span></span>

<span data-ttu-id="ea996-110">Począwszy od platformy .NET 5,0, `PublishDepsFilePath` jest pusty dla aplikacji jednoplikowych, a nowa `IntermediateDepsFilePath` właściwość określa *deps.jsw* lokalizacji w katalogu pośrednim.</span><span class="sxs-lookup"><span data-stu-id="ea996-110">Starting in .NET 5.0, `PublishDepsFilePath` is empty for single-file applications and a new `IntermediateDepsFilePath` property specifies the *deps.json* location in the intermediate directory.</span></span> <span data-ttu-id="ea996-111">Ponadto w przypadku aplikacji innych niż Jednoplikowe *deps.jsw* pliku nie można skopiować do katalogu wyjściowego (czyli ścieżki określonej przez `PublishDepsFilePath` ) do późniejszej kompilacji.</span><span class="sxs-lookup"><span data-stu-id="ea996-111">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory (that is, the path specified by `PublishDepsFilePath`) until later in the build.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ea996-112">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="ea996-112">Reason for change</span></span>

<span data-ttu-id="ea996-113">Ta zmiana została wprowadzona z kilku powodów:</span><span class="sxs-lookup"><span data-stu-id="ea996-113">This change was made for a couple of reasons:</span></span>

- <span data-ttu-id="ea996-114">Ze względu na refaktoryzację logiki publikowania w celu obsługi [ulepszonych aplikacji jednoplikowych](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) w programie .NET 5.</span><span class="sxs-lookup"><span data-stu-id="ea996-114">Due to a refactoring of the publish logic in order to support [improved single-file apps](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) in .NET 5.</span></span>

- <span data-ttu-id="ea996-115">W aplikacjach jednoplikowych, aby pomóc w ochronie przed obiektami docelowymi, które próbują ponownie zapisać *deps.jsna* pliku po powiązaniu *deps.jsna, w* ten sposób dyskretnie nie wpływa na aplikację.</span><span class="sxs-lookup"><span data-stu-id="ea996-115">In single-file apps, to help guard against targets that try to rewrite the *deps.json* file after *deps.json* has already been bundled, thus silently not affecting the app.</span></span> <span data-ttu-id="ea996-116">Z tego powodu `PublishDepsFilePath` jest puste dla aplikacji jednoplikowych.</span><span class="sxs-lookup"><span data-stu-id="ea996-116">For this reason, `PublishDepsFilePath` is empty for single-file applications.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ea996-117">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="ea996-117">Recommended action</span></span>

<span data-ttu-id="ea996-118">Cele, które ponownie zapisują *deps.jsw* pliku, powinny zasadniczo używać `IntermediateDepsFilePath` właściwości.</span><span class="sxs-lookup"><span data-stu-id="ea996-118">Targets that rewrite the *deps.json* file should generally do so using the `IntermediateDepsFilePath` property.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ea996-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="ea996-119">Affected APIs</span></span>

<span data-ttu-id="ea996-120">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="ea996-120">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
