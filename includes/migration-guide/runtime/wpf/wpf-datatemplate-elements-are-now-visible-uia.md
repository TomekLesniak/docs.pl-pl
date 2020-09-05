---
ms.openlocfilehash: 4394e69dafeb6cce2d7719a67bbce396d3bc1086
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496915"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a>Elementy DataTemplate WPF są teraz widoczne dla UIA

#### <a name="details"></a>Szczegóły

Wcześniej <xref:System.Windows.DataTemplate?displayProperty=fullName> elementy były niewidoczne dla automatyzacji interfejsu użytkownika. Począwszy od 4,5, Automatyzacja interfejsu użytkownika będzie wykrywać te elementy. Jest to przydatne w wielu przypadkach, ale może przerwać testy, które są zależne od drzew UIA, które nie zawierają <xref:System.Windows.DataTemplate?displayProperty=fullName> elementów.

#### <a name="suggestion"></a>Sugestia

Testy automatyzacji interfejsu użytkownika dla tej aplikacji mogą wymagać aktualizacji do konta dla drzewa UIA teraz, łącznie z wcześniej niewidocznymi <xref:System.Windows.DataTemplate?displayProperty=fullName> elementami. Na przykład testy, które oczekują, że niektóre elementy powinny znajdować się obok siebie, mogą teraz oczekiwać, że wcześniej niewidoczne elementy UIA między. Testy, które opierają się na określonych licznikach lub indeksach dla elementów UIA, mogą wymagać aktualizacji z nowymi wartościami.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.DataTemplate.%23ctor>
- <xref:System.Windows.DataTemplate.%23ctor(System.Object)>

<!--

#### Affected APIs

- `M:System.Windows.DataTemplate.#ctor`
- `M:System.Windows.DataTemplate.#ctor(System.Object)`

-->
