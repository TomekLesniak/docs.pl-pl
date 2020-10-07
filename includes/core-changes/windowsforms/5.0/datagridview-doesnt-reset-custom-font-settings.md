---
ms.openlocfilehash: 9c84c9f844a2a7efb9633c11634b069ef6b6033b
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804868"
---
### <a name="datagridview-no-longer-resets-fonts-for-customized-cell-styles"></a><span data-ttu-id="d2135-101">Formant DataGridView nie jest już resetowany czcionek dla niestandardowych stylów komórek</span><span class="sxs-lookup"><span data-stu-id="d2135-101">DataGridView no longer resets fonts for customized cell styles</span></span>

<span data-ttu-id="d2135-102">Gdy czcionka otoczenia ulegnie zmianie, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> nie jest już resetowane domyślne czcionki stylu komórki, aby pasowała do czcionki otaczającej, Jeśli czcionka stylu komórki została dostosowana.</span><span class="sxs-lookup"><span data-stu-id="d2135-102">When the ambient font changes, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> no longer resets default cell style fonts to match the ambient font if the cell style font has been customized.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d2135-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="d2135-103">Change description</span></span>

<span data-ttu-id="d2135-104">W poprzednich wersjach .NET, Jeśli czcionka otoczenia ulegnie zmianie, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> resetuje i przesłania czcionki zdefiniowane przez użytkownika we <xref:System.Windows.Forms.DataGridView.DefaultCellStyle> <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> właściwościach, i <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> .</span><span class="sxs-lookup"><span data-stu-id="d2135-104">In previous .NET versions, if the ambient font changes, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> resets and overrides user-defined fonts in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, and <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties.</span></span>

<span data-ttu-id="d2135-105">Począwszy od programu .NET 5,0, w przypadku konfigurowania ustawień czcionki we <xref:System.Windows.Forms.DataGridView.DefaultCellStyle> <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> właściwościach, lub, <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> te ustawienia są zachowywane nawet wtedy, gdy zmieni się czcionka otoczenia.</span><span class="sxs-lookup"><span data-stu-id="d2135-105">Starting in .NET 5.0, if you configure font settings in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties, those settings are retained even when the ambient font changes.</span></span> <span data-ttu-id="d2135-106">Dla każdej z tych właściwości, które nie dostosowuje czcionki, czcionka zmieni się w celu dopasowania do ustawień czcionki otoczenia.</span><span class="sxs-lookup"><span data-stu-id="d2135-106">For any of these properties that you don't customize the font, the font will change to match the ambient font settings.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d2135-107">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="d2135-107">Reason for change</span></span>

<span data-ttu-id="d2135-108">[Zmiana domyślnej czcionki w programie .NET Core 3,0](../../../../docs/core/compatibility/winforms.md#default-control-font-changed-to-segoe-ui-9-pt)powoduje zmianę domyślnych ustawień czcionki dla różnych stylów komórek.</span><span class="sxs-lookup"><span data-stu-id="d2135-108">With the [change of the default font in .NET Core 3.0](../../../../docs/core/compatibility/winforms.md#default-control-font-changed-to-segoe-ui-9-pt), the default font settings for the various cell styles also changed.</span></span> <span data-ttu-id="d2135-109">Takie zachowanie jest niepożądane w przypadku aplikacji korzystających z niestandardowych stylów w swoich <xref:System.Windows.Forms.DataGridViewElement.DataGridView> kontrolkach i utrudniają migrację tych aplikacji z .NET Framework do programu .net 5,0.</span><span class="sxs-lookup"><span data-stu-id="d2135-109">This behavior is undesirable for apps that rely on custom styling in their <xref:System.Windows.Forms.DataGridViewElement.DataGridView> controls, and impeded the migration of these apps from .NET Framework to .NET 5.0.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d2135-110">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="d2135-110">Version introduced</span></span>

<span data-ttu-id="d2135-111">.NET 5,0 RC2</span><span class="sxs-lookup"><span data-stu-id="d2135-111">.NET 5.0 RC2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d2135-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="d2135-112">Recommended action</span></span>

<span data-ttu-id="d2135-113">W Twojej części nie jest wymagana żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="d2135-113">No action is required on your part.</span></span> <span data-ttu-id="d2135-114">Jednakże jeśli dostosowano czcionkę we <xref:System.Windows.Forms.DataGridView.DefaultCellStyle> <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> właściwościach,, lub, <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> chcesz dopasować czcionkę do otaczającej czcionki, ustaw <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> `null` dla każdej właściwości.</span><span class="sxs-lookup"><span data-stu-id="d2135-114">However, if you've customized the font in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties and want the font to match the ambient font, set <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> to `null` for each property.</span></span>

#### <a name="category"></a><span data-ttu-id="d2135-115">Kategoria</span><span class="sxs-lookup"><span data-stu-id="d2135-115">Category</span></span>

- <span data-ttu-id="d2135-116">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d2135-116">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d2135-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d2135-117">Affected APIs</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Windows.Forms.DataGridView.DefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle`

-->
