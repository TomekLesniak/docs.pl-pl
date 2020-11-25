---
title: 'Zmiana podziału: wartość OutputType ustawiona na WinExe dla aplikacji WPF i WinForms'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, gdzie wartość OutputType jest automatycznie ustawiana na WinExe dla aplikacji Windows Forms.
ms.date: 09/18/2020
ms.openlocfilehash: 072c5b11c8304eb540e176ce9747930789f28505
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761684"
---
# <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a><span data-ttu-id="f6678-103">OutputType ustawiony na WinExe dla aplikacji WPF i WinForms</span><span class="sxs-lookup"><span data-stu-id="f6678-103">OutputType set to WinExe for WPF and WinForms apps</span></span>

<span data-ttu-id="f6678-104">`OutputType` jest automatycznie ustawiany na `WinExe` dla Windows Presentation Foundation (WPF) i Windows Forms aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f6678-104">`OutputType` is automatically set to `WinExe` for Windows Presentation Foundation (WPF) and Windows Forms apps.</span></span> <span data-ttu-id="f6678-105">Gdy `OutputType` jest ustawiona na `WinExe` , okno konsoli nie jest otwierane, gdy aplikacja jest wykonywana.</span><span class="sxs-lookup"><span data-stu-id="f6678-105">When `OutputType` is set to `WinExe`, a console window doesn't open when the app is executed.</span></span>

## <a name="change-description"></a><span data-ttu-id="f6678-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="f6678-106">Change description</span></span>

<span data-ttu-id="f6678-107">W poprzednich wersjach programu .NET jest używana wartość określona dla `OutputType` pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="f6678-107">In previous versions of .NET, the value that's specified for `OutputType` in the project file is used.</span></span> <span data-ttu-id="f6678-108">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="f6678-108">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="f6678-109">Począwszy od platformy .NET 5,0, `OutputType` jest automatycznie ustawiany na `WinExe` dla aplikacji WPF i Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f6678-109">Starting in .NET 5.0, `OutputType` is automatically set to `WinExe` for WPF and Windows Forms apps.</span></span> <span data-ttu-id="f6678-110">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="f6678-110">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

## <a name="reason-for-change"></a><span data-ttu-id="f6678-111">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="f6678-111">Reason for change</span></span>

<span data-ttu-id="f6678-112">Zakłada się, że większość użytkowników nie chce, aby okno konsoli było otwierane podczas wykonywania aplikacji WPF lub Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f6678-112">It's assumed that most users don't want a console window to open when a WPF or Windows Forms app is executed.</span></span> <span data-ttu-id="f6678-113">Ponadto, gdy [te typy aplikacji używają zestawu .NET SDK](sdk-and-target-framework-change.md) zamiast zestawu Windows Desktop SDK, zostanie ustawiona prawidłowa wartość domyślna.</span><span class="sxs-lookup"><span data-stu-id="f6678-113">In addition, [now that these application types use the .NET SDK](sdk-and-target-framework-change.md) instead of the Windows Desktop SDK, the correct default will be set.</span></span> <span data-ttu-id="f6678-114">Dodatkowo, gdy zostanie dodana obsługa dla urządzeń z systemami iOS i Android, będzie ona łatwiejsza dla wielu platform, jeśli wszystkie używają tego samego typu danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="f6678-114">Further, when support for targeting iOS and Android is added, it will be easier to multi-target between multiple platforms if they all use the same output type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f6678-115">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="f6678-115">Version introduced</span></span>

<span data-ttu-id="f6678-116">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="f6678-116">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f6678-117">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="f6678-117">Recommended action</span></span>

<span data-ttu-id="f6678-118">W Twojej części nie jest wymagana żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="f6678-118">No action is required in your part.</span></span> <span data-ttu-id="f6678-119">Jeśli jednak chcesz przywrócić stare zachowanie, ustaw `DisableWinExeOutputInference` Właściwość na `true` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="f6678-119">However, if you want to revert to the old behavior, set the `DisableWinExeOutputInference` property to `true` in your project file.</span></span>

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

## <a name="affected-apis"></a><span data-ttu-id="f6678-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="f6678-120">Affected APIs</span></span>

<span data-ttu-id="f6678-121">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="f6678-121">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
