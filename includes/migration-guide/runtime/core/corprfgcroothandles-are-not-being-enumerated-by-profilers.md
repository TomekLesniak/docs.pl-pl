---
ms.openlocfilehash: 25437dcc0c814ed2265b2efb34316af48b372ebd
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497540"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a>COR_PRF_GC_ROOT_HANDLEs nie są wyliczane przez program do plików

#### <a name="details"></a>Szczegóły

W .NET Framework v 4.5.1 interfejs API profilowania <code>RootReferences2()</code> jest niepoprawnie nigdy nie zwraca <code>COR_PRF_GC_ROOT_HANDLE</code> (są zwracane jako <code>COR_PRF_GC_ROOT_OTHER</code> zamiast). Ten problem został rozwiązany, rozpoczynając od .NET Framework 4,6.

#### <a name="suggestion"></a>Sugestia

Ten problem został rozwiązany w .NET Framework 4,6 i może zostać rozwiązany przez uaktualnienie do tej wersji .NET Framework.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5.1|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
