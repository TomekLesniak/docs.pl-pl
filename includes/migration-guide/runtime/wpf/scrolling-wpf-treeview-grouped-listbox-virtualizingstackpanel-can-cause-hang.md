---
ms.openlocfilehash: 31ada197db36be192317e32a37a353d375d9cc65
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496527"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>Przewijanie drzewa WPF lub zgrupowane pole listy w VirtualizingStackPanel może spowodować zawieszenie

#### <a name="details"></a>Szczegóły

W .NET Framework v 4.5, przewinięcie WPF <xref:System.Windows.Controls.TreeView?displayProperty=fullName> w zwirtualizowanym panelu stosu może spowodować zawieszenie, jeśli w okienku ekranu pojawią się marginesy (między elementami na <xref:System.Windows.Controls.TreeView?displayProperty=fullName> przykład lub w elemencie ItemsPresenter). Ponadto w niektórych przypadkach różne elementy w widoku mogą spowodować niestabilność nawet wtedy, gdy nie ma marginesów.

#### <a name="suggestion"></a>Sugestia

Tę usterkę można uniknąć przez uaktualnienie do .NET Framework 4.5.1. Alternatywnie marginesy mogą być usuwane z kolekcji widoku (na przykład <xref:System.Windows.Controls.TreeView?displayProperty=fullName> s) w zwirtualizowanych panelach stosu, jeśli wszystkie zawarte elementy mają ten sam rozmiar.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Duży|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)`

-->
