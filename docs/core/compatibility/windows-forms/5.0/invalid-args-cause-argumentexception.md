---
title: 'Zmiana istotna: metody WinForms teraz generują ArgumentException'
description: Dowiedz się więcej o istotnej zmianie w programie .NET 5,0, gdzie metody sWindows Forms teraz generują ArgumentException dla nieprawidłowych argumentów.
ms.date: 07/18/2020
ms.openlocfilehash: 46fe3f3b1208a5cd676e1b7546507bed36a850f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761716"
---
# <a name="winforms-methods-now-throw-argumentexception"></a>Metody WinForms teraz generują ArgumentException

Niektóre metody Windows Forms teraz generują <xref:System.ArgumentException> dla nieprawidłowych argumentów, w których wcześniej nie zostały.

## <a name="change-description"></a>Zmień opis

Wcześniej przekazywanie argumentów nieoczekiwanego lub nieprawidłowego typu do określonych metod Windows Forms spowoduje nieokreślony stan. Począwszy od platformy .NET 5,0, metody te generują teraz, <xref:System.ArgumentException> gdy przekazane nieprawidłowe argumenty.

Zgłaszanie jest <xref:System.ArgumentException> zgodne z zachowaniem środowiska uruchomieniowego .NET. Usprawnia to również środowisko debugowania, przez co jasno komunikuje się, który argument jest nieprawidłowy.

## <a name="version-introduced"></a>Wprowadzona wersja

.NET 5,0

## <a name="recommended-action"></a>Zalecana akcja

- Zaktualizuj kod, aby zapobiec przekazywaniu nieprawidłowych argumentów.
- W razie potrzeby dojście do <xref:System.ArgumentException> wywołania metody.

## <a name="affected-apis"></a>Dotyczy interfejsów API

Poniższa tabela zawiera listę odpowiednich metod i parametrów:

| Metoda | Nazwa parametru | Warunek | Dodana wersja |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | Argument nie jest typu <xref:System.Windows.Forms.TabPage> . | Wersja zapoznawcza 1 |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | Argument to `null` , <xref:System.String.Empty?displayProperty=nameWithType> lub biały znak. | Wersja zapoznawcza 5 |
| <xref:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)> | `culture` | Nie można pobrać elementu `InputLanguage` dla określonej kultury. | Wersja zapoznawcza 7 |

<!--

### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`
- `M:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)`

### Category

Windows Forms

-->
