---
ms.openlocfilehash: 4d479636f41095610eaf39f92ad0dad4863ab8b5
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216355"
---
### <a name="typedescriptionproviderattribute-moved-to-another-assembly"></a><span data-ttu-id="a20e7-101">TypeDescriptionProviderAttribute przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="a20e7-101">TypeDescriptionProviderAttribute moved to another assembly</span></span>

<span data-ttu-id="a20e7-102"><xref:System.ComponentModel.TypeDescriptionProviderAttribute> Klasa została przeniesiona.</span><span class="sxs-lookup"><span data-stu-id="a20e7-102">The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a20e7-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="a20e7-103">Change description</span></span>

<span data-ttu-id="a20e7-104">W programie .NET Core 2,2 i starszych wersjach <xref:System.ComponentModel.TypeDescriptionProviderAttribute> Klasa jest dostępna w zestawie *System. ComponentModel. TypeConverter* .</span><span class="sxs-lookup"><span data-stu-id="a20e7-104">In .NET Core 2.2 and earlier versions, The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="a20e7-105">Począwszy od platformy .NET Core 3,0, znajduje się on w zestawie *System. ObjectModel* .</span><span class="sxs-lookup"><span data-stu-id="a20e7-105">Starting with .NET Core 3.0, it is found in the *System.ObjectModel* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a20e7-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="a20e7-106">Version introduced</span></span>

<span data-ttu-id="a20e7-107">3.0</span><span class="sxs-lookup"><span data-stu-id="a20e7-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a20e7-108">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="a20e7-108">Recommended action</span></span>

<span data-ttu-id="a20e7-109">Ta zmiana dotyczy tylko aplikacji, które używają odbicia do <xref:System.ComponentModel.TypeDescriptionProviderAttribute> ładowania typu przez wywołanie metody, takiej <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> jak lub przeciążenia <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> , która zakłada, że typ znajduje się w określonym zestawie.</span><span class="sxs-lookup"><span data-stu-id="a20e7-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.TypeDescriptionProviderAttribute> type by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="a20e7-110">W takim przypadku zestaw, do którego odwołuje się wywołanie metody, powinien zostać zaktualizowany w celu odzwierciedlenia nowej lokalizacji zestawu.</span><span class="sxs-lookup"><span data-stu-id="a20e7-110">If that is the case, the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="a20e7-111">Kategoria</span><span class="sxs-lookup"><span data-stu-id="a20e7-111">Category</span></span>

<span data-ttu-id="a20e7-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a20e7-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a20e7-113">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="a20e7-113">Affected APIs</span></span>

- <span data-ttu-id="a20e7-114">Brak</span><span class="sxs-lookup"><span data-stu-id="a20e7-114">None</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->