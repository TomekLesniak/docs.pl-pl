---
ms.openlocfilehash: 018c99d60dc8926cae2682dc9c035e25fba711e5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496849"
---
### <a name="incorrect-code-generation-when-passing-and-comparing-uint16-values"></a>Niepoprawna generacja kodu podczas przekazywania i porównywania wartości UInt16

#### <a name="details"></a>Szczegóły

Ze względu na zmiany wprowadzone w .NET Framework 4,7, w niektórych przypadkach kod wygenerowany przez kompilator JIT w aplikacjach uruchomionych na .NET Framework 4,7 niepoprawnie porównuje dwie <code>T:System.UInt16</code> wartości. Aby uzyskać więcej informacji, zobacz temat [#11508 problemu: ciche złe codegen podczas przekazywania i porównywania argumentów UShort](https://github.com/dotnet/coreclr/issues/11508) na GitHub.com.

#### <a name="suggestion"></a>Sugestia

Jeśli wystąpią problemy z porównaniem 16-bitowych wartości unsigned w .NET Framework 4,7, należy przeprowadzić uaktualnienie do .NET Framework 4.7.1.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4,7|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
