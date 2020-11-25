---
ms.openlocfilehash: 9544b65f31772d0f4cee918528a73171fec4de99
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032053"
---
### <a name="change-in-default-value-of-useshellexecute"></a><span data-ttu-id="754d6-101">Zmień wartość domyślną UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="754d6-101">Change in default value of UseShellExecute</span></span>

<span data-ttu-id="754d6-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> ma wartość domyślną `false` w programie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="754d6-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> has a default value of `false` on .NET Core.</span></span> <span data-ttu-id="754d6-103">W .NET Framework wartość domyślna to `true` .</span><span class="sxs-lookup"><span data-stu-id="754d6-103">On .NET Framework, its default value is `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="754d6-104">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="754d6-104">Change description</span></span>

<span data-ttu-id="754d6-105"><xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> umożliwia uruchamianie aplikacji bezpośrednio, na przykład przy użyciu kodu, takiego jak `Process.Start("mspaint.exe")` uruchomienie programu Paint.</span><span class="sxs-lookup"><span data-stu-id="754d6-105"><xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> lets you launch an application directly, for example, with code such as `Process.Start("mspaint.exe")` that launches Paint.</span></span> <span data-ttu-id="754d6-106">Umożliwia ona również pośrednio uruchomienie skojarzonej aplikacji, jeśli <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> jest ustawiona na `true` .</span><span class="sxs-lookup"><span data-stu-id="754d6-106">It also lets you indirectly launch an associated application if <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is set to `true`.</span></span> <span data-ttu-id="754d6-107">Na .NET Framework wartość domyślna <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `true` , co oznacza, że kod taki jak `Process.Start("mytextfile.txt")` zostałby uruchomiony Notatnik, jeśli masz skojarzone pliki *txt* z tym edytorem.</span><span class="sxs-lookup"><span data-stu-id="754d6-107">On .NET Framework, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `true`, meaning that code such as `Process.Start("mytextfile.txt")` would launch Notepad, if you've associated *.txt* files with that editor.</span></span> <span data-ttu-id="754d6-108">Aby zapobiec pośredniemu uruchamianiu aplikacji na .NET Framework, musisz jawnie ustawić <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> wartość `false` .</span><span class="sxs-lookup"><span data-stu-id="754d6-108">To prevent indirectly launching an app on .NET Framework, you must explicitly set <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="754d6-109">W przypadku platformy .NET Core wartość domyślna <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false` .</span><span class="sxs-lookup"><span data-stu-id="754d6-109">On .NET Core, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `false`.</span></span> <span data-ttu-id="754d6-110">Oznacza to, że domyślnie skojarzone aplikacje nie są uruchamiane podczas wywoływania `Process.Start` .</span><span class="sxs-lookup"><span data-stu-id="754d6-110">This means that, by default, associated applications are not launched when you call `Process.Start`.</span></span>

<span data-ttu-id="754d6-111">Ta zmiana została wprowadzona w programie .NET Core ze względu na wydajność.</span><span class="sxs-lookup"><span data-stu-id="754d6-111">This change was introduced in .NET Core for performance reasons.</span></span> <span data-ttu-id="754d6-112">Zwykle <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> jest używany do bezpośredniego uruchamiania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="754d6-112">Typically, <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> is used to launch an application directly.</span></span> <span data-ttu-id="754d6-113">Bezpośrednie uruchamianie aplikacji nie wymaga ponoszenia powłoki systemu Windows i wiąże się z powiązanymi kosztami wydajności.</span><span class="sxs-lookup"><span data-stu-id="754d6-113">Launching an app directly does not need to involve the Windows shell and incur the associated performance cost.</span></span> <span data-ttu-id="754d6-114">Aby ten przypadek domyślny był szybszy, program .NET Core zmienia wartość domyślną <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> na `false` .</span><span class="sxs-lookup"><span data-stu-id="754d6-114">To make this default case faster, .NET Core changes the default value of <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="754d6-115">Jeśli potrzebujesz, możesz zrezygnować z wolniejszej ścieżki.</span><span class="sxs-lookup"><span data-stu-id="754d6-115">You can opt in to the slower path if you need it.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="754d6-116">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="754d6-116">Version introduced</span></span>

<span data-ttu-id="754d6-117">2.1</span><span class="sxs-lookup"><span data-stu-id="754d6-117">2.1</span></span>

> [!NOTE]
> <span data-ttu-id="754d6-118">We wcześniejszych wersjach programu .NET Core `UseShellExecute` nie została zaimplementowana dla systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="754d6-118">In earlier versions of .NET Core, `UseShellExecute` was not implemented for Windows.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="754d6-119">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="754d6-119">Recommended action</span></span>

<span data-ttu-id="754d6-120">Jeśli aplikacja korzysta ze starego zachowania, należy wywołać polecenie <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> z <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> ustawioną `true` na wartość dla <xref:System.Diagnostics.ProcessStartInfo> obiektu.</span><span class="sxs-lookup"><span data-stu-id="754d6-120">If your app relies on the old behavior, call <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> with <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> set to `true` on the <xref:System.Diagnostics.ProcessStartInfo> object.</span></span>

#### <a name="category"></a><span data-ttu-id="754d6-121">Kategoria</span><span class="sxs-lookup"><span data-stu-id="754d6-121">Category</span></span>

<span data-ttu-id="754d6-122">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="754d6-122">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="754d6-123">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="754d6-123">Affected APIs</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
