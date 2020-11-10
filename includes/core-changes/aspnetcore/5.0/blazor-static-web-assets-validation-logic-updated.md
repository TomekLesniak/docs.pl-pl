---
ms.openlocfilehash: c090e99cd0569a843a4c505ad11b8da5740213e8
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440482"
---
### <a name="blazor-updated-validation-logic-for-static-web-assets"></a><span data-ttu-id="379a9-101">Blazor: Zaktualizowano logikę walidacji dla statycznych zasobów sieci Web</span><span class="sxs-lookup"><span data-stu-id="379a9-101">Blazor: Updated validation logic for static web assets</span></span>

<span data-ttu-id="379a9-102">Wystąpił problem podczas weryfikacji konfliktu dla statycznych zasobów sieci Web w ASP.NET Core 3,1 i Blazor webassembly 3,2.</span><span class="sxs-lookup"><span data-stu-id="379a9-102">There was an issue in conflict validation for static web assets in ASP.NET Core 3.1 and Blazor WebAssembly 3.2.</span></span> <span data-ttu-id="379a9-103">Problem:</span><span class="sxs-lookup"><span data-stu-id="379a9-103">The issue:</span></span>

* <span data-ttu-id="379a9-104">Uniemożliwiło prawidłowe wykrywanie konfliktów między zasobami i zasobami hosta z bibliotek klas Razor (RCLs) i Blazor aplikacji webassembly.</span><span class="sxs-lookup"><span data-stu-id="379a9-104">Prevented proper conflict detection between the host assets and assets from Razor Class Libraries (RCLs) and Blazor WebAssembly apps.</span></span>
* <span data-ttu-id="379a9-105">W większości ma wpływ na aplikacje Blazor webassembly, ponieważ domyślnie statyczne zasoby sieci Web w RCLs są obsługiwane pod `_content/$(PackageId)` prefiksem.</span><span class="sxs-lookup"><span data-stu-id="379a9-105">Mostly affects Blazor WebAssembly apps, since by default, static web assets in RCLs are served under the `_content/$(PackageId)` prefix.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="379a9-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="379a9-106">Version introduced</span></span>

<span data-ttu-id="379a9-107">5,0</span><span class="sxs-lookup"><span data-stu-id="379a9-107">5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="379a9-108">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="379a9-108">Old behavior</span></span>

<span data-ttu-id="379a9-109">Podczas opracowywania RCL statyczne zasoby sieci Web mogą zostać zastąpione w trybie dyskretnym zasobami projektu hosta na tym samym ścieżka hosta.</span><span class="sxs-lookup"><span data-stu-id="379a9-109">During development, an RCL's static web assets could be silently overridden with host project assets on the same host path.</span></span> <span data-ttu-id="379a9-110">Rozważmy RCL, który definiuje statyczny element zawartości sieci Web, który ma być obsługiwany w */folder/file.txt*.</span><span class="sxs-lookup"><span data-stu-id="379a9-110">Consider an RCL that has defined a static web asset to be served at */folder/file.txt*.</span></span> <span data-ttu-id="379a9-111">Jeśli host umieścił plik w *katalogu wwwroot/folder/file.txt* , plik na serwerze dyskretnie overrode plik w aplikacji RCL lub Blazor webassembly.</span><span class="sxs-lookup"><span data-stu-id="379a9-111">If the host placed a file at *wwwroot/folder/file.txt* , the file on the server silently overrode the file on the RCL or Blazor WebAssembly app.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="379a9-112">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="379a9-112">New behavior</span></span>

<span data-ttu-id="379a9-113">ASP.NET Core prawidłowo wykrywane, gdy ten problem wystąpi.</span><span class="sxs-lookup"><span data-stu-id="379a9-113">ASP.NET Core correctly detects when this issue happens.</span></span> <span data-ttu-id="379a9-114">Informuje użytkownika o konflikcie, dzięki czemu można wykonać odpowiednie działania.</span><span class="sxs-lookup"><span data-stu-id="379a9-114">It informs you, the user, of the conflict so that you can take the appropriate action.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="379a9-115">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="379a9-115">Reason for change</span></span>

