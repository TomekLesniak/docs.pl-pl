---
ms.openlocfilehash: 78678b4b352bb063d1521e9aee3492c0cee059b8
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032134"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a><span data-ttu-id="9588c-101">InvalidAsynchronousStateException — przeniesiony do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="9588c-101">InvalidAsynchronousStateException moved to another assembly</span></span>

<span data-ttu-id="9588c-102"><xref:System.ComponentModel.InvalidAsynchronousStateException>Klasa została przeniesiona.</span><span class="sxs-lookup"><span data-stu-id="9588c-102">The <xref:System.ComponentModel.InvalidAsynchronousStateException> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="9588c-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="9588c-103">Change description</span></span>

<span data-ttu-id="9588c-104">W programie .NET Core 2,2 i starszych wersjach <xref:System.ComponentModel.InvalidAsynchronousStateException> Klasa jest dostępna w zestawie *System. ComponentModel. TypeConverter* .</span><span class="sxs-lookup"><span data-stu-id="9588c-104">In .NET Core 2.2 and earlier versions, the <xref:System.ComponentModel.InvalidAsynchronousStateException> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="9588c-105">Począwszy od platformy .NET Core 3,0, znajduje się on w zestawie *System. ComponentModel. prymityws* .</span><span class="sxs-lookup"><span data-stu-id="9588c-105">Starting with .NET Core 3.0, it is found in the *System.ComponentModel.Primitives* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9588c-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="9588c-106">Version introduced</span></span>

<span data-ttu-id="9588c-107">3.0</span><span class="sxs-lookup"><span data-stu-id="9588c-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9588c-108">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="9588c-108">Recommended action</span></span>

<span data-ttu-id="9588c-109">Ta zmiana dotyczy tylko aplikacji, które używają odbicia do ładowania <xref:System.ComponentModel.InvalidAsynchronousStateException> przez wywołanie metody, takiej jak <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> lub przeciążenia <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> , która zakłada, że typ znajduje się w określonym zestawie.</span><span class="sxs-lookup"><span data-stu-id="9588c-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.InvalidAsynchronousStateException> by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="9588c-110">W takim przypadku należy zaktualizować zestaw przywoływany w wywołaniu metody, aby odzwierciedlić nową lokalizację zestawu.</span><span class="sxs-lookup"><span data-stu-id="9588c-110">If that is the case, update the assembly referenced in the method call to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="9588c-111">Kategoria</span><span class="sxs-lookup"><span data-stu-id="9588c-111">Category</span></span>

<span data-ttu-id="9588c-112">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="9588c-112">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9588c-113">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="9588c-113">Affected APIs</span></span>

<span data-ttu-id="9588c-114">Brak.</span><span class="sxs-lookup"><span data-stu-id="9588c-114">None.</span></span>

<!--

#### Affected APIs

- Not detectable via API analysis

-->
