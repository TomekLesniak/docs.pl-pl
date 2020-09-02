---
ms.openlocfilehash: bba9659b92e5aabc276c585929c99898316036c5
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359141"
---
### <a name="hardware-intrinsic-issupported-checks-may-differ-for-nested-types"></a><span data-ttu-id="aad81-101">Wewnętrzne testy nieobsługiwane sprzętowo mogą się różnić w zależności od typów zagnieżdżonych</span><span class="sxs-lookup"><span data-stu-id="aad81-101">Hardware intrinsic IsSupported checks may differ for nested types</span></span>

<span data-ttu-id="aad81-102">Sprawdzanie `<Isa>.X64.IsSupported` , gdzie `<Isa>` odwołuje się do klas w <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> przestrzeni nazw, może teraz generować różne wyniki do poprzednich wersji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="aad81-102">Checking `<Isa>.X64.IsSupported`, where `<Isa>` refers to the classes in the <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> namespace, may now produce a different result to previous versions of .NET.</span></span>

> [!TIP]
> <span data-ttu-id="aad81-103">Program *ISA* jest przeznaczony dla standardowej architektury branżowej.</span><span class="sxs-lookup"><span data-stu-id="aad81-103">*ISA* stands for industry standard architecture.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="aad81-104">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="aad81-104">Version introduced</span></span>

<span data-ttu-id="aad81-105">5,0 wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="aad81-105">5.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="aad81-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="aad81-106">Change description</span></span>

<span data-ttu-id="aad81-107">W poprzednich wersjach programu .NET niektóre <xref:System.Runtime.Intrinsics.X86> Typy sprzętu — na przykład, <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType> nie uwidaczniają klasy zagnieżdżonej `X64` .</span><span class="sxs-lookup"><span data-stu-id="aad81-107">In previous versions of .NET, some of the <xref:System.Runtime.Intrinsics.X86> hardware-intrinsic types, for example, <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType>, didn't expose a nested `X64` class.</span></span> <span data-ttu-id="aad81-108">W przypadku tych typów wywoływanie `<Isa>.X64.IsSupported` został rozwiązany z `IsSupported` właściwością `X64` klasy zagnieżdżonej klasy nadrzędnej `<Isa>` .</span><span class="sxs-lookup"><span data-stu-id="aad81-108">For these types, calling `<Isa>.X64.IsSupported` resolved to an `IsSupported` property on a nested `X64` class of a parent class of `<Isa>`.</span></span> <span data-ttu-id="aad81-109">Oznacza to, że właściwość może zwrócić `true` nawet wtedy, gdy `<Isa>.IsSupported` zwraca `false` .</span><span class="sxs-lookup"><span data-stu-id="aad81-109">This meant that the property could return `true` even when `<Isa>.IsSupported` returns `false`.</span></span>

<span data-ttu-id="aad81-110">W programie .NET 5,0 i jego nowszych wersjach wszystkie <xref:System.Runtime.Intrinsics.X86> typy uwidaczniają zagnieżdżoną `X64` klasę, która odpowiednio obsługuje raporty.</span><span class="sxs-lookup"><span data-stu-id="aad81-110">In .NET 5.0 and later versions, all of the <xref:System.Runtime.Intrinsics.X86> types expose a nested `X64` class that appropriately reports support.</span></span> <span data-ttu-id="aad81-111">Dzięki temu ogólna hierarchia jest poprawna, a w `<Isa>.X64.IsSupported` przypadku `true` , gdy jest, `<Isa>.IsSupported` można również przyjąć, że jest to możliwe `true` .</span><span class="sxs-lookup"><span data-stu-id="aad81-111">This ensures that the general hierarchy remains correct, and that if `<Isa>.X64.IsSupported` is `true`, then `<Isa>.IsSupported` can also be assumed to be `true`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="aad81-112">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="aad81-112">Reason for change</span></span>

<span data-ttu-id="aad81-113">Miało to `<Isa>.X64.IsSupported` `true` na celu, że `<Isa>.IsSupported` jest również implikowane `true` .</span><span class="sxs-lookup"><span data-stu-id="aad81-113">It was intended that if `<Isa>.X64.IsSupported` is `true`, `<Isa>.IsSupported` is also implied to be `true`.</span></span> <span data-ttu-id="aad81-114">Jednak ze względu na sposób, w jaki rozpoznawanie elementów członkowskich działa w języku C#, klasy, które nie miały klasy zagnieżdżonej, `X64` uwidaczniają sytuację, w której to nigdy nie było tak samo, i doprowadziło do błędów w kodzie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="aad81-114">However, due to how member resolution works in C#, classes that didn't have a nested `X64` class exposed a situation where this wasn't always the case and led to bugs in user code.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="aad81-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="aad81-115">Recommended action</span></span>

<span data-ttu-id="aad81-116">W razie potrzeby dostosuj kod, który sprawdza, czy `IsSupported` ma być sprawdzana odpowiednia wartość ISA.</span><span class="sxs-lookup"><span data-stu-id="aad81-116">If necessary, adjust code that checks `IsSupported` to check for the appropriate ISA.</span></span>

#### <a name="category"></a><span data-ttu-id="aad81-117">Kategoria</span><span class="sxs-lookup"><span data-stu-id="aad81-117">Category</span></span>

<span data-ttu-id="aad81-118">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="aad81-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="aad81-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="aad81-119">Affected APIs</span></span>

- <xref:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported`

-->