<span data-ttu-id="379a9-116">Statyczne zasoby sieci Web nie były zamierzone dla plików na hoście *wwwroot* projektu.</span><span class="sxs-lookup"><span data-stu-id="379a9-116">Static web assets weren't intended to be overridable by files on the *wwwroot* host of the project.</span></span> <span data-ttu-id="379a9-117">Umożliwienie przesłania tych plików może prowadzić do błędów, które są trudne do zdiagnozowania.</span><span class="sxs-lookup"><span data-stu-id="379a9-117">Allowing for the overriding of those files could lead to errors that are difficult to diagnose.</span></span> <span data-ttu-id="379a9-118">Wynikiem mogą być niezdefiniowane zmiany zachowania w opublikowanych aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="379a9-118">The result could be undefined behavior changes in published apps.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="379a9-119">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="379a9-119">Recommended action</span></span>

<span data-ttu-id="379a9-120">Domyślnie nie ma powodów, dla których plik RCL powoduje konflikt z plikiem na hoście.</span><span class="sxs-lookup"><span data-stu-id="379a9-120">By default, there's no reason for an RCL file to conflict with a file on the host.</span></span> <span data-ttu-id="379a9-121">Pliki RCL są poprzedzone prefiksem `_content/${PackageId}` .</span><span class="sxs-lookup"><span data-stu-id="379a9-121">RCL files are prefixed with `_content/${PackageId}`.</span></span> <span data-ttu-id="379a9-122">Pliki zestawu webassembly Blazor są umieszczane w katalogu głównym przestrzeni adresów URL hosta, co ułatwia konflikty.</span><span class="sxs-lookup"><span data-stu-id="379a9-122">Blazor WebAssembly files are placed at the root of the host URL space, which makes conflicts easier.</span></span> <span data-ttu-id="379a9-123">Na przykład aplikacje webassembly Blazor zawierają plik *favicon. ico* , który host może również znajdować się w folderze *wwwroot* .</span><span class="sxs-lookup"><span data-stu-id="379a9-123">For example, Blazor WebAssembly apps contain a *favicon.ico* file that the host might also include in its *wwwroot* folder.</span></span>

<span data-ttu-id="379a9-124">Jeśli źródłem konfliktu jest plik RCL, często oznacza to, że kod kopiuje zasoby z biblioteki do folderu *wwwroot* projektu.</span><span class="sxs-lookup"><span data-stu-id="379a9-124">If the conflict's source is an RCL file, it often means code is copying assets from the library into the project's *wwwroot* folder.</span></span> <span data-ttu-id="379a9-125">Pisanie kodu w celu skopiowania plików obniża podstawowe cele statycznych zasobów internetowych.</span><span class="sxs-lookup"><span data-stu-id="379a9-125">Writing code to copy files defeats a primary goal of static web assets.</span></span> <span data-ttu-id="379a9-126">Ten cel ma na celu uzyskanie aktualizacji w przeglądarce, gdy zawartość jest aktualizowana bez konieczności wyzwalania nowej kompilacji.</span><span class="sxs-lookup"><span data-stu-id="379a9-126">This goal is fundamental to get updates on the browser when the contents are updated without having to trigger a new compilation.</span></span>

<span data-ttu-id="379a9-127">Możesz zachować takie zachowanie i zachować plik na hoście.</span><span class="sxs-lookup"><span data-stu-id="379a9-127">You may choose to preserve this behavior and maintain the file on the host.</span></span> <span data-ttu-id="379a9-128">Aby to zrobić, usuń plik z listy statycznych zasobów internetowych z niestandardowym elementem docelowym programu MSBuild.</span><span class="sxs-lookup"><span data-stu-id="379a9-128">To do so, remove the file from the list of static web assets with a custom MSBuild target.</span></span>

<span data-ttu-id="379a9-129">Aby użyć pliku RCL lub pliku aplikacji webassembly Blazor zamiast pliku projektu hosta, usuń plik z projektu hosta.</span><span class="sxs-lookup"><span data-stu-id="379a9-129">To use the RCL's file or the Blazor WebAssembly app's file instead of the host project's file, remove the file from the host project.</span></span>

#### <a name="category"></a><span data-ttu-id="379a9-130">Kategoria</span><span class="sxs-lookup"><span data-stu-id="379a9-130">Category</span></span>

<span data-ttu-id="379a9-131">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="379a9-131">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="379a9-132">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="379a9-132">Affected APIs</span></span>

<span data-ttu-id="379a9-133">Brak</span><span class="sxs-lookup"><span data-stu-id="379a9-133">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
