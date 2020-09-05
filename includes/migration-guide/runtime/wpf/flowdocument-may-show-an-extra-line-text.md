---
ms.openlocfilehash: a61005e317020c47a283dae292236624ec6057ce
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496312"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a><span data-ttu-id="1fb28-101">FlowDocument może wyświetlić dodatkowy wiersz tekstu</span><span class="sxs-lookup"><span data-stu-id="1fb28-101">FlowDocument may show an extra line of text</span></span>

#### <a name="details"></a><span data-ttu-id="1fb28-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="1fb28-102">Details</span></span>

<span data-ttu-id="1fb28-103">W niektórych przypadkach <xref:System.Windows.Documents.FlowDocument> element będzie wyświetlał dodatkowy wiersz tekstu podczas uruchamiania na .NET Framework 4,5 w porównaniu do sposobu, w jaki jest wyświetlany, gdy jest uruchamiany na .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="1fb28-103">In some cases, a <xref:System.Windows.Documents.FlowDocument> element will display an extra line of text when running on the .NET Framework 4.5 compared to how it displayed when run on the .NET Framework 4.0.</span></span> <span data-ttu-id="1fb28-104">Nie istnieją znane przypadki zmiany, które powodują słabą i nieillegibly tekstu, ale może to spowodować, że tekst jest wyświetlany wcześniej z <xref:System.Windows.Documents.FlowDocument> widoku.</span><span class="sxs-lookup"><span data-stu-id="1fb28-104">There are no known cases of the change causing any text to be displayed poorly or illegibly, but it could cause text to appear that previously was omitted from a <xref:System.Windows.Documents.FlowDocument>'s view.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1fb28-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="1fb28-105">Suggestion</span></span>

<span data-ttu-id="1fb28-106">W niektórych przypadkach zmniejszenie właściwości PageHeight elementu wyświetlanego przez jedną może przywrócić poprzednią liczbę wyświetlanych wierszy.</span><span class="sxs-lookup"><span data-stu-id="1fb28-106">In some cases, decreasing the display element's PageHeight property by one can restore the previous number of displayed lines.</span></span>

| <span data-ttu-id="1fb28-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="1fb28-107">Name</span></span>    | <span data-ttu-id="1fb28-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="1fb28-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1fb28-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="1fb28-109">Scope</span></span>   |<span data-ttu-id="1fb28-110">Edge</span><span class="sxs-lookup"><span data-stu-id="1fb28-110">Edge</span></span>|
|<span data-ttu-id="1fb28-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="1fb28-111">Version</span></span>|<span data-ttu-id="1fb28-112">4.5</span><span class="sxs-lookup"><span data-stu-id="1fb28-112">4.5</span></span>|
|<span data-ttu-id="1fb28-113">Typ</span><span class="sxs-lookup"><span data-stu-id="1fb28-113">Type</span></span>|<span data-ttu-id="1fb28-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="1fb28-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1fb28-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="1fb28-115">Affected APIs</span></span>

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
