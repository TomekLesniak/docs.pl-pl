---
ms.openlocfilehash: 1487e32ffca7b4bbebb5edac7efc8961ac05723b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497102"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a>Dostęp do wybranych elementów programu WPF DataGrid z procedury obsługi zdarzenia UnloadingRow elementu DataGrid może spowodować wystąpienie elementu NullReferenceException

#### <a name="details"></a>Szczegóły

Ze względu na usterkę w .NET Framework 4,5, obsługa zdarzeń dla <xref:System.Windows.Controls.DataGrid> zdarzeń obejmujących usunięcie wiersza może spowodować, że <xref:System.NullReferenceException?displayProperty=fullName> zostanie wygenerowany, jeśli uzyskują dostęp do <xref:System.Windows.Controls.DataGrid> <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> właściwości lub <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> .

#### <a name="suggestion"></a>Sugestia

Ten problem został rozwiązany w .NET Framework 4,6 i może zostać rozwiązany przez uaktualnienie do tej wersji .NET Framework.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType>

<!--

#### Affected APIs

- `E:System.Windows.Controls.DataGrid.UnloadingRow`
- `E:System.Windows.Controls.DataGrid.UnloadingRowDetails`

-->
