---
ms.openlocfilehash: 3fb8807a9b6f0bb0d2bc746f5e89eaa8a81d6aa8
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556248"
---
### <a name="donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a><span data-ttu-id="51dfc-101">Nieobsługiwany przełącznik zgodności DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="51dfc-101">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>

<span data-ttu-id="51dfc-102">`Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox`Przełącznik zgodności, który został wprowadzony w .NET Framework 4.6.1, nie jest obsługiwany w Windows Forms na platformie .NET Core i .net 5,0 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="51dfc-102">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core and .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="51dfc-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="51dfc-103">Change description</span></span>

<span data-ttu-id="51dfc-104">Rozpoczynając od .NET Framework 4.6.1, wybierając klawisz <kbd>Ctrl</kbd>  +  <kbd>a</kbd> skrótu w <xref:System.Windows.Forms.TextBox> kontrolce zaznacz wszystkie teksty.</span><span class="sxs-lookup"><span data-stu-id="51dfc-104">Starting with .NET Framework 4.6.1, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key in a <xref:System.Windows.Forms.TextBox> control selected all text.</span></span> <span data-ttu-id="51dfc-105">W .NET Framework 4,6 i poprzednich wersjach, wybranie <kbd>Ctrl</kbd>  +  <kbd>A</kbd> klawisza skrótu Ctrl nie zakończyło się niepowodzeniem, aby zaznaczyć cały tekst, jeśli właściwość [TextBox. ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) i <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> właściwości zostały ustawione na `true` .</span><span class="sxs-lookup"><span data-stu-id="51dfc-105">In .NET Framework 4.6 and previous versions, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key failed to select all text if the [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) and <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> properties were both set to `true`.</span></span> <span data-ttu-id="51dfc-106">`Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox`Przełącznik zgodności został wprowadzony w .NET Framework 4.6.1, aby zachować oryginalne zachowanie.</span><span class="sxs-lookup"><span data-stu-id="51dfc-106">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch was introduced in .NET Framework 4.6.1 to retain the original behavior.</span></span> <span data-ttu-id="51dfc-107">Aby uzyskać więcej informacji, zobacz <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="51dfc-107">For more information see <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="51dfc-108">W przypadku oprogramowania .NET Core i .NET 5,0 i nowszych wersji `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` przełącznik nie jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="51dfc-108">In .NET Core and .NET 5.0 and later versions, the `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="51dfc-109">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="51dfc-109">Version introduced</span></span>

<span data-ttu-id="51dfc-110">3.0</span><span class="sxs-lookup"><span data-stu-id="51dfc-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="51dfc-111">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="51dfc-111">Recommended action</span></span>

<span data-ttu-id="51dfc-112">Usuń przełącznik.</span><span class="sxs-lookup"><span data-stu-id="51dfc-112">Remove the switch.</span></span> <span data-ttu-id="51dfc-113">Przełącznik nie jest obsługiwany i żadna alternatywna funkcja nie jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="51dfc-113">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="51dfc-114">Kategoria</span><span class="sxs-lookup"><span data-stu-id="51dfc-114">Category</span></span>

<span data-ttu-id="51dfc-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51dfc-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="51dfc-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="51dfc-116">Affected APIs</span></span>

- <span data-ttu-id="51dfc-117">Brak</span><span class="sxs-lookup"><span data-stu-id="51dfc-117">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
