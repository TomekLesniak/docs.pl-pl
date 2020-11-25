---
title: Windows Forms istotne zmiany
description: Wyświetla listę istotnych zmian w Windows Forms dla platformy .NET Core 3,0 i 3,1.
ms.date: 09/08/2020
ms.openlocfilehash: b944f7eea89b61f41feb8eef99e949c2d6017960
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726434"
---
# <a name="breaking-changes-in-windows-forms-for-net-core-30-and-31"></a><span data-ttu-id="9b30d-103">Istotne zmiany w Windows Forms dla platform .NET Core 3,0 i 3,1</span><span class="sxs-lookup"><span data-stu-id="9b30d-103">Breaking changes in Windows Forms for .NET Core 3.0 and 3.1</span></span>

<span data-ttu-id="9b30d-104">Obsługa Windows Forms została dodana do programu .NET Core w wersji 3,0.</span><span class="sxs-lookup"><span data-stu-id="9b30d-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="9b30d-105">W tym artykule wymieniono istotne zmiany Windows Forms przez wersję programu .NET, w której zostały wprowadzone.</span><span class="sxs-lookup"><span data-stu-id="9b30d-105">This article lists breaking changes for Windows Forms by the .NET version in which they were introduced.</span></span> <span data-ttu-id="9b30d-106">W przypadku uaktualniania aplikacji Windows Forms z .NET Framework lub z poprzedniej wersji platformy .NET Core (3,0 lub nowszej) ten artykuł dotyczy Ciebie.</span><span class="sxs-lookup"><span data-stu-id="9b30d-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article applies to you.</span></span>

<span data-ttu-id="9b30d-107">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="9b30d-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="9b30d-108">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="9b30d-108">Breaking change</span></span> | <span data-ttu-id="9b30d-109">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="9b30d-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="9b30d-110">Usunięte kontrolki</span><span class="sxs-lookup"><span data-stu-id="9b30d-110">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="9b30d-111">3,1</span><span class="sxs-lookup"><span data-stu-id="9b30d-111">3.1</span></span> |
| [<span data-ttu-id="9b30d-112">Zdarzenie CellFormatting nie zostało zgłoszone, jeśli jest wyświetlana etykietka narzędzia</span><span class="sxs-lookup"><span data-stu-id="9b30d-112">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="9b30d-113">3,1</span><span class="sxs-lookup"><span data-stu-id="9b30d-113">3.1</span></span> |
| [<span data-ttu-id="9b30d-114">Formant. DefaultFont został zmieniony na Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="9b30d-114">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="9b30d-115">3.0</span><span class="sxs-lookup"><span data-stu-id="9b30d-115">3.0</span></span> |
| [<span data-ttu-id="9b30d-116">Modernizacja FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="9b30d-116">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="9b30d-117">3.0</span><span class="sxs-lookup"><span data-stu-id="9b30d-117">3.0</span></span> |
| [<span data-ttu-id="9b30d-118">SerializableAttribute usunięte z niektórych typów Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9b30d-118">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="9b30d-119">3.0</span><span class="sxs-lookup"><span data-stu-id="9b30d-119">3.0</span></span> |
| [<span data-ttu-id="9b30d-120">Nieobsługiwany przełącznik zgodności AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="9b30d-120">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="9b30d-121">3.0</span><span class="sxs-lookup"><span data-stu-id="9b30d-121">3.0</span></span> |
| [<span data-ttu-id="9b30d-122">Przełącznik zgodności DomainUpDown. UseLegacyScrolling nie jest obsługiwany</span><span class="sxs-lookup"><span data-stu-id="9b30d-122">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="9b30d-123">3.0</span><span class="sxs-lookup"><span data-stu-id="9b30d-123">3.0</span></span> |
| [<span data-ttu-id="9b30d-124">Nieobsługiwany przełącznik zgodności DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="9b30d-124">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="9b30d-125">3.0</span><span class="sxs-lookup"><span data-stu-id="9b30d-125">3.0</span></span> |
| [<span data-ttu-id="9b30d-126">Nieobsługiwany przełącznik zgodności DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="9b30d-126">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="9b30d-127">3.0</span><span class="sxs-lookup"><span data-stu-id="9b30d-127">3.0</span></span> |
| [<span data-ttu-id="9b30d-128">Nieobsługiwany przełącznik zgodności DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="9b30d-128">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="9b30d-129">3.0</span><span class="sxs-lookup"><span data-stu-id="9b30d-129">3.0</span></span> |
| [<span data-ttu-id="9b30d-130">Nieobsługiwany przełącznik zgodności EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="9b30d-130">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="9b30d-131">3.0</span><span class="sxs-lookup"><span data-stu-id="9b30d-131">3.0</span></span> |
| [<span data-ttu-id="9b30d-132">Nieobsługiwany przełącznik zgodności UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="9b30d-132">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="9b30d-133">3.0</span><span class="sxs-lookup"><span data-stu-id="9b30d-133">3.0</span></span> |
| [<span data-ttu-id="9b30d-134">Nieobsługiwany przełącznik zgodności UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="9b30d-134">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="9b30d-135">3.0</span><span class="sxs-lookup"><span data-stu-id="9b30d-135">3.0</span></span> |

## <a name="net-core-31"></a><span data-ttu-id="9b30d-136">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="9b30d-136">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

<span data-ttu-id="9b30d-137">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9b30d-137">\*\*_</span></span>

## <a name="net-core-30"></a><span data-ttu-id="9b30d-138">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9b30d-138">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

_*_

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

_*_

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

<span data-ttu-id="9b30d-139">_\*\*</span><span class="sxs-lookup"><span data-stu-id="9b30d-139">_\*\*</span></span>

## <a name="see-also"></a><span data-ttu-id="9b30d-140">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9b30d-140">See also</span></span>

- [<span data-ttu-id="9b30d-141">Port aplikacji Windows Forms do programu .NET Core</span><span class="sxs-lookup"><span data-stu-id="9b30d-141">Port a Windows Forms app to .NET Core</span></span>](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)
