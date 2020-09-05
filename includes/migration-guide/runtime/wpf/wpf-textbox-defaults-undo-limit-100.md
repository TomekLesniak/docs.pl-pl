---
ms.openlocfilehash: 9d960774161fc44810f90ca30f56eb98f98de3ff
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496666"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="5562f-101">Wartość pola tekstowego WPF jest domyślna dla limitu cofania 100</span><span class="sxs-lookup"><span data-stu-id="5562f-101">WPF TextBox defaults to undo limit of 100</span></span>

#### <a name="details"></a><span data-ttu-id="5562f-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="5562f-102">Details</span></span>

<span data-ttu-id="5562f-103">W .NET Framework 4,5 domyślny limit cofania dla pola tekstowego WPF to 100 (w przeciwieństwie do nieograniczonego w .NET Framework 4,0)</span><span class="sxs-lookup"><span data-stu-id="5562f-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5562f-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="5562f-104">Suggestion</span></span>

<span data-ttu-id="5562f-105">Jeśli limit cofania wynoszący 100 jest zbyt niski, limit może być jawnie ustawiony z <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span><span class="sxs-lookup"><span data-stu-id="5562f-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>

| <span data-ttu-id="5562f-106">Nazwa</span><span class="sxs-lookup"><span data-stu-id="5562f-106">Name</span></span>    | <span data-ttu-id="5562f-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="5562f-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5562f-108">Zakres</span><span class="sxs-lookup"><span data-stu-id="5562f-108">Scope</span></span>   |<span data-ttu-id="5562f-109">Edge</span><span class="sxs-lookup"><span data-stu-id="5562f-109">Edge</span></span>|
|<span data-ttu-id="5562f-110">Wersja</span><span class="sxs-lookup"><span data-stu-id="5562f-110">Version</span></span>|<span data-ttu-id="5562f-111">4.5</span><span class="sxs-lookup"><span data-stu-id="5562f-111">4.5</span></span>|
|<span data-ttu-id="5562f-112">Typ</span><span class="sxs-lookup"><span data-stu-id="5562f-112">Type</span></span>|<span data-ttu-id="5562f-113">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="5562f-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="5562f-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="5562f-114">Affected APIs</span></span>

- <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.TextBox`

-->
