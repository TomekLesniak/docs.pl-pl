---
ms.openlocfilehash: 196a26bd235e5e2556baa7fac979b3316ff81e1f
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556223"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="b4280-101">Nieobsługiwany przełącznik zgodności EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="b4280-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="b4280-102">`Switch.System.Windows.Forms.EnableVisualStyleValidation`Przełącznik zgodności nie jest obsługiwany w Windows Forms na platformie .NET Core lub .net 5,0 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="b4280-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b4280-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="b4280-103">Change description</span></span>

<span data-ttu-id="b4280-104">W .NET Framework `Switch.System.Windows.Forms.EnableVisualStyleValidation` przełącznik zgodności zezwala aplikacji na rezygnację z walidacji stylów wizualnych dostarczonych w postaci liczbowej.</span><span class="sxs-lookup"><span data-stu-id="b4280-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="b4280-105">W przypadku programów .NET Core i .NET 5,0 i nowszych `Switch.System.Windows.Forms.EnableVisualStyleValidation` przełącznik nie jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="b4280-105">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b4280-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="b4280-106">Version introduced</span></span>

<span data-ttu-id="b4280-107">3.0</span><span class="sxs-lookup"><span data-stu-id="b4280-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b4280-108">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="b4280-108">Recommended action</span></span>

<span data-ttu-id="b4280-109">Usuń przełącznik.</span><span class="sxs-lookup"><span data-stu-id="b4280-109">Remove the switch.</span></span> <span data-ttu-id="b4280-110">Przełącznik nie jest obsługiwany i żadna alternatywna funkcja nie jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="b4280-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="b4280-111">Kategoria</span><span class="sxs-lookup"><span data-stu-id="b4280-111">Category</span></span>

<span data-ttu-id="b4280-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b4280-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b4280-113">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="b4280-113">Affected APIs</span></span>

- <span data-ttu-id="b4280-114">Brak</span><span class="sxs-lookup"><span data-stu-id="b4280-114">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
