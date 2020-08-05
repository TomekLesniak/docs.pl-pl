---
ms.openlocfilehash: e10b5168d59edd56ff549a3a1e3a09d023fe5e28
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556231"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>Nieobsługiwany przełącznik zgodności DoNotLoadLatestRichEditControl

`Switch.System.Windows.Forms.UseLegacyImages`Przełącznik zgodności, który został wprowadzony w .NET Framework 4.7.1, nie jest obsługiwany w Windows Forms na platformie .NET Core lub .net 5,0 i nowszych.

#### <a name="change-description"></a>Zmień opis

W .NET Framework 4.6.2 i poprzednich wersjach <xref:System.Windows.Forms.RichTextBox> kontrolka tworzy wystąpienie elementu Win32 RichEdit Control v 3.0 i dla aplikacji, które są przeznaczone dla .NET Framework 4.7.1, <xref:System.Windows.Forms.RichTextBox> formant tworzy wystąpienie elementu RichEdit v 4.1 (w *msftedit.dll*). `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl`Wprowadzono przełącznik zgodności, aby umożliwić aplikacjom, które są przeznaczone .NET Framework 4.7.1 i nowsze wersje, aby zrezygnować z nowej kontrolki RichEdit v 4.1 i zamiast tego używać starego formantu RichEdit v3.

W przypadku oprogramowania .NET Core i .NET 5,0 i nowszych wersji `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` przełącznik nie jest obsługiwany. Obsługiwane są tylko nowe wersje <xref:System.Windows.Forms.RichTextBox> formantu.

#### <a name="version-introduced"></a>Wprowadzona wersja

3.0

#### <a name="recommended-action"></a>Zalecana akcja

Usuń przełącznik. Przełącznik nie jest obsługiwany i żadna alternatywna funkcja nie jest dostępna.

#### <a name="category"></a>Kategoria

Windows Forms

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

#### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
