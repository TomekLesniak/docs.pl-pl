---
ms.openlocfilehash: e128bdb5735b3e4844356ad4807cc092f6f2b105
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062431"
---
### <a name="no-aw-suffix-probing-on-non-windows-platforms"></a><span data-ttu-id="e46d6-101">Brak podwyższenia poziomu sufiksu na platformach innych niż Windows</span><span class="sxs-lookup"><span data-stu-id="e46d6-101">No A/W suffix probing on non-Windows platforms</span></span>

<span data-ttu-id="e46d6-102">Środowisko uruchomieniowe platformy .NET nie dodaje już `A` `W` sufiksu lub do funkcji eksportu nazw podczas sondowania dla P/Invoke na platformach innych niż Windows.</span><span class="sxs-lookup"><span data-stu-id="e46d6-102">The .NET runtimes no longer add an `A` or `W` suffix to function export names during probing for P/Invokes on non-Windows platforms.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e46d6-103">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="e46d6-103">Version introduced</span></span>

<span data-ttu-id="e46d6-104">5,0 wersja zapoznawcza 4</span><span class="sxs-lookup"><span data-stu-id="e46d6-104">5.0 Preview 4</span></span>

#### <a name="change-description"></a><span data-ttu-id="e46d6-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="e46d6-105">Change description</span></span>

<span data-ttu-id="e46d6-106">[System Windows ma konwencję](/windows/win32/intl/conventions-for-function-prototypes) dodawania `A` `W` sufiksu lub do Windows SDK nazw funkcji, które są odpowiednio zgodne ze stroną kodową systemu Windows i wersjami Unicode.</span><span class="sxs-lookup"><span data-stu-id="e46d6-106">[Windows has a convention](/windows/win32/intl/conventions-for-function-prototypes) of adding an `A` or `W` suffix to Windows SDK function names, which correspond to the Windows code page and Unicode versions, respectively.</span></span>

<span data-ttu-id="e46d6-107">We wcześniejszych wersjach programu .NET środowisko uruchomieniowe CoreCLR i mono dodaje `A` `W` sufiks lub do nazwy eksportu podczas odnajdywania eksportu dla P/Invoke *na wszystkich platformach*.</span><span class="sxs-lookup"><span data-stu-id="e46d6-107">In previous versions of .NET, both the CoreCLR and Mono runtimes add an `A` or `W` suffix to the export name during export discovery for P/Invokes *on all platforms*.</span></span>

<span data-ttu-id="e46d6-108">W programie .NET 5,0 i nowszych wersjach `A` sufiks lub `W` jest dodawany do nazwy eksportu podczas odnajdywania eksportu *tylko w systemie Windows*.</span><span class="sxs-lookup"><span data-stu-id="e46d6-108">In .NET 5.0 and later versions, an `A` or `W` suffix is added to the export name during export discovery *on Windows only*.</span></span> <span data-ttu-id="e46d6-109">Na platformach UNIX sufiks nie jest dodawany.</span><span class="sxs-lookup"><span data-stu-id="e46d6-109">On Unix platforms, the suffix is not added.</span></span> <span data-ttu-id="e46d6-110">Semantyka obu środowisk uruchomieniowych na platformie Windows pozostaje niezmieniona.</span><span class="sxs-lookup"><span data-stu-id="e46d6-110">The semantics of both runtimes on the Windows platform remain unchanged.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e46d6-111">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="e46d6-111">Reason for change</span></span>

<span data-ttu-id="e46d6-112">Ta zmiana została wprowadzona w celu uproszczenia sondowania międzyplatformowego.</span><span class="sxs-lookup"><span data-stu-id="e46d6-112">This change was made to simplify cross-platform probing.</span></span> <span data-ttu-id="e46d6-113">Nie należy tego robić, ponieważ platformy inne niż Windows nie zawierają tej semantyki.</span><span class="sxs-lookup"><span data-stu-id="e46d6-113">It's overhead that shouldn't be incurred, given that non-Windows platforms don't contain this semantic.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e46d6-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="e46d6-114">Recommended action</span></span>

<span data-ttu-id="e46d6-115">Aby wyeliminować zmianę, można ręcznie dodać żądany sufiks na platformach innych niż Windows.</span><span class="sxs-lookup"><span data-stu-id="e46d6-115">To mitigate the change, you can manually add the desired suffix on non-Windows platforms.</span></span> <span data-ttu-id="e46d6-116">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="e46d6-116">For example:</span></span>

```csharp
[DllImport(...)]
extern static void SetWindowTextW();
```

#### <a name="category"></a><span data-ttu-id="e46d6-117">Kategoria</span><span class="sxs-lookup"><span data-stu-id="e46d6-117">Category</span></span>

<span data-ttu-id="e46d6-118">Interop</span><span class="sxs-lookup"><span data-stu-id="e46d6-118">Interop</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e46d6-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="e46d6-119">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Runtime.InteropServices.DllImportAttribute`

-->
