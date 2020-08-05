---
ms.openlocfilehash: 3fb8807a9b6f0bb0d2bc746f5e89eaa8a81d6aa8
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556248"
---
### <a name="donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a>Nieobsługiwany przełącznik zgodności DoNotSupportSelectAllShortcutInMultilineTextBox

`Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox`Przełącznik zgodności, który został wprowadzony w .NET Framework 4.6.1, nie jest obsługiwany w Windows Forms na platformie .NET Core i .net 5,0 i nowszych.

#### <a name="change-description"></a>Zmień opis

Rozpoczynając od .NET Framework 4.6.1, wybierając klawisz <kbd>Ctrl</kbd>  +  <kbd>a</kbd> skrótu w <xref:System.Windows.Forms.TextBox> kontrolce zaznacz wszystkie teksty. W .NET Framework 4,6 i poprzednich wersjach, wybranie <kbd>Ctrl</kbd>  +  <kbd>A</kbd> klawisza skrótu Ctrl nie zakończyło się niepowodzeniem, aby zaznaczyć cały tekst, jeśli właściwość [TextBox. ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) i <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> właściwości zostały ustawione na `true` . `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox`Przełącznik zgodności został wprowadzony w .NET Framework 4.6.1, aby zachować oryginalne zachowanie. Aby uzyskać więcej informacji, zobacz <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.

W przypadku oprogramowania .NET Core i .NET 5,0 i nowszych wersji `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` przełącznik nie jest obsługiwany.

#### <a name="version-introduced"></a>Wprowadzona wersja

3.0

#### <a name="recommended-action"></a>Zalecana akcja

Usuń przełącznik. Przełącznik nie jest obsługiwany i żadna alternatywna funkcja nie jest dostępna.

#### <a name="category"></a>Kategoria

Windows Forms

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- Brak

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
