---
ms.openlocfilehash: 54bee14f6de409550357194e905b6ee5d8ef8f18
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679005"
---
### <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a><span data-ttu-id="1a7b0-101">OutputType ustawiony na WinExe dla aplikacji WPF i WinForms</span><span class="sxs-lookup"><span data-stu-id="1a7b0-101">OutputType set to WinExe for WPF and WinForms apps</span></span>

<span data-ttu-id="1a7b0-102">`OutputType` jest automatycznie ustawiany na `WinExe` dla Windows Presentation Foundation (WPF) i Windows Forms aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1a7b0-102">`OutputType` is automatically set to `WinExe` for Windows Presentation Foundation (WPF) and Windows Forms apps.</span></span> <span data-ttu-id="1a7b0-103">Gdy `OutputType` jest ustawiona na `WinExe` , okno konsoli nie jest otwierane, gdy aplikacja jest wykonywana.</span><span class="sxs-lookup"><span data-stu-id="1a7b0-103">When `OutputType` is set to `WinExe`, a console window doesn't open when the app is executed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1a7b0-104">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="1a7b0-104">Change description</span></span>

<span data-ttu-id="1a7b0-105">W poprzednich wersjach programu .NET jest używana wartość określona dla `OutputType` pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="1a7b0-105">In previous versions of .NET, the value that's specified for `OutputType` in the project file is used.</span></span> <span data-ttu-id="1a7b0-106">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="1a7b0-106">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="1a7b0-107">Począwszy od platformy .NET 5,0, `OutputType` jest automatycznie ustawiany na `WinExe` dla aplikacji WPF i Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1a7b0-107">Starting in .NET 5.0, `OutputType` is automatically set to `WinExe` for WPF and Windows Forms apps.</span></span> <span data-ttu-id="1a7b0-108">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="1a7b0-108">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

#### <a name="reason-for-change"></a><span data-ttu-id="1a7b0-109">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="1a7b0-109">Reason for change</span></span>

<span data-ttu-id="1a7b0-110">Zakłada się, że większość użytkowników nie chce, aby okno konsoli było otwierane podczas wykonywania aplikacji WPF lub Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1a7b0-110">It's assumed that most users don't want a console window to open when a WPF or Windows Forms app is executed.</span></span> <span data-ttu-id="1a7b0-111">Ponadto, gdy [te typy aplikacji używają zestawu .NET SDK](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk) zamiast zestawu Windows Desktop SDK, zostanie ustawiona prawidłowa wartość domyślna.</span><span class="sxs-lookup"><span data-stu-id="1a7b0-111">In addition, [now that these application types use the .NET SDK](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk) instead of the Windows Desktop SDK, the correct default will be set.</span></span> <span data-ttu-id="1a7b0-112">Dodatkowo, gdy zostanie dodana obsługa dla urządzeń z systemami iOS i Android, będzie ona łatwiejsza dla wielu platform, jeśli wszystkie używają tego samego typu danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="1a7b0-112">Further, when support for targeting iOS and Android is added, it will be easier to multi-target between multiple platforms if they all use the same output type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1a7b0-113">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="1a7b0-113">Version introduced</span></span>

<span data-ttu-id="1a7b0-114">.NET 5,0 — wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="1a7b0-114">.NET 5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1a7b0-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="1a7b0-115">Recommended action</span></span>

<span data-ttu-id="1a7b0-116">W Twojej części nie jest wymagana żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="1a7b0-116">No action is required in your part.</span></span> <span data-ttu-id="1a7b0-117">Jeśli jednak chcesz przywrócić stare zachowanie, ustaw `DisableWinExeOutputInference` Właściwość na `true` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="1a7b0-117">However, if you want to revert to the old behavior, set the `DisableWinExeOutputInference` property to `true` in your project file.</span></span>

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

#### <a name="category"></a><span data-ttu-id="1a7b0-118">Kategoria</span><span class="sxs-lookup"><span data-stu-id="1a7b0-118">Category</span></span>

- <span data-ttu-id="1a7b0-119">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a7b0-119">Windows Forms</span></span>
- <span data-ttu-id="1a7b0-120">Struktura prezentacji systemu Windows (WPF)</span><span class="sxs-lookup"><span data-stu-id="1a7b0-120">Windows Presentation Framework (WPF)</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1a7b0-121">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="1a7b0-121">Affected APIs</span></span>

<span data-ttu-id="1a7b0-122">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="1a7b0-122">Not detectable via API analysis.</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
