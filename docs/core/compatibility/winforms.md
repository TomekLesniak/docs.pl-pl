---
title: Windows Forms istotne zmiany
description: Wyświetla listę istotnych zmian w Windows Forms dla platform .NET Core i .NET 5.
ms.date: 09/08/2020
ms.openlocfilehash: c3d2d23601d6a2d9d44761c4371fe34d3d5ed1f3
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656348"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="86f07-103">Istotne zmiany w Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86f07-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="86f07-104">Obsługa Windows Forms została dodana do programu .NET Core w wersji 3,0.</span><span class="sxs-lookup"><span data-stu-id="86f07-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="86f07-105">W tym artykule wymieniono istotne zmiany Windows Forms przez wersję programu .NET, w której zostały wprowadzone.</span><span class="sxs-lookup"><span data-stu-id="86f07-105">This article lists breaking changes for Windows Forms by the .NET version in which they were introduced.</span></span> <span data-ttu-id="86f07-106">W przypadku uaktualniania aplikacji Windows Forms z .NET Framework lub z poprzedniej wersji platformy .NET Core (3,0 lub nowszej) ten artykuł dotyczy Ciebie.</span><span class="sxs-lookup"><span data-stu-id="86f07-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article applies to you.</span></span>

<span data-ttu-id="86f07-107">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="86f07-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="86f07-108">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="86f07-108">Breaking change</span></span> | <span data-ttu-id="86f07-109">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="86f07-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="86f07-110">Interfejsy API związane z formantem DataGridView teraz zgłaszają InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="86f07-110">DataGridView-related APIs now throw InvalidOperationException</span></span>](#datagridview-related-apis-now-throw-invalidoperationexception) | <span data-ttu-id="86f07-111">5,0</span><span class="sxs-lookup"><span data-stu-id="86f07-111">5.0</span></span> |
| [<span data-ttu-id="86f07-112">WinForms i aplikacje WPF używają Microsoft. NET. Sdk</span><span class="sxs-lookup"><span data-stu-id="86f07-112">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>](#winforms-and-wpf-apps-use-microsoftnetsdk) | <span data-ttu-id="86f07-113">5,0</span><span class="sxs-lookup"><span data-stu-id="86f07-113">5.0</span></span> |
| [<span data-ttu-id="86f07-114">Usunięto kontrolki paska stanu</span><span class="sxs-lookup"><span data-stu-id="86f07-114">Removed status bar controls</span></span>](#removed-status-bar-controls) | <span data-ttu-id="86f07-115">5,0</span><span class="sxs-lookup"><span data-stu-id="86f07-115">5.0</span></span> |
| [<span data-ttu-id="86f07-116">Metody WinForms teraz generują ArgumentException</span><span class="sxs-lookup"><span data-stu-id="86f07-116">WinForms methods now throw ArgumentException</span></span>](#winforms-methods-now-throw-argumentexception) | <span data-ttu-id="86f07-117">5,0</span><span class="sxs-lookup"><span data-stu-id="86f07-117">5.0</span></span> |
| [<span data-ttu-id="86f07-118">Metody WinForms teraz generują ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="86f07-118">WinForms methods now throw ArgumentNullException</span></span>](#winforms-methods-now-throw-argumentnullexception) | <span data-ttu-id="86f07-119">5,0</span><span class="sxs-lookup"><span data-stu-id="86f07-119">5.0</span></span> |
| [<span data-ttu-id="86f07-120">Właściwości WinForms teraz generują wyjątku ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="86f07-120">WinForms properties now throw ArgumentOutOfRangeException</span></span>](#winforms-properties-now-throw-argumentoutofrangeexception) | <span data-ttu-id="86f07-121">5,0</span><span class="sxs-lookup"><span data-stu-id="86f07-121">5.0</span></span> |
| [<span data-ttu-id="86f07-122">Usunięte kontrolki</span><span class="sxs-lookup"><span data-stu-id="86f07-122">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="86f07-123">3,1</span><span class="sxs-lookup"><span data-stu-id="86f07-123">3.1</span></span> |
| [<span data-ttu-id="86f07-124">Zdarzenie CellFormatting nie zostało zgłoszone, jeśli jest wyświetlana etykietka narzędzia</span><span class="sxs-lookup"><span data-stu-id="86f07-124">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="86f07-125">3,1</span><span class="sxs-lookup"><span data-stu-id="86f07-125">3.1</span></span> |
| [<span data-ttu-id="86f07-126">Formant. DefaultFont został zmieniony na Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="86f07-126">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="86f07-127">3,0</span><span class="sxs-lookup"><span data-stu-id="86f07-127">3.0</span></span> |
| [<span data-ttu-id="86f07-128">Modernizacja FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="86f07-128">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="86f07-129">3,0</span><span class="sxs-lookup"><span data-stu-id="86f07-129">3.0</span></span> |
| [<span data-ttu-id="86f07-130">SerializableAttribute usunięte z niektórych typów Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86f07-130">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="86f07-131">3,0</span><span class="sxs-lookup"><span data-stu-id="86f07-131">3.0</span></span> |
| [<span data-ttu-id="86f07-132">Nieobsługiwany przełącznik zgodności AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="86f07-132">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="86f07-133">3,0</span><span class="sxs-lookup"><span data-stu-id="86f07-133">3.0</span></span> |
| [<span data-ttu-id="86f07-134">Przełącznik zgodności DomainUpDown. UseLegacyScrolling nie jest obsługiwany</span><span class="sxs-lookup"><span data-stu-id="86f07-134">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="86f07-135">3,0</span><span class="sxs-lookup"><span data-stu-id="86f07-135">3.0</span></span> |
| [<span data-ttu-id="86f07-136">Nieobsługiwany przełącznik zgodności DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="86f07-136">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="86f07-137">3,0</span><span class="sxs-lookup"><span data-stu-id="86f07-137">3.0</span></span> |
| [<span data-ttu-id="86f07-138">Nieobsługiwany przełącznik zgodności DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="86f07-138">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="86f07-139">3,0</span><span class="sxs-lookup"><span data-stu-id="86f07-139">3.0</span></span> |
| [<span data-ttu-id="86f07-140">Nieobsługiwany przełącznik zgodności DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="86f07-140">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="86f07-141">3,0</span><span class="sxs-lookup"><span data-stu-id="86f07-141">3.0</span></span> |
| [<span data-ttu-id="86f07-142">Nieobsługiwany przełącznik zgodności EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="86f07-142">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="86f07-143">3,0</span><span class="sxs-lookup"><span data-stu-id="86f07-143">3.0</span></span> |
| [<span data-ttu-id="86f07-144">Nieobsługiwany przełącznik zgodności UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="86f07-144">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="86f07-145">3,0</span><span class="sxs-lookup"><span data-stu-id="86f07-145">3.0</span></span> |
| [<span data-ttu-id="86f07-146">Nieobsługiwany przełącznik zgodności UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="86f07-146">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="86f07-147">3,0</span><span class="sxs-lookup"><span data-stu-id="86f07-147">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="86f07-148">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="86f07-148">.NET 5.0</span></span>

[!INCLUDE [null-owner-causes-invalidoperationexception](../../../includes/core-changes/windowsforms/5.0/null-owner-causes-invalidoperationexception.md)]

***

[!INCLUDE [sdk-and-target-framework-change](../../../includes/core-changes/windowsforms/5.0/sdk-and-target-framework-change.md)]

***

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

***

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

***

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

[!INCLUDE [invalid-args-cause-argumentoutofrangeexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentoutofrangeexception.md)]

***

## <a name="net-core-31"></a><span data-ttu-id="86f07-149">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="86f07-149">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="86f07-150">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="86f07-150">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

## <a name="see-also"></a><span data-ttu-id="86f07-151">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="86f07-151">See also</span></span>

- [<span data-ttu-id="86f07-152">Port aplikacji Windows Forms do programu .NET Core</span><span class="sxs-lookup"><span data-stu-id="86f07-152">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
