---
ms.openlocfilehash: e10b5168d59edd56ff549a3a1e3a09d023fe5e28
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556231"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a><span data-ttu-id="30a4c-101">Nieobsługiwany przełącznik zgodności DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="30a4c-101">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>

<span data-ttu-id="30a4c-102">`Switch.System.Windows.Forms.UseLegacyImages`Przełącznik zgodności, który został wprowadzony w .NET Framework 4.7.1, nie jest obsługiwany w Windows Forms na platformie .NET Core lub .net 5,0 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="30a4c-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="30a4c-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="30a4c-103">Change description</span></span>

<span data-ttu-id="30a4c-104">W .NET Framework 4.6.2 i poprzednich wersjach <xref:System.Windows.Forms.RichTextBox> kontrolka tworzy wystąpienie elementu Win32 RichEdit Control v 3.0 i dla aplikacji, które są przeznaczone dla .NET Framework 4.7.1, <xref:System.Windows.Forms.RichTextBox> formant tworzy wystąpienie elementu RichEdit v 4.1 (w *msftedit.dll*).</span><span class="sxs-lookup"><span data-stu-id="30a4c-104">In .NET Framework 4.6.2 and previous versions, the <xref:System.Windows.Forms.RichTextBox> control instantiates the Win32 RichEdit control v3.0, and for applications that target .NET Framework 4.7.1, the  <xref:System.Windows.Forms.RichTextBox> control instantiates RichEdit v4.1 (in *msftedit.dll*).</span></span> <span data-ttu-id="30a4c-105">`Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl`Wprowadzono przełącznik zgodności, aby umożliwić aplikacjom, które są przeznaczone .NET Framework 4.7.1 i nowsze wersje, aby zrezygnować z nowej kontrolki RichEdit v 4.1 i zamiast tego używać starego formantu RichEdit v3.</span><span class="sxs-lookup"><span data-stu-id="30a4c-105">The `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` compatibility switch was introduced to allow applications that target .NET Framework 4.7.1 and later versions to opt out of the new RichEdit v4.1 control and use the old RichEdit v3 control instead.</span></span>

<span data-ttu-id="30a4c-106">W przypadku oprogramowania .NET Core i .NET 5,0 i nowszych wersji `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` przełącznik nie jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="30a4c-106">In .NET Core and .NET 5.0 and later versions, the `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` switch is not supported.</span></span> <span data-ttu-id="30a4c-107">Obsługiwane są tylko nowe wersje <xref:System.Windows.Forms.RichTextBox> formantu.</span><span class="sxs-lookup"><span data-stu-id="30a4c-107">Only new versions of the <xref:System.Windows.Forms.RichTextBox> control are supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="30a4c-108">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="30a4c-108">Version introduced</span></span>

<span data-ttu-id="30a4c-109">3.0</span><span class="sxs-lookup"><span data-stu-id="30a4c-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="30a4c-110">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="30a4c-110">Recommended action</span></span>

<span data-ttu-id="30a4c-111">Usuń przełącznik.</span><span class="sxs-lookup"><span data-stu-id="30a4c-111">Remove the switch.</span></span> <span data-ttu-id="30a4c-112">Przełącznik nie jest obsługiwany i żadna alternatywna funkcja nie jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="30a4c-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="30a4c-113">Kategoria</span><span class="sxs-lookup"><span data-stu-id="30a4c-113">Category</span></span>

<span data-ttu-id="30a4c-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30a4c-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="30a4c-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="30a4c-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

#### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
