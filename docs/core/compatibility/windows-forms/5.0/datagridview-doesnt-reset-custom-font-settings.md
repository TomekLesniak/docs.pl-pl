---
title: 'Nieprzerwana zmiana: formant DataGridView nie ustawia już czcionek dla dostosowanych stylów komórek'
description: Zapoznaj się z istotną zmianą w programie .NET 5,0, gdzie formant DataGridView nie resetuje domyślnych czcionek stylu komórki, aby pasowały do czcionki otaczającej, Jeśli czcionka stylu komórki została dostosowana.
ms.date: 10/18/2020
ms.openlocfilehash: 708b12ba1305681f5c38eb605861d02e3b2c8eb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761721"
---
# <a name="datagridview-no-longer-resets-fonts-for-customized-cell-styles"></a>Formant DataGridView nie jest już resetowany czcionek dla niestandardowych stylów komórek

Gdy czcionka otoczenia ulegnie zmianie, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> nie jest już resetowane domyślne czcionki stylu komórki, aby pasowała do czcionki otaczającej, Jeśli czcionka stylu komórki została dostosowana.

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach .NET, Jeśli czcionka otoczenia ulegnie zmianie, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> resetuje i przesłania czcionki zdefiniowane przez użytkownika we <xref:System.Windows.Forms.DataGridView.DefaultCellStyle> <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> właściwościach, i <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> .

Począwszy od programu .NET 5,0, w przypadku konfigurowania ustawień czcionki we <xref:System.Windows.Forms.DataGridView.DefaultCellStyle> <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> właściwościach, lub, <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> te ustawienia są zachowywane nawet wtedy, gdy zmieni się czcionka otoczenia. Dla każdej z tych właściwości, które nie dostosowuje czcionki, czcionka zmieni się w celu dopasowania do ustawień czcionki otoczenia.

## <a name="reason-for-change"></a>Przyczyna zmiany

[Zmiana domyślnej czcionki w programie .NET Core 3,0](../../winforms.md#default-control-font-changed-to-segoe-ui-9-pt)powoduje zmianę domyślnych ustawień czcionki dla różnych stylów komórek. Takie zachowanie jest niepożądane w przypadku aplikacji korzystających z niestandardowych stylów w swoich <xref:System.Windows.Forms.DataGridViewElement.DataGridView> kontrolkach i utrudniają migrację tych aplikacji z .NET Framework do programu .net 5,0.

## <a name="version-introduced"></a>Wprowadzona wersja

.NET 5,0

## <a name="recommended-action"></a>Zalecana akcja

W Twojej części nie jest wymagana żadna akcja. Jednakże jeśli dostosowano czcionkę we <xref:System.Windows.Forms.DataGridView.DefaultCellStyle> <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> właściwościach,, lub, <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> chcesz dopasować czcionkę do otaczającej czcionki, ustaw <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> `null` dla każdej właściwości.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Windows.Forms.DataGridView.DefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle`

### Category

- Windows Forms

-->
