---
ms.openlocfilehash: 760c9ce2427bc1f5e9276e66ecb6d2cf2ed83c16
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738826"
---
### <a name="parameter-names-changed-in-rc1"></a>Nazwy parametrów zostały zmienione w wersji RC1

Niektóre nazwy parametrów zestawu odwołania zostały zmienione w celu dopasowania do nazw parametrów w zestawach implementacji.

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET 5,0 w wersji zapoznawczej i RC niektóre nazwy parametrów [zestawu odwołania](../../../../docs/standard/assembly/reference-assemblies.md) są inne niż odpowiadające im parametry w zestawie implementacji. Może to spowodować problemy podczas korzystania z nazwanych argumentów i odbicie.

W przypadku programu .NET 5,0 RC2 te niezgodne nazwy parametrów zostały zaktualizowane w zestawach odniesienia w celu dokładnego dopasowania do odpowiednich nazw parametrów w zestawach implementacji.

W poniższej tabeli przedstawiono interfejsy API i nazwy parametrów, które uległy zmianie.

| Interfejs API | Stara nazwa parametru | Nazwa nowego parametru |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

#### <a name="reason-for-change"></a>Przyczyna zmiany

Nazwy parametrów zostały zmienione pod kątem spójności i w celu uniknięcia błędów przy użyciu nazwanych argumentów i odbicia.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC2

#### <a name="recommended-action"></a>Zalecana akcja

Jeśli wystąpi błąd kompilatora z powodu zmiany nazwy parametru, należy odpowiednio zaktualizować nazwę parametru.

#### <a name="category"></a>Kategoria

Podstawowe biblioteki platformy .NET

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
