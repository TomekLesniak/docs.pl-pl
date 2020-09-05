---
ms.openlocfilehash: a61005e317020c47a283dae292236624ec6057ce
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496312"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a>FlowDocument może wyświetlić dodatkowy wiersz tekstu

#### <a name="details"></a>Szczegóły

W niektórych przypadkach <xref:System.Windows.Documents.FlowDocument> element będzie wyświetlał dodatkowy wiersz tekstu podczas uruchamiania na .NET Framework 4,5 w porównaniu do sposobu, w jaki jest wyświetlany, gdy jest uruchamiany na .NET Framework 4,0. Nie istnieją znane przypadki zmiany, które powodują słabą i nieillegibly tekstu, ale może to spowodować, że tekst jest wyświetlany wcześniej z <xref:System.Windows.Documents.FlowDocument> widoku.

#### <a name="suggestion"></a>Sugestia

W niektórych przypadkach zmniejszenie właściwości PageHeight elementu wyświetlanego przez jedną może przywrócić poprzednią liczbę wyświetlanych wierszy.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Documents.FlowDocument.%23ctor>
- <xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)>
- <xref:System.Windows.Controls.FlowDocumentReader.%23ctor>
- <xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor>
- <xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor>

<!--

#### Affected APIs

- `M:System.Windows.Documents.FlowDocument.#ctor`
- `M:System.Windows.Documents.FlowDocument.#ctor(System.Windows.Documents.Block)`
- `M:System.Windows.Controls.FlowDocumentReader.#ctor`
- `M:System.Windows.Controls.FlowDocumentPageViewer.#ctor`
- `M:System.Windows.Controls.Primitives.DocumentPageView.#ctor`

-->
