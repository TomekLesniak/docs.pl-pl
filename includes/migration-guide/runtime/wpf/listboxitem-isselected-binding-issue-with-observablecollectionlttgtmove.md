---
ms.openlocfilehash: 196b6a13d32c7767b858d6d68ca775eb49324805
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497106"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a>Problem z powiązaniem IsSelected ListBoxItem z ObservableCollection &lt; T &gt; . Przenieś

#### <a name="details"></a>Szczegóły

Wywołanie <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> lub <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> w kolekcji powiązanej <xref:System.Windows.Controls.ListBox?displayProperty=fullName> z zaznaczonymi elementami może prowadzić do nieprawidłowych zachowań z przyszłym wyborem lub usunięciem zaznaczenia <xref:System.Windows.Controls.ListBox?displayProperty=fullName> elementów.

#### <a name="suggestion"></a>Sugestia

Wywołanie <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> i <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> zamiast obejścia <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> tego problemu. Alternatywnie ten problem został rozwiązany w .NET Framework 4,6 i może zostać rozwiązany przez uaktualnienie do tej wersji .NET Framework.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.ObjectModel.ObservableCollection`1.Move(System.Int32,System.Int32)``
- ``M:System.Collections.ObjectModel.ObservableCollection`1.MoveItem(System.Int32,System.Int32)``

-->
