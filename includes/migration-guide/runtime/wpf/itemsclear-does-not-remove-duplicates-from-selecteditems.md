---
ms.openlocfilehash: 25ce391f917bd270d4d9a75f608e4a8ec763d15c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496910"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a>Elementy. Clear nie usuwa duplikatów z SelectedItems

#### <a name="details"></a>Szczegóły

Załóżmy, że selektor (z włączoną obsługą wielu zaznaczeń) ma duplikaty w <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> kolekcji — ten sam element występuje więcej niż jeden raz.  Usunięcie tych elementów ze źródła danych (np. przez wywoływanie elementów. Clear) nie powiodło się usunięcie ich z <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> ; tylko pierwsze wystąpienie zostanie usunięte. Ponadto kolejne użycie <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (np. SelectedItems. Clear ()) może napotkać problemy, takie jak <xref:System.ArgumentException?displayProperty=fullName> , ponieważ <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> zawiera elementy, które nie znajdują się już w źródle danych.

#### <a name="suggestion"></a>Sugestia

Uaktualnij, jeśli to możliwe, aby .NET Framework 4.6.2.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.MultiSelector.SelectedItems`

-->
