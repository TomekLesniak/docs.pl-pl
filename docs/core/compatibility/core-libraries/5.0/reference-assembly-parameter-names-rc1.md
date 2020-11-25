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
# <a name="parameter-names-changed-in-rc2"></a>Nazwy parametrów zostały zmienione w RC2

Niektóre nazwy parametrów zestawu odwołania zostały zmienione w celu dopasowania do nazw parametrów w zestawach implementacji.

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET 5,0 w wersji zapoznawczej i RC niektóre nazwy parametrów [zestawu odwołania](../../../../standard/assembly/reference-assemblies.md) są inne niż odpowiadające im parametry w zestawie implementacji. Może to spowodować problemy podczas korzystania z nazwanych argumentów i odbicie.

W przypadku programu .NET 5,0 RC2 te niezgodne nazwy parametrów zostały zaktualizowane w zestawach odniesienia w celu dokładnego dopasowania do odpowiednich nazw parametrów w zestawach implementacji.

W poniższej tabeli przedstawiono interfejsy API i nazwy parametrów, które uległy zmianie.

| Interfejs API | Stara nazwa parametru | Nazwa nowego parametru |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

## <a name="reason-for-change"></a>Przyczyna zmiany

Nazwy parametrów zostały zmienione pod kątem spójności i w celu uniknięcia błędów przy użyciu nazwanych argumentów i odbicia.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC2

## <a name="recommended-action"></a>Zalecana akcja

Jeśli wystąpi błąd kompilatora z powodu zmiany nazwy parametru, należy odpowiednio zaktualizować nazwę parametru.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
