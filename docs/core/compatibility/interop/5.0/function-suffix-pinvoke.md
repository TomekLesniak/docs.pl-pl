---
title: 'Nieprzerwana zmiana: nie znaleziono sufiksu/W na platformach innych niż Windows'
description: Dowiedz się więcej o zmianie nieprzerwaności międzyoperacyjności w programie .NET 5,0, gdzie sufiksy nie są już dodawane do funkcji eksportowania nazw podczas sondowania dla P/Invoke na platformach innych niż Windows.
ms.date: 08/13/2020
ms.openlocfilehash: a4c612a81796faf80fa257df21232a54f7b95431
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761551"
---
# <a name="no-aw-suffix-probing-on-non-windows-platforms"></a><span data-ttu-id="d515d-103">Brak podwyższenia poziomu sufiksu na platformach innych niż Windows</span><span class="sxs-lookup"><span data-stu-id="d515d-103">No A/W suffix probing on non-Windows platforms</span></span>

<span data-ttu-id="d515d-104">Środowisko uruchomieniowe platformy .NET nie dodaje już `A` `W` sufiksu lub do funkcji eksportu nazw podczas sondowania dla P/Invoke na platformach innych niż Windows.</span><span class="sxs-lookup"><span data-stu-id="d515d-104">The .NET runtimes no longer add an `A` or `W` suffix to function export names during probing for P/Invokes on non-Windows platforms.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d515d-105">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="d515d-105">Version introduced</span></span>

<span data-ttu-id="d515d-106">5,0</span><span class="sxs-lookup"><span data-stu-id="d515d-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="d515d-107">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="d515d-107">Change description</span></span>

<span data-ttu-id="d515d-108">[System Windows ma konwencję](/windows/win32/intl/conventions-for-function-prototypes) dodawania `A` `W` sufiksu lub do Windows SDK nazw funkcji, które są odpowiednio zgodne ze stroną kodową systemu Windows i wersjami Unicode.</span><span class="sxs-lookup"><span data-stu-id="d515d-108">[Windows has a convention](/windows/win32/intl/conventions-for-function-prototypes) of adding an `A` or `W` suffix to Windows SDK function names, which correspond to the Windows code page and Unicode versions, respectively.</span></span>

<span data-ttu-id="d515d-109">We wcześniejszych wersjach programu .NET środowisko uruchomieniowe CoreCLR i mono dodaje `A` `W` sufiks lub do nazwy eksportu podczas odnajdywania eksportu dla P/Invoke *na wszystkich platformach*.</span><span class="sxs-lookup"><span data-stu-id="d515d-109">In previous versions of .NET, both the CoreCLR and Mono runtimes add an `A` or `W` suffix to the export name during export discovery for P/Invokes *on all platforms*.</span></span>

<span data-ttu-id="d515d-110">W programie .NET 5,0 i nowszych wersjach `A` sufiks lub `W` jest dodawany do nazwy eksportu podczas odnajdywania eksportu *tylko w systemie Windows*.</span><span class="sxs-lookup"><span data-stu-id="d515d-110">In .NET 5.0 and later versions, an `A` or `W` suffix is added to the export name during export discovery *on Windows only*.</span></span> <span data-ttu-id="d515d-111">Na platformach UNIX sufiks nie jest dodawany.</span><span class="sxs-lookup"><span data-stu-id="d515d-111">On Unix platforms, the suffix is not added.</span></span> <span data-ttu-id="d515d-112">Semantyka obu środowisk uruchomieniowych na platformie Windows pozostaje niezmieniona.</span><span class="sxs-lookup"><span data-stu-id="d515d-112">The semantics of both runtimes on the Windows platform remain unchanged.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d515d-113">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="d515d-113">Reason for change</span></span>

<span data-ttu-id="d515d-114">Ta zmiana została wprowadzona w celu uproszczenia sondowania międzyplatformowego.</span><span class="sxs-lookup"><span data-stu-id="d515d-114">This change was made to simplify cross-platform probing.</span></span> <span data-ttu-id="d515d-115">Nie należy tego robić, ponieważ platformy inne niż Windows nie zawierają tej semantyki.</span><span class="sxs-lookup"><span data-stu-id="d515d-115">It's overhead that shouldn't be incurred, given that non-Windows platforms don't contain this semantic.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d515d-116">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="d515d-116">Recommended action</span></span>

<span data-ttu-id="d515d-117">Aby wyeliminować zmianę, można ręcznie dodać żądany sufiks na platformach innych niż Windows.</span><span class="sxs-lookup"><span data-stu-id="d515d-117">To mitigate the change, you can manually add the desired suffix on non-Windows platforms.</span></span> <span data-ttu-id="d515d-118">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="d515d-118">For example:</span></span>

```csharp
[DllImport(...)]
extern static void SetWindowTextW();
```

## <a name="affected-apis"></a><span data-ttu-id="d515d-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d515d-119">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Runtime.InteropServices.DllImportAttribute`

### Category

Interop

-->
