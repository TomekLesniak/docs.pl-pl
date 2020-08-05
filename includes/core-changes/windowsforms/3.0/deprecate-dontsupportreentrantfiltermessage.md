---
ms.openlocfilehash: 95aa243a5790d4201c7871e617dbe4ccafb7c1a1
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556247"
---
### <a name="dontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a><span data-ttu-id="70670-101">Nieobsługiwany przełącznik zgodności DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="70670-101">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>

<span data-ttu-id="70670-102">`Switch.System.Windows.Forms.DontSupportReentrantFilterMessage`Przełącznik zgodności, który został wprowadzony w .NET Framework 4.6.1, nie jest obsługiwany w Windows Forms na platformie .NET Core i .net 5,0 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="70670-102">The `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core and .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="70670-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="70670-103">Change description</span></span>

<span data-ttu-id="70670-104">Począwszy od .NET Framework 4.6.1, `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` przełącznik zgodności rozwiązuje możliwe wyjątki, <xref:System.IndexOutOfRangeException> gdy <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> komunikat jest wywoływany z implementacją niestandardową <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="70670-104">Starting with the .NET Framework 4.6.1, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch addresses possible <xref:System.IndexOutOfRangeException> exceptions when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> message is called with a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="70670-105">Aby uzyskać więcej informacji, zobacz Rozwiązywanie [problemów z niestandardowymi implementacjami IMessageFilter. PreFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span><span class="sxs-lookup"><span data-stu-id="70670-105">For more information, see [Mitigation: Custom IMessageFilter.PreFilterMessage Implementations](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span></span>

<span data-ttu-id="70670-106">W przypadku programów .NET Core i .NET 5,0 i nowszych `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` przełącznik nie jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="70670-106">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="70670-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="70670-107">Version introduced</span></span>

<span data-ttu-id="70670-108">3.0</span><span class="sxs-lookup"><span data-stu-id="70670-108">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="70670-109">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="70670-109">Recommended action</span></span>

<span data-ttu-id="70670-110">Usuń przełącznik.</span><span class="sxs-lookup"><span data-stu-id="70670-110">Remove the switch.</span></span> <span data-ttu-id="70670-111">Przełącznik nie jest obsługiwany i żadna alternatywna funkcja nie jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="70670-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="70670-112">Kategoria</span><span class="sxs-lookup"><span data-stu-id="70670-112">Category</span></span>

<span data-ttu-id="70670-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="70670-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="70670-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="70670-114">Affected APIs</span></span>

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
