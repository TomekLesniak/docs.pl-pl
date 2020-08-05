---
ms.openlocfilehash: df6169289fb96df5f7daf8bd58ccaeebc33ad87c
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556239"
---
### <a name="uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a><span data-ttu-id="836b5-101">Nieobsługiwany przełącznik zgodności UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="836b5-101">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>

<span data-ttu-id="836b5-102">`Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue`Przełącznik zgodności, który został wprowadzony w .NET Framework 4.7.2, nie jest obsługiwany w Windows Forms na platformie .NET Core lub .net 5,0 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="836b5-102">The `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch, which was introduced in .NET Framework 4.7.2, is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="836b5-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="836b5-103">Change description</span></span>

<span data-ttu-id="836b5-104">Począwszy od .NET Framework 4.7.2, `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` przełącznik zgodności pozwala deweloperowi zrezygnować z nowego zachowania <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> właściwości, co teraz zwraca odwołanie do kontroli źródła.</span><span class="sxs-lookup"><span data-stu-id="836b5-104">Starting with .NET Framework 4.7.2, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch allows the developer to opt out of the new behavior of the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property, which now returns a reference to the source control.</span></span> <span data-ttu-id="836b5-105">Poprzednie zachowanie właściwości zostało zwrócone `null` .</span><span class="sxs-lookup"><span data-stu-id="836b5-105">The previous behavior of the property was to return `null`.</span></span> <span data-ttu-id="836b5-106">Aby uzyskać więcej informacji, zobacz [ \<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span><span class="sxs-lookup"><span data-stu-id="836b5-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="836b5-107">W przypadku programów .NET Core i .NET 5,0 i nowszych `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` przełącznik nie jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="836b5-107">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="836b5-108">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="836b5-108">Version introduced</span></span>

<span data-ttu-id="836b5-109">3.0</span><span class="sxs-lookup"><span data-stu-id="836b5-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="836b5-110">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="836b5-110">Recommended action</span></span>

<span data-ttu-id="836b5-111">Usuń przełącznik.</span><span class="sxs-lookup"><span data-stu-id="836b5-111">Remove the switch.</span></span> <span data-ttu-id="836b5-112">Przełącznik nie jest obsługiwany i żadna alternatywna funkcja nie jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="836b5-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="836b5-113">Kategoria</span><span class="sxs-lookup"><span data-stu-id="836b5-113">Category</span></span>

<span data-ttu-id="836b5-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="836b5-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="836b5-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="836b5-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
