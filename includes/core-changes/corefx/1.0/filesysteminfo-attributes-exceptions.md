---
ms.openlocfilehash: 2ea9abca7578c2ddf92712a1c597f8f1ff4a5c0c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032081"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a><span data-ttu-id="ca9bb-101">UnauthorizedAccessException zgłoszone przez FileSystemInfo. Attributes</span><span class="sxs-lookup"><span data-stu-id="ca9bb-101">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>

<span data-ttu-id="ca9bb-102">W przypadku platformy .NET Core <xref:System.UnauthorizedAccessException> jest generowany, gdy wywołujący próbuje ustawić wartość atrybutu pliku, ale nie ma uprawnienia do zapisu.</span><span class="sxs-lookup"><span data-stu-id="ca9bb-102">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown when the caller attempts to set a file attribute value but doesn't have write permission.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ca9bb-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="ca9bb-103">Change description</span></span>

<span data-ttu-id="ca9bb-104">W .NET Framework <xref:System.ArgumentException> jest generowany, gdy obiekt wywołujący próbuje ustawić wartość atrybutu pliku w programie, <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> ale nie ma uprawnienia do zapisu.</span><span class="sxs-lookup"><span data-stu-id="ca9bb-104">In .NET Framework, an <xref:System.ArgumentException> is thrown when the caller attempts to set a file attribute value in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> but doesn't have write permission.</span></span> <span data-ttu-id="ca9bb-105">W przypadku platformy .NET Core <xref:System.UnauthorizedAccessException> jest zgłaszany.</span><span class="sxs-lookup"><span data-stu-id="ca9bb-105">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown instead.</span></span> <span data-ttu-id="ca9bb-106">(W programie .NET Core <xref:System.ArgumentException> jest nadal zgłaszane, jeśli obiekt wywołujący podejmie próbę ustawienia nieprawidłowego atrybutu pliku).</span><span class="sxs-lookup"><span data-stu-id="ca9bb-106">(In .NET Core, an <xref:System.ArgumentException> is still thrown if the caller attempts to set an invalid file attribute.)</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ca9bb-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="ca9bb-107">Version introduced</span></span>

<span data-ttu-id="ca9bb-108">1,0</span><span class="sxs-lookup"><span data-stu-id="ca9bb-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ca9bb-109">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="ca9bb-109">Recommended action</span></span>

<span data-ttu-id="ca9bb-110">Zmodyfikuj wszelkie `catch` instrukcje, aby przechwycić <xref:System.UnauthorizedAccessException> zamiast lub, w razie potrzeby,, lub oprócz, <xref:System.ArgumentException> .</span><span class="sxs-lookup"><span data-stu-id="ca9bb-110">Modify any `catch` statements to catch an <xref:System.UnauthorizedAccessException> instead of, or in addition to, an <xref:System.ArgumentException>, as necessary.</span></span>

#### <a name="category"></a><span data-ttu-id="ca9bb-111">Kategoria</span><span class="sxs-lookup"><span data-stu-id="ca9bb-111">Category</span></span>

<span data-ttu-id="ca9bb-112">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="ca9bb-112">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ca9bb-113">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="ca9bb-113">Affected APIs</span></span>

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
