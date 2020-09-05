---
ms.openlocfilehash: c4a3d903894027a01d32ca132d1233da9d9c3ee5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496590"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>PreviewLostKeyboardFocus jest wywoływana wielokrotnie, jeśli jej program obsługi wyświetli okno komunikatu Windows Forms

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4,5, wywołanie <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> z <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> programu obsługi spowoduje ponowne uruchomienie programu obsługi po zamknięciu okna komunikatu, co może spowodować powstanie nieskończonej pętli okien komunikatów.

#### <a name="suggestion"></a>Sugestia

Istnieją dwie opcje obejścia tego problemu:<ol><li>Można to uniknąć, wywołując <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> zamiast <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> .</li><li>Można to uniknąć, wyświetlając okno komunikatu z <xref:System.Windows.UIElement.LostKeyboardFocus> programu obsługi zdarzeń (w przeciwieństwie do <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName> programu obsługi zdarzeń).</li></ol>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType>

<!--

#### Affected APIs

- `E:System.Windows.ContentElement.PreviewLostKeyboardFocus`
- `E:System.Windows.IInputElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement3D.PreviewLostKeyboardFocus`

-->
