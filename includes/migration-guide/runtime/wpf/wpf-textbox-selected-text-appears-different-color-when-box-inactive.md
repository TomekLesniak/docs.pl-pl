---
ms.openlocfilehash: c01705002ad87a12389078d75ffd0f91f934d36e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497814"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="9e970-101">Zaznaczony tekst pola tekstowego WPF jest wyświetlany w innym kolorze, gdy pole tekstowe jest nieaktywne</span><span class="sxs-lookup"><span data-stu-id="9e970-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

#### <a name="details"></a><span data-ttu-id="9e970-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="9e970-102">Details</span></span>

<span data-ttu-id="9e970-103">W .NET Framework 4,5, gdy kontrolka pola tekstowego WPF jest nieaktywna (nie ma fokusu), zaznaczony tekst wewnątrz pola będzie wyglądać inaczej, niż w przypadku, gdy formant jest aktywny.</span><span class="sxs-lookup"><span data-stu-id="9e970-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9e970-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="9e970-104">Suggestion</span></span>

<span data-ttu-id="9e970-105">Zachowanie poprzedniego (.NET Framework 4,0) może zostać przywrócone przez ustawienie <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> właściwości na <code>false</code> .</span><span class="sxs-lookup"><span data-stu-id="9e970-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>

| <span data-ttu-id="9e970-106">Nazwa</span><span class="sxs-lookup"><span data-stu-id="9e970-106">Name</span></span>    | <span data-ttu-id="9e970-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="9e970-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9e970-108">Zakres</span><span class="sxs-lookup"><span data-stu-id="9e970-108">Scope</span></span>   |<span data-ttu-id="9e970-109">Edge</span><span class="sxs-lookup"><span data-stu-id="9e970-109">Edge</span></span>|
|<span data-ttu-id="9e970-110">Wersja</span><span class="sxs-lookup"><span data-stu-id="9e970-110">Version</span></span>|<span data-ttu-id="9e970-111">4.5</span><span class="sxs-lookup"><span data-stu-id="9e970-111">4.5</span></span>|
|<span data-ttu-id="9e970-112">Typ</span><span class="sxs-lookup"><span data-stu-id="9e970-112">Type</span></span>|<span data-ttu-id="9e970-113">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="9e970-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="9e970-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="9e970-114">Affected APIs</span></span>

- <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.TextBox`

-->
