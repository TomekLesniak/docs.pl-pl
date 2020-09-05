---
ms.openlocfilehash: 961ca545560a53fc2c1d52722b68ae460de66877
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496896"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a>DataGridCellsPanel. BringIndexIntoView zgłasza wyjątku ArgumentOutOfRangeException

#### <a name="details"></a>Szczegóły

<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> działa asynchronicznie, gdy Wirtualizacja kolumny jest włączona, ale szerokość kolumn nie została jeszcze ustalona.  Jeśli kolumny zostaną usunięte przed wykonaniem asynchronicznej pracy, <xref:System.ArgumentOutOfRangeException?displayProperty=fullName> może wystąpić.

#### <a name="suggestion"></a>Sugestia

Jeden z następujących elementów:<ol><li>Uaktualnij do .NET Framework 4,7.</li><li>Zainstaluj najnowszą poprawkę obsługi dla .NET Framework 4.6.2.</li><li>Należy unikać usuwania kolumn do momentu ukończenia asynchronicznej odpowiedzi <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> .</li></ol>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.6.2|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)`
- `M:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)`

-->
