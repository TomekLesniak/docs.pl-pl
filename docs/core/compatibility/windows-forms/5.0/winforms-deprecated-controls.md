---
title: 'Nieprzerwana zmiana: Usunięto kontrolki paska stanu'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, w której niektóre kontrolki Windows Forms nie są już dostępne.
ms.date: 07/18/2020
ms.openlocfilehash: 70aaa20f3fee1f4c342c4d9e547b0658aaf533b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761608"
---
# <a name="removed-status-bar-controls"></a>Usunięto kontrolki paska stanu

Począwszy od platformy .NET 5,0, niektóre kontrolki Windows Forms nie są już dostępne.

## <a name="change-description"></a>Zmień opis

Począwszy od platformy .NET 5,0, niektóre kontrolki Windows Forms powiązane z paskiem stanu nie są już dostępne. Kontrolki zamiany, które mają lepszy projekt i pomoc techniczną, zostały wprowadzone w .NET Framework 2,0. Przestarzałe formanty zostały wcześniej usunięte z przyborników projektanta, ale były nadal dostępne do użycia. Teraz zostały całkowicie usunięte.

Następujące typy nie są już dostępne:

* `StatusBar`
* `StatusBarDrawItemEventArgs`
* `StatusBarDrawItemEventHandler`
* `StatusBarPanel`
* `StatusBarPanelAutoSize`
* `StatusBarPanelBorderStyle`
* `StatusBarPanelClickEventArgs`
* `StatusBarPanelClickEventHandler`
* `StatusBarPanelStyle`

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

Przejdź do zastępczych interfejsów API dla tych formantów i ich scenariuszy:

| Stara kontrolka (API) | Zalecane zastąpienie                          |
|-------------------|--------------------------------------------------|
| StatusBar         | <xref:System.Windows.Forms.StatusStrip>          |
| StatusBarPanel    | <xref:System.Windows.Forms.ToolStripStatusLabel> |

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Forms.StatusBar?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanel?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelAutoSize?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelBorderStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelStyle?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Windows.Forms.StatusBar`
- `T:System.Windows.Forms.StatusBarDrawItemEventArgs`
- `T:System.Windows.Forms.StatusBarDrawItemEventHandler`
- `T:System.Windows.Forms.StatusBarPanel`
- `T:System.Windows.Forms.StatusBarPanelAutoSize`
- `T:System.Windows.Forms.StatusBarPanelBorderStyle`
- `T:System.Windows.Forms.StatusBarPanelClickEventArgs`
- `T:System.Windows.Forms.StatusBarPanelClickEventHandler`
- `T:System.Windows.Forms.StatusBarPanelStyle`

### Category

Windows Forms

-->
