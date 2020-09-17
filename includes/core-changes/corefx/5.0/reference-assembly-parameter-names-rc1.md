---
ms.openlocfilehash: 760c9ce2427bc1f5e9276e66ecb6d2cf2ed83c16
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738826"
---
### <a name="parameter-names-changed-in-rc1"></a><span data-ttu-id="c78e4-101">Nazwy parametrów zostały zmienione w wersji RC1</span><span class="sxs-lookup"><span data-stu-id="c78e4-101">Parameter names changed in RC1</span></span>

<span data-ttu-id="c78e4-102">Niektóre nazwy parametrów zestawu odwołania zostały zmienione w celu dopasowania do nazw parametrów w zestawach implementacji.</span><span class="sxs-lookup"><span data-stu-id="c78e4-102">Some reference assembly parameter names have changed to match parameter names in the implementation assemblies.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c78e4-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="c78e4-103">Change description</span></span>

<span data-ttu-id="c78e4-104">W poprzednich wersjach programu .NET 5,0 w wersji zapoznawczej i RC niektóre nazwy parametrów [zestawu odwołania](../../../../docs/standard/assembly/reference-assemblies.md) są inne niż odpowiadające im parametry w zestawie implementacji.</span><span class="sxs-lookup"><span data-stu-id="c78e4-104">In previous .NET 5.0 preview and RC versions, some [reference assembly](../../../../docs/standard/assembly/reference-assemblies.md) parameter names are different to their corresponding parameters in the implementation assembly.</span></span> <span data-ttu-id="c78e4-105">Może to spowodować problemy podczas korzystania z nazwanych argumentów i odbicie.</span><span class="sxs-lookup"><span data-stu-id="c78e4-105">This can cause problems while using named arguments and reflection.</span></span>

<span data-ttu-id="c78e4-106">W przypadku programu .NET 5,0 RC2 te niezgodne nazwy parametrów zostały zaktualizowane w zestawach odniesienia w celu dokładnego dopasowania do odpowiednich nazw parametrów w zestawach implementacji.</span><span class="sxs-lookup"><span data-stu-id="c78e4-106">In .NET 5.0 RC2, these mismatched parameter names were updated in the reference assemblies to exactly match the corresponding parameter names in the implementation assemblies.</span></span>

<span data-ttu-id="c78e4-107">W poniższej tabeli przedstawiono interfejsy API i nazwy parametrów, które uległy zmianie.</span><span class="sxs-lookup"><span data-stu-id="c78e4-107">The following table shows the APIs and parameter names that changed.</span></span>

| <span data-ttu-id="c78e4-108">Interfejs API</span><span class="sxs-lookup"><span data-stu-id="c78e4-108">API</span></span> | <span data-ttu-id="c78e4-109">Stara nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="c78e4-109">Old parameter name</span></span> | <span data-ttu-id="c78e4-110">Nazwa nowego parametru</span><span class="sxs-lookup"><span data-stu-id="c78e4-110">New parameter name</span></span> |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

#### <a name="reason-for-change"></a><span data-ttu-id="c78e4-111">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="c78e4-111">Reason for change</span></span>

<span data-ttu-id="c78e4-112">Nazwy parametrów zostały zmienione pod kątem spójności i w celu uniknięcia błędów przy użyciu nazwanych argumentów i odbicia.</span><span class="sxs-lookup"><span data-stu-id="c78e4-112">The parameter names were changed for consistency and to avoid failures when using named arguments and reflection.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c78e4-113">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="c78e4-113">Version introduced</span></span>

<span data-ttu-id="c78e4-114">5,0 RC2</span><span class="sxs-lookup"><span data-stu-id="c78e4-114">5.0 RC2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c78e4-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="c78e4-115">Recommended action</span></span>

<span data-ttu-id="c78e4-116">Jeśli wystąpi błąd kompilatora z powodu zmiany nazwy parametru, należy odpowiednio zaktualizować nazwę parametru.</span><span class="sxs-lookup"><span data-stu-id="c78e4-116">If you encounter a compiler error due to a parameter name change, update the parameter name accordingly.</span></span>

#### <a name="category"></a><span data-ttu-id="c78e4-117">Kategoria</span><span class="sxs-lookup"><span data-stu-id="c78e4-117">Category</span></span>

<span data-ttu-id="c78e4-118">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="c78e4-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c78e4-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="c78e4-119">Affected APIs</span></span>

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
