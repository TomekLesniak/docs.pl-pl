---
ms.openlocfilehash: 43ebb37124b8efe077b9f81fe5351bd7db2c72f7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302721"
---
### <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a><span data-ttu-id="5e27c-101">Wektor \<T> zawsze zgłasza NotSupportedException dla nieobsługiwanych typów</span><span class="sxs-lookup"><span data-stu-id="5e27c-101">Vector\<T> always throws NotSupportedException for unsupported types</span></span>

<span data-ttu-id="5e27c-102"><xref:System.Numerics.Vector%601?displayProperty=nameWithType>teraz zawsze jest zgłaszany <xref:System.NotSupportedException> dla nieobsługiwanych parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="5e27c-102"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> now always throws a <xref:System.NotSupportedException> for unsupported type parameters.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5e27c-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="5e27c-103">Change description</span></span>

<span data-ttu-id="5e27c-104">Wcześniej elementy członkowskie <xref:System.Numerics.Vector%601> nie zawsze zgłaszają <xref:System.NotSupportedException> `T` [nieobsługiwany typ](#unsupported-types).</span><span class="sxs-lookup"><span data-stu-id="5e27c-104">Previously, members of <xref:System.Numerics.Vector%601> would not always throw a <xref:System.NotSupportedException> when `T` was an [unsupported type](#unsupported-types).</span></span> <span data-ttu-id="5e27c-105">Wyjątek nie został zawsze wygenerowany ze względu na ścieżki kodu obsługujące przyspieszenie sprzętowe.</span><span class="sxs-lookup"><span data-stu-id="5e27c-105">The exception wasn't always thrown because of code paths that supported hardware acceleration.</span></span> <span data-ttu-id="5e27c-106">Na przykład `Vector<bool> + Vector<bool>` `default` zamiast zgłaszać wyjątek na platformach, które nie mają przyspieszenia sprzętowego, takiego jak ARM32.</span><span class="sxs-lookup"><span data-stu-id="5e27c-106">For example, `Vector<bool> + Vector<bool>` returned `default` instead of throwing an exception on platforms that have no hardware acceleration, such as ARM32.</span></span> <span data-ttu-id="5e27c-107">W przypadku nieobsługiwanych typów <xref:System.Numerics.Vector%601> elementy członkowskie wykazują niespójne zachowanie na różnych platformach i konfiguracjach sprzętu.</span><span class="sxs-lookup"><span data-stu-id="5e27c-107">For unsupported types, <xref:System.Numerics.Vector%601> members exhibited inconsistent behavior across different platforms and hardware configurations.</span></span>

<span data-ttu-id="5e27c-108">Począwszy od platformy .NET 5,0, <xref:System.Numerics.Vector%601> członkowie zawsze zgłaszają <xref:System.NotSupportedException> wszystkie konfiguracje sprzętu, gdy `T` nie jest to obsługiwanego typu.</span><span class="sxs-lookup"><span data-stu-id="5e27c-108">Starting in .NET 5.0, <xref:System.Numerics.Vector%601> members always throw a <xref:System.NotSupportedException> on all hardware configurations when `T` is not a supported type.</span></span>

##### <a name="unsupported-types"></a><span data-ttu-id="5e27c-109">Nieobsługiwane typy</span><span class="sxs-lookup"><span data-stu-id="5e27c-109">Unsupported types</span></span>

<span data-ttu-id="5e27c-110">Obsługiwane typy dla parametru typu <xref:System.Numerics.Vector%601> są:</span><span class="sxs-lookup"><span data-stu-id="5e27c-110">The supported types for the type parameter of <xref:System.Numerics.Vector%601> are:</span></span>

- `byte`
- `sbyte`
- `short`
- `ushort`
- `int`
- `uint`
- `long`
- `ulong`
- `float`
- `double`

<span data-ttu-id="5e27c-111">Obsługiwane typy nie uległy zmianie, ale mogą ulec zmianie w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="5e27c-111">The supported types have not changed, however, they may change in the future.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5e27c-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="5e27c-112">Version introduced</span></span>

<span data-ttu-id="5e27c-113">5,0 wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="5e27c-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5e27c-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="5e27c-114">Recommended action</span></span>

<span data-ttu-id="5e27c-115">Nie używaj nieobsługiwanego typu dla parametru typu <xref:System.Numerics.Vector%601> .</span><span class="sxs-lookup"><span data-stu-id="5e27c-115">Don't use an unsupported type for the type parameter of <xref:System.Numerics.Vector%601>.</span></span>

#### <a name="category"></a><span data-ttu-id="5e27c-116">Kategoria</span><span class="sxs-lookup"><span data-stu-id="5e27c-116">Category</span></span>

<span data-ttu-id="5e27c-117">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="5e27c-117">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5e27c-118">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="5e27c-118">Affected APIs</span></span>

- <span data-ttu-id="5e27c-119"><xref:System.Numerics.Vector%601?displayProperty=fullName>i wszystkie jej elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="5e27c-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> and all its members</span></span>

<!--

#### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
