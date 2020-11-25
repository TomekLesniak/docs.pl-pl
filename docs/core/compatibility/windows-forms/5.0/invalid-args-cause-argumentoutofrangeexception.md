---
title: 'Zmiana istotna: właściwości WinForms teraz generują wyjątku ArgumentOutOfRangeException'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, w której niektóre właściwości Windows Forms teraz zgłaszają wyjątku ArgumentOutOfRangeException dla nieprawidłowych argumentów.
ms.date: 06/18/2020
ms.openlocfilehash: 94593047d16304ce401b23993ad4ca173c10812b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761587"
---
# <a name="winforms-properties-now-throw-argumentoutofrangeexception"></a>Właściwości WinForms teraz generują wyjątku ArgumentOutOfRangeException

Niektóre właściwości Windows Forms teraz zwracają <xref:System.ArgumentOutOfRangeException> dla nieprawidłowych argumentów, w których wcześniej nie zostały.

## <a name="change-description"></a>Zmień opis

Wcześniej te właściwości spowodowały różne wyjątki, takie jak <xref:System.NullReferenceException> , <xref:System.IndexOutOfRangeException> , lub <xref:System.ArgumentException> , gdy przekazane są argumenty poza zakresem. Począwszy od platformy .NET 5,0, te właściwości generują teraz, <xref:System.ArgumentOutOfRangeException> gdy przekazane argumenty są poza zakresem.

Zgłaszanie jest <xref:System.ArgumentOutOfRangeException> zgodne z zachowaniem środowiska uruchomieniowego .NET. Usprawnia to również środowisko debugowania, przez co jasno komunikuje się, który argument jest nieprawidłowy.

## <a name="version-introduced"></a>Wprowadzona wersja

.NET 5,0

## <a name="recommended-action"></a>Zalecana akcja

- Zaktualizuj kod, aby zapobiec przekazywaniu nieprawidłowych argumentów.
- Jeśli to konieczne, należy obsłużyć <xref:System.ArgumentOutOfRangeException> podczas ustawiania właściwości.

## <a name="affected-apis"></a>Dotyczy interfejsów API

W poniższej tabeli wymieniono odpowiednie właściwości i parametry:

> [!div class="mx-tdBreakAll"]
> | Właściwość | Nazwa parametru | Dodana wersja |
> |-|-|-|
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)?displayProperty=nameWithType> | `index` | 5,0 wersja zapoznawcza 5 |
> | <xref:System.Windows.Forms.TreeNode.ImageIndex?displayProperty=nameWithType> | `value` | 5,0 wersja zapoznawcza 6 |
> | <xref:System.Windows.Forms.TreeNode.SelectedImageIndex?displayProperty=nameWithType> | `value` | 5,0 wersja zapoznawcza 6 |

<!--

### Affected APIs

- `P:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)`
- `P:System.Windows.Forms.TreeNode.ImageIndex`
- `P:System.Windows.Forms.TreeNode.SelectedImageIndex`

### Category

Windows Forms

-->
