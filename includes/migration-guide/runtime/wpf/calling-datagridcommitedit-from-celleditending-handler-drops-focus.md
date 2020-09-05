---
ms.openlocfilehash: c78122a2fe69c78625d6cb7fa9ddf41c49c2e737
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497449"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>Wywołanie elementu DataGrid. CommitEdit z obsługi CellEditEnding powoduje odrzucenie fokusu

#### <a name="details"></a>Szczegóły

Wywołanie <xref:System.Windows.Controls.DataGrid.CommitEdit> z jednego z <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> programów obsługi zdarzeń powoduje <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> utratę fokusu.

#### <a name="suggestion"></a>Sugestia

Ta usterka została rozwiązana w .NET Framework 4.5.2, dlatego można ją uniknąć, uaktualniając .NET Framework. Alternatywnie można to uniknąć przez jawne ponowne wybranie polecenia <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> po wywołaniu <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName> .

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.CommitEdit`
- `M:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)`

-->
