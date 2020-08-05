---
ms.openlocfilehash: 3db4b0b42a154c5bc9296889ae9dc4b7ecf1e58e
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556232"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="4debd-101">Nieobsługiwany przełącznik zgodności AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="4debd-101">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="4debd-102">`Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls`Przełącznik zgodności jest obsługiwany w Windows Forms na .NET Framework 4,6 i nowszych wersjach, ale nie jest obsługiwany w przypadku platformy .NET Core lub .net 5,0 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="4debd-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="4debd-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="4debd-103">Change description</span></span>

<span data-ttu-id="4debd-104">W .NET Framework 4,6 i nowszych wersjach, wybranie karty zmienia kolejność kolekcji kontrolek.</span><span class="sxs-lookup"><span data-stu-id="4debd-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="4debd-105">`Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls`Przełącznik zgodności pozwala aplikacji pominąć tę zmianę kolejności, jeśli to zachowanie jest niepożądane.</span><span class="sxs-lookup"><span data-stu-id="4debd-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="4debd-106">W przypadku programów .NET Core i .NET 5,0 i nowszych `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` przełącznik nie jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="4debd-106">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4debd-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="4debd-107">Version introduced</span></span>

<span data-ttu-id="4debd-108">3.0</span><span class="sxs-lookup"><span data-stu-id="4debd-108">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4debd-109">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="4debd-109">Recommended action</span></span>

<span data-ttu-id="4debd-110">Usuń przełącznik.</span><span class="sxs-lookup"><span data-stu-id="4debd-110">Remove the switch.</span></span> <span data-ttu-id="4debd-111">Przełącznik nie jest obsługiwany i żadna alternatywna funkcja nie jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="4debd-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="4debd-112">Kategoria</span><span class="sxs-lookup"><span data-stu-id="4debd-112">Category</span></span>

<span data-ttu-id="4debd-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4debd-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4debd-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="4debd-114">Affected APIs</span></span>

- <span data-ttu-id="4debd-115">Brak</span><span class="sxs-lookup"><span data-stu-id="4debd-115">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
