---
ms.openlocfilehash: 6431f3b4d0983c44629e4fe760c75adcc277ddd4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496727"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a><span data-ttu-id="ecf35-101">Niektóre interfejsy API platformy .NET powodują wystąpienie pierwszej szansy (obsłużone) EntryPointNotFoundExceptions</span><span class="sxs-lookup"><span data-stu-id="ecf35-101">Some .NET APIs cause first chance (handled) EntryPointNotFoundExceptions</span></span>

#### <a name="details"></a><span data-ttu-id="ecf35-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="ecf35-102">Details</span></span>

<span data-ttu-id="ecf35-103">W .NET Framework 4,5 niewielka liczba metod .NET rozpoczęła generowanie pierwszej szansy <xref:System.EntryPointNotFoundException?displayProperty=fullName> s.</span><span class="sxs-lookup"><span data-stu-id="ecf35-103">In the .NET Framework 4.5, a small number of .NET methods began throwing first chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span> <span data-ttu-id="ecf35-104">Te wyjątki zostały obsłużone w .NET Framework, ale mogą przerwać automatyzację testu, która nie oczekiwała na wyjątki pierwszej szansy.</span><span class="sxs-lookup"><span data-stu-id="ecf35-104">These exceptions were handled within the .NET Framework, but could break test automation that did not expect the first chance exceptions.</span></span> <span data-ttu-id="ecf35-105">Te same interfejsy API przerywają niektóre scenariusze ApiVerifier, gdy HighVersionLie jest włączony.</span><span class="sxs-lookup"><span data-stu-id="ecf35-105">These same APIs break some ApiVerifier scenarios when HighVersionLie is enabled.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ecf35-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="ecf35-106">Suggestion</span></span>

<span data-ttu-id="ecf35-107">Tę usterkę można uniknąć przez uaktualnienie do .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="ecf35-107">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="ecf35-108">Alternatywnie można zaktualizować automatyzację testową, aby nie przerywać pierwszej szansy <xref:System.EntryPointNotFoundException?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="ecf35-108">Alternatively, test automation can be updated to not break on first-chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span>

| <span data-ttu-id="ecf35-109">Nazwa</span><span class="sxs-lookup"><span data-stu-id="ecf35-109">Name</span></span>    | <span data-ttu-id="ecf35-110">Wartość</span><span class="sxs-lookup"><span data-stu-id="ecf35-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ecf35-111">Zakres</span><span class="sxs-lookup"><span data-stu-id="ecf35-111">Scope</span></span>   |<span data-ttu-id="ecf35-112">Edge</span><span class="sxs-lookup"><span data-stu-id="ecf35-112">Edge</span></span>|
|<span data-ttu-id="ecf35-113">Wersja</span><span class="sxs-lookup"><span data-stu-id="ecf35-113">Version</span></span>|<span data-ttu-id="ecf35-114">4.5</span><span class="sxs-lookup"><span data-stu-id="ecf35-114">4.5</span></span>|
|<span data-ttu-id="ecf35-115">Typ</span><span class="sxs-lookup"><span data-stu-id="ecf35-115">Type</span></span>|<span data-ttu-id="ecf35-116">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="ecf35-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ecf35-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="ecf35-117">Affected APIs</span></span>

- <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)>

<!--

#### Affected APIs

- `M:System.Diagnostics.Debug.Assert(System.Boolean)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])`
- `M:System.Xml.Serialization.XmlSerializer.#ctor(System.Type)`

-->
