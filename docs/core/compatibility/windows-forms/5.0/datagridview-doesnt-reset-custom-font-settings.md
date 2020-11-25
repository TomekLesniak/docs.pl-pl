---
title: 'Nieprzerwana zmiana: formant DataGridView nie ustawia już czcionek dla dostosowanych stylów komórek'
description: Zapoznaj się z istotną zmianą w programie .NET 5,0, gdzie formant DataGridView nie resetuje domyślnych czcionek stylu komórki, aby pasowały do czcionki otaczającej, Jeśli czcionka stylu komórki została dostosowana.
ms.date: 10/18/2020
ms.openlocfilehash: 708b12ba1305681f5c38eb605861d02e3b2c8eb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761721"
---
# <a name="datagridview-no-longer-resets-fonts-for-customized-cell-styles"></a><span data-ttu-id="62df3-103">Formant DataGridView nie jest już resetowany czcionek dla niestandardowych stylów komórek</span><span class="sxs-lookup"><span data-stu-id="62df3-103">DataGridView no longer resets fonts for customized cell styles</span></span>

<span data-ttu-id="62df3-104">Gdy czcionka otoczenia ulegnie zmianie, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> nie jest już resetowane domyślne czcionki stylu komórki, aby pasowała do czcionki otaczającej, Jeśli czcionka stylu komórki została dostosowana.</span><span class="sxs-lookup"><span data-stu-id="62df3-104">When the ambient font changes, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> no longer resets default cell style fonts to match the ambient font if the cell style font has been customized.</span></span>

## <a name="change-description"></a><span data-ttu-id="62df3-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="62df3-105">Change description</span></span>

<span data-ttu-id="62df3-106">W poprzednich wersjach .NET, Jeśli czcionka otoczenia ulegnie zmianie, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> resetuje i przesłania czcionki zdefiniowane przez użytkownika we <xref:System.Windows.Forms.DataGridView.DefaultCellStyle> <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> właściwościach, i <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> .</span><span class="sxs-lookup"><span data-stu-id="62df3-106">In previous .NET versions, if the ambient font changes, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> resets and overrides user-defined fonts in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, and <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties.</span></span>

<span data-ttu-id="62df3-107">Począwszy od programu .NET 5,0, w przypadku konfigurowania ustawień czcionki we <xref:System.Windows.Forms.DataGridView.DefaultCellStyle> <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> właściwościach, lub, <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> te ustawienia są zachowywane nawet wtedy, gdy zmieni się czcionka otoczenia.</span><span class="sxs-lookup"><span data-stu-id="62df3-107">Starting in .NET 5.0, if you configure font settings in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties, those settings are retained even when the ambient font changes.</span></span> <span data-ttu-id="62df3-108">Dla każdej z tych właściwości, które nie dostosowuje czcionki, czcionka zmieni się w celu dopasowania do ustawień czcionki otoczenia.</span><span class="sxs-lookup"><span data-stu-id="62df3-108">For any of these properties that you don't customize the font, the font will change to match the ambient font settings.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="62df3-109">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="62df3-109">Reason for change</span></span>

<span data-ttu-id="62df3-110">[Zmiana domyślnej czcionki w programie .NET Core 3,0](../../winforms.md#default-control-font-changed-to-segoe-ui-9-pt)powoduje zmianę domyślnych ustawień czcionki dla różnych stylów komórek.</span><span class="sxs-lookup"><span data-stu-id="62df3-110">With the [change of the default font in .NET Core 3.0](../../winforms.md#default-control-font-changed-to-segoe-ui-9-pt), the default font settings for the various cell styles also changed.</span></span> <span data-ttu-id="62df3-111">Takie zachowanie jest niepożądane w przypadku aplikacji korzystających z niestandardowych stylów w swoich <xref:System.Windows.Forms.DataGridViewElement.DataGridView> kontrolkach i utrudniają migrację tych aplikacji z .NET Framework do programu .net 5,0.</span><span class="sxs-lookup"><span data-stu-id="62df3-111">This behavior is undesirable for apps that rely on custom styling in their <xref:System.Windows.Forms.DataGridViewElement.DataGridView> controls, and impeded the migration of these apps from .NET Framework to .NET 5.0.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="62df3-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="62df3-112">Version introduced</span></span>

<span data-ttu-id="62df3-113">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="62df3-113">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="62df3-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="62df3-114">Recommended action</span></span>

<span data-ttu-id="62df3-115">W Twojej części nie jest wymagana żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="62df3-115">No action is required on your part.</span></span> <span data-ttu-id="62df3-116">Jednakże jeśli dostosowano czcionkę we <xref:System.Windows.Forms.DataGridView.DefaultCellStyle> <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> właściwościach,, lub, <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> chcesz dopasować czcionkę do otaczającej czcionki, ustaw <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> `null` dla każdej właściwości.</span><span class="sxs-lookup"><span data-stu-id="62df3-116">However, if you've customized the font in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties and want the font to match the ambient font, set <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> to `null` for each property.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="62df3-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="62df3-117">Affected APIs</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Windows.Forms.DataGridView.DefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle`

### Category

- Windows Forms

-->
