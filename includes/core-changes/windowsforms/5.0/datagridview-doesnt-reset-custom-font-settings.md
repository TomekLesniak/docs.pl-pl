---
ms.openlocfilehash: 9c84c9f844a2a7efb9633c11634b069ef6b6033b
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804868"
---
### <a name="datagridview-no-longer-resets-fonts-for-customized-cell-styles"></a>Formant DataGridView nie jest już resetowany czcionek dla niestandardowych stylów komórek

Gdy czcionka otoczenia ulegnie zmianie, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> nie jest już resetowane domyślne czcionki stylu komórki, aby pasowała do czcionki otaczającej, Jeśli czcionka stylu komórki została dostosowana.

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach .NET, Jeśli czcionka otoczenia ulegnie zmianie, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> resetuje i przesłania czcionki zdefiniowane przez użytkownika we <xref:System.Windows.Forms.DataGridView.DefaultCellStyle> <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> właściwościach, i <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> .

Począwszy od programu .NET 5,0, w przypadku konfigurowania ustawień czcionki we <xref:System.Windows.Forms.DataGridView.DefaultCellStyle> <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> właściwościach, lub, <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> te ustawienia są zachowywane nawet wtedy, gdy zmieni się czcionka otoczenia. Dla każdej z tych właściwości, które nie dostosowuje czcionki, czcionka zmieni się w celu dopasowania do ustawień czcionki otoczenia.

#### <a name="reason-for-change"></a>Przyczyna zmiany

[Zmiana domyślnej czcionki w programie .NET Core 3,0](../../../../docs/core/compatibility/winforms.md#default-control-font-changed-to-segoe-ui-9-pt)powoduje zmianę domyślnych ustawień czcionki dla różnych stylów komórek. Takie zachowanie jest niepożądane w przypadku aplikacji korzystających z niestandardowych stylów w swoich <xref:System.Windows.Forms.DataGridViewElement.DataGridView> kontrolkach i utrudniają migrację tych aplikacji z .NET Framework do programu .net 5,0.

#### <a name="version-introduced"></a>Wprowadzona wersja

.NET 5,0 RC2

#### <a name="recommended-action"></a>Zalecana akcja

W Twojej części nie jest wymagana żadna akcja. Jednakże jeśli dostosowano czcionkę we <xref:System.Windows.Forms.DataGridView.DefaultCellStyle> <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> właściwościach,, lub, <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> chcesz dopasować czcionkę do otaczającej czcionki, ustaw <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> `null` dla każdej właściwości.

#### <a name="category"></a>Kategoria

- Windows Forms

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Windows.Forms.DataGridView.DefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle`

-->
