---
ms.openlocfilehash: 6431f3b4d0983c44629e4fe760c75adcc277ddd4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496727"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>Niektóre interfejsy API platformy .NET powodują wystąpienie pierwszej szansy (obsłużone) EntryPointNotFoundExceptions

#### <a name="details"></a>Szczegóły

W .NET Framework 4,5 niewielka liczba metod .NET rozpoczęła generowanie pierwszej szansy <xref:System.EntryPointNotFoundException?displayProperty=fullName> s. Te wyjątki zostały obsłużone w .NET Framework, ale mogą przerwać automatyzację testu, która nie oczekiwała na wyjątki pierwszej szansy. Te same interfejsy API przerywają niektóre scenariusze ApiVerifier, gdy HighVersionLie jest włączony.

#### <a name="suggestion"></a>Sugestia

Tę usterkę można uniknąć przez uaktualnienie do .NET Framework 4.5.1. Alternatywnie można zaktualizować automatyzację testową, aby nie przerywać pierwszej szansy <xref:System.EntryPointNotFoundException?displayProperty=fullName> .

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe

#### <a name="affected-apis"></a>Dotyczy interfejsów API

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
