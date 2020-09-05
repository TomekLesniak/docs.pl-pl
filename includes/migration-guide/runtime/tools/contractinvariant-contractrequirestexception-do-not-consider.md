---
ms.openlocfilehash: 17fde81f9734966692c9f41d2213f8682dedea46
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496509"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a>Contract. Invariant lub Contract. wymaga, \<TException> aby nie brać pod uwagę ciągu. IsNullOrEmpty jako czysty

#### <a name="details"></a>Szczegóły

W przypadku aplikacji, które są przeznaczone dla .NET Framework 4.6.1, jeśli kontrakt niezmienny dla <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> lub kontrakt warunku wstępnego dla <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> wywołania <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> metody, nastąpi emituje Ostrzeżenie kompilatora CC1036: &quot; wykryto wywołanie metody "System. String. IsNullOrWhteSpace (System. String)" bez [czysty] w metodzie. &quot; Jest to ostrzeżenie kompilatora, a nie błąd kompilatora.

#### <a name="suggestion"></a>Sugestia

To zachowanie zostało opisane w [#339 problemu](https://github.com/Microsoft/CodeContracts/issues/339)w usłudze GitHub. Aby wyeliminować to ostrzeżenie, można pobrać i skompilować zaktualizowaną wersję kodu źródłowego dla narzędzia kontrakty kodu z usługi [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md). Informacje na temat pobierania znajdują się u dołu strony.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.6.1|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)`
- `M:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)`

-->
