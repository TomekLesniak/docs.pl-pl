---
ms.openlocfilehash: c01705002ad87a12389078d75ffd0f91f934d36e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497814"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>Zaznaczony tekst pola tekstowego WPF jest wyświetlany w innym kolorze, gdy pole tekstowe jest nieaktywne

#### <a name="details"></a>Szczegóły

W .NET Framework 4,5, gdy kontrolka pola tekstowego WPF jest nieaktywna (nie ma fokusu), zaznaczony tekst wewnątrz pola będzie wyglądać inaczej, niż w przypadku, gdy formant jest aktywny.

#### <a name="suggestion"></a>Sugestia

Zachowanie poprzedniego (.NET Framework 4,0) może zostać przywrócone przez ustawienie <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> właściwości na <code>false</code> .

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
