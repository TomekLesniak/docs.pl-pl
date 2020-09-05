---
ms.openlocfilehash: 9d960774161fc44810f90ca30f56eb98f98de3ff
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496666"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a>Wartość pola tekstowego WPF jest domyślna dla limitu cofania 100

#### <a name="details"></a>Szczegóły

W .NET Framework 4,5 domyślny limit cofania dla pola tekstowego WPF to 100 (w przeciwieństwie do nieograniczonego w .NET Framework 4,0)

#### <a name="suggestion"></a>Sugestia

Jeśli limit cofania wynoszący 100 jest zbyt niski, limit może być jawnie ustawiony z <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.TextBox`

-->
