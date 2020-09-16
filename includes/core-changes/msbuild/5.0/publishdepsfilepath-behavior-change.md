---
ms.openlocfilehash: 077eadb05ab16f5cec8817b89bc771de0c94aefa
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679333"
---
### <a name="publishdepsfilepath-behavior-change"></a><span data-ttu-id="f1269-101">PublishDepsFilePath zmiana zachowania</span><span class="sxs-lookup"><span data-stu-id="f1269-101">PublishDepsFilePath behavior change</span></span>

<span data-ttu-id="f1269-102">`PublishDepsFilePath`Właściwość programu MSBuild jest pusta dla aplikacji jednoplikowych.</span><span class="sxs-lookup"><span data-stu-id="f1269-102">The `PublishDepsFilePath` MSBuild property is empty for single-file applications.</span></span> <span data-ttu-id="f1269-103">Ponadto w przypadku aplikacji innych niż Jednoplikowe *deps.jsw* pliku nie mogą być kopiowane do katalogu wyjściowego do późniejszej kompilacji.</span><span class="sxs-lookup"><span data-stu-id="f1269-103">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory until later in the build.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f1269-104">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="f1269-104">Version introduced</span></span>

<span data-ttu-id="f1269-105">5,0</span><span class="sxs-lookup"><span data-stu-id="f1269-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="f1269-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="f1269-106">Change description</span></span>

<span data-ttu-id="f1269-107">W poprzednich wersjach programu .NET `PublishDepsFilePath` Właściwość programu MSBuild jest ścieżką do *deps.jsaplikacji w* pliku w katalogu wyjściowym dla aplikacji nienależących do jednego pliku i ścieżka w katalogu pośrednim dla aplikacji jednoplikowych.</span><span class="sxs-lookup"><span data-stu-id="f1269-107">In previous .NET versions, the `PublishDepsFilePath` MSBuild property is the path to the app's *deps.json* file in the output directory for non single-file applications, and a path in the intermediate directory for single-file apps.</span></span>

<span data-ttu-id="f1269-108">Począwszy od platformy .NET 5,0, `PublishDepsFilePath` jest pusty dla aplikacji jednoplikowych, a nowa `IntermediateDepsFilePath` właściwość określa *deps.jsw* lokalizacji w katalogu pośrednim.</span><span class="sxs-lookup"><span data-stu-id="f1269-108">Starting in .NET 5.0, `PublishDepsFilePath` is empty for single-file applications and a new `IntermediateDepsFilePath` property specifies the *deps.json* location in the intermediate directory.</span></span> <span data-ttu-id="f1269-109">Ponadto w przypadku aplikacji innych niż Jednoplikowe *deps.jsw* pliku nie można skopiować do katalogu wyjściowego (czyli ścieżki określonej przez `PublishDepsFilePath` ) do późniejszej kompilacji.</span><span class="sxs-lookup"><span data-stu-id="f1269-109">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory (that is, the path specified by `PublishDepsFilePath`) until later in the build.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f1269-110">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="f1269-110">Reason for change</span></span>

<span data-ttu-id="f1269-111">Ta zmiana została wprowadzona z kilku powodów:</span><span class="sxs-lookup"><span data-stu-id="f1269-111">This change was made for a couple of reasons:</span></span>

- <span data-ttu-id="f1269-112">Ze względu na refaktoryzację logiki publikowania w celu obsługi [ulepszonych aplikacji jednoplikowych](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) w programie .NET 5.</span><span class="sxs-lookup"><span data-stu-id="f1269-112">Due to a refactoring of the publish logic in order to support [improved single-file apps](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) in .NET 5.</span></span>

- <span data-ttu-id="f1269-113">W aplikacjach jednoplikowych, aby pomóc w ochronie przed obiektami docelowymi, które próbują ponownie zapisać *deps.jsna* pliku po powiązaniu *deps.jsna, w* ten sposób dyskretnie nie wpływa na aplikację.</span><span class="sxs-lookup"><span data-stu-id="f1269-113">In single-file apps, to help guard against targets that try to rewrite the *deps.json* file after *deps.json* has already been bundled, thus silently not affecting the app.</span></span> <span data-ttu-id="f1269-114">Z tego powodu `PublishDepsFilePath` jest puste dla aplikacji jednoplikowych.</span><span class="sxs-lookup"><span data-stu-id="f1269-114">For this reason, `PublishDepsFilePath` is empty for single-file applications.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f1269-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="f1269-115">Recommended action</span></span>

<span data-ttu-id="f1269-116">Cele, które ponownie zapisują *deps.jsw* pliku, powinny zasadniczo używać `IntermediateDepsFilePath` właściwości.</span><span class="sxs-lookup"><span data-stu-id="f1269-116">Targets that rewrite the *deps.json* file should generally do so using the `IntermediateDepsFilePath` property.</span></span>

#### <a name="category"></a><span data-ttu-id="f1269-117">Kategoria</span><span class="sxs-lookup"><span data-stu-id="f1269-117">Category</span></span>

<span data-ttu-id="f1269-118">MSBuild</span><span class="sxs-lookup"><span data-stu-id="f1269-118">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f1269-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="f1269-119">Affected APIs</span></span>

<span data-ttu-id="f1269-120">Brak</span><span class="sxs-lookup"><span data-stu-id="f1269-120">N/A</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
