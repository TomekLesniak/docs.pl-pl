---
title: 'Istotna zmiana: nazwy parametrów zostały zmienione w RC2'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których niektóre nazwy parametrów zestawów odwołań zostały zmienione w wersjach zapoznawczych i Release-Candidate programu .NET 5,0.
ms.date: 11/01/2020
ms.openlocfilehash: 554a4fa9e08fdb504f380465496d7e7e9df85814
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761503"
---
# <a name="parameter-names-changed-in-rc2"></a><span data-ttu-id="97a07-103">Nazwy parametrów zostały zmienione w RC2</span><span class="sxs-lookup"><span data-stu-id="97a07-103">Parameter names changed in RC2</span></span>

<span data-ttu-id="97a07-104">Niektóre nazwy parametrów zestawu odwołania zostały zmienione w celu dopasowania do nazw parametrów w zestawach implementacji.</span><span class="sxs-lookup"><span data-stu-id="97a07-104">Some reference assembly parameter names have changed to match parameter names in the implementation assemblies.</span></span>

## <a name="change-description"></a><span data-ttu-id="97a07-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="97a07-105">Change description</span></span>

<span data-ttu-id="97a07-106">W poprzednich wersjach programu .NET 5,0 w wersji zapoznawczej i RC niektóre nazwy parametrów [zestawu odwołania](../../../../standard/assembly/reference-assemblies.md) są inne niż odpowiadające im parametry w zestawie implementacji.</span><span class="sxs-lookup"><span data-stu-id="97a07-106">In previous .NET 5.0 preview and RC versions, some [reference assembly](../../../../standard/assembly/reference-assemblies.md) parameter names are different to their corresponding parameters in the implementation assembly.</span></span> <span data-ttu-id="97a07-107">Może to spowodować problemy podczas korzystania z nazwanych argumentów i odbicie.</span><span class="sxs-lookup"><span data-stu-id="97a07-107">This can cause problems while using named arguments and reflection.</span></span>

<span data-ttu-id="97a07-108">W przypadku programu .NET 5,0 RC2 te niezgodne nazwy parametrów zostały zaktualizowane w zestawach odniesienia w celu dokładnego dopasowania do odpowiednich nazw parametrów w zestawach implementacji.</span><span class="sxs-lookup"><span data-stu-id="97a07-108">In .NET 5.0 RC2, these mismatched parameter names were updated in the reference assemblies to exactly match the corresponding parameter names in the implementation assemblies.</span></span>

<span data-ttu-id="97a07-109">W poniższej tabeli przedstawiono interfejsy API i nazwy parametrów, które uległy zmianie.</span><span class="sxs-lookup"><span data-stu-id="97a07-109">The following table shows the APIs and parameter names that changed.</span></span>

| <span data-ttu-id="97a07-110">Interfejs API</span><span class="sxs-lookup"><span data-stu-id="97a07-110">API</span></span> | <span data-ttu-id="97a07-111">Stara nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="97a07-111">Old parameter name</span></span> | <span data-ttu-id="97a07-112">Nazwa nowego parametru</span><span class="sxs-lookup"><span data-stu-id="97a07-112">New parameter name</span></span> |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

## <a name="reason-for-change"></a><span data-ttu-id="97a07-113">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="97a07-113">Reason for change</span></span>

<span data-ttu-id="97a07-114">Nazwy parametrów zostały zmienione pod kątem spójności i w celu uniknięcia błędów przy użyciu nazwanych argumentów i odbicia.</span><span class="sxs-lookup"><span data-stu-id="97a07-114">The parameter names were changed for consistency and to avoid failures when using named arguments and reflection.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="97a07-115">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="97a07-115">Version introduced</span></span>

<span data-ttu-id="97a07-116">5,0 RC2</span><span class="sxs-lookup"><span data-stu-id="97a07-116">5.0 RC2</span></span>

## <a name="recommended-action"></a><span data-ttu-id="97a07-117">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="97a07-117">Recommended action</span></span>

<span data-ttu-id="97a07-118">Jeśli wystąpi błąd kompilatora z powodu zmiany nazwy parametru, należy odpowiednio zaktualizować nazwę parametru.</span><span class="sxs-lookup"><span data-stu-id="97a07-118">If you encounter a compiler error due to a parameter name change, update the parameter name accordingly.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="97a07-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="97a07-119">Affected APIs</span></span>

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
