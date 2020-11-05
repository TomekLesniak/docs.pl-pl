---
title: Windows Forms istotne zmiany
description: Wyświetla listę istotnych zmian w Windows Forms dla platform .NET Core i .NET 5.
ms.date: 09/08/2020
ms.openlocfilehash: 01810a690227bbcab2103f00767315dbc5d5fae3
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400646"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="97cc4-103">Istotne zmiany w Windows Forms</span><span class="sxs-lookup"><span data-stu-id="97cc4-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="97cc4-104">Obsługa Windows Forms została dodana do programu .NET Core w wersji 3,0.</span><span class="sxs-lookup"><span data-stu-id="97cc4-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="97cc4-105">W tym artykule wymieniono istotne zmiany Windows Forms przez wersję programu .NET, w której zostały wprowadzone.</span><span class="sxs-lookup"><span data-stu-id="97cc4-105">This article lists breaking changes for Windows Forms by the .NET version in which they were introduced.</span></span> <span data-ttu-id="97cc4-106">W przypadku uaktualniania aplikacji Windows Forms z .NET Framework lub z poprzedniej wersji platformy .NET Core (3,0 lub nowszej) ten artykuł dotyczy Ciebie.</span><span class="sxs-lookup"><span data-stu-id="97cc4-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article applies to you.</span></span>

<span data-ttu-id="97cc4-107">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="97cc4-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="97cc4-108">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="97cc4-108">Breaking change</span></span> | <span data-ttu-id="97cc4-109">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="97cc4-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="97cc4-110">TextFormatFlags. ModifyString jest przestarzała</span><span class="sxs-lookup"><span data-stu-id="97cc4-110">TextFormatFlags.ModifyString is obsolete</span></span>](#textformatflagsmodifystring-is-obsolete) | <span data-ttu-id="97cc4-111">5,0</span><span class="sxs-lookup"><span data-stu-id="97cc4-111">5.0</span></span> |
| [<span data-ttu-id="97cc4-112">Formant DataGridView nie jest już resetowany czcionek dla niestandardowych stylów komórek</span><span class="sxs-lookup"><span data-stu-id="97cc4-112">DataGridView no longer resets fonts for customized cell styles</span></span>](#datagridview-no-longer-resets-fonts-for-customized-cell-styles) | <span data-ttu-id="97cc4-113">5,0</span><span class="sxs-lookup"><span data-stu-id="97cc4-113">5.0</span></span> |
| [<span data-ttu-id="97cc4-114">OutputType ustawiony na WinExe dla aplikacji WPF i WinForms</span><span class="sxs-lookup"><span data-stu-id="97cc4-114">OutputType set to WinExe for WPF and WinForms apps</span></span>](#outputtype-set-to-winexe-for-wpf-and-winforms-apps) | <span data-ttu-id="97cc4-115">5,0</span><span class="sxs-lookup"><span data-stu-id="97cc4-115">5.0</span></span> |
| [<span data-ttu-id="97cc4-116">Interfejsy API związane z formantem DataGridView teraz zgłaszają InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="97cc4-116">DataGridView-related APIs now throw InvalidOperationException</span></span>](#datagridview-related-apis-now-throw-invalidoperationexception) | <span data-ttu-id="97cc4-117">5,0</span><span class="sxs-lookup"><span data-stu-id="97cc4-117">5.0</span></span> |
| [<span data-ttu-id="97cc4-118">WinForms i aplikacje WPF używają Microsoft. NET. Sdk</span><span class="sxs-lookup"><span data-stu-id="97cc4-118">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>](#winforms-and-wpf-apps-use-microsoftnetsdk) | <span data-ttu-id="97cc4-119">5,0</span><span class="sxs-lookup"><span data-stu-id="97cc4-119">5.0</span></span> |
| [<span data-ttu-id="97cc4-120">Usunięto kontrolki paska stanu</span><span class="sxs-lookup"><span data-stu-id="97cc4-120">Removed status bar controls</span></span>](#removed-status-bar-controls) | <span data-ttu-id="97cc4-121">5,0</span><span class="sxs-lookup"><span data-stu-id="97cc4-121">5.0</span></span> |
| [<span data-ttu-id="97cc4-122">Metody WinForms teraz generują ArgumentException</span><span class="sxs-lookup"><span data-stu-id="97cc4-122">WinForms methods now throw ArgumentException</span></span>](#winforms-methods-now-throw-argumentexception) | <span data-ttu-id="97cc4-123">5,0</span><span class="sxs-lookup"><span data-stu-id="97cc4-123">5.0</span></span> |
| [<span data-ttu-id="97cc4-124">Metody WinForms teraz generują ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="97cc4-124">WinForms methods now throw ArgumentNullException</span></span>](#winforms-methods-now-throw-argumentnullexception) | <span data-ttu-id="97cc4-125">5,0</span><span class="sxs-lookup"><span data-stu-id="97cc4-125">5.0</span></span> |
| [<span data-ttu-id="97cc4-126">Właściwości WinForms teraz generują wyjątku ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="97cc4-126">WinForms properties now throw ArgumentOutOfRangeException</span></span>](#winforms-properties-now-throw-argumentoutofrangeexception) | <span data-ttu-id="97cc4-127">5,0</span><span class="sxs-lookup"><span data-stu-id="97cc4-127">5.0</span></span> |
| [<span data-ttu-id="97cc4-128">Usunięte kontrolki</span><span class="sxs-lookup"><span data-stu-id="97cc4-128">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="97cc4-129">3,1</span><span class="sxs-lookup"><span data-stu-id="97cc4-129">3.1</span></span> |
| [<span data-ttu-id="97cc4-130">Zdarzenie CellFormatting nie zostało zgłoszone, jeśli jest wyświetlana etykietka narzędzia</span><span class="sxs-lookup"><span data-stu-id="97cc4-130">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="97cc4-131">3,1</span><span class="sxs-lookup"><span data-stu-id="97cc4-131">3.1</span></span> |
| [<span data-ttu-id="97cc4-132">Formant. DefaultFont został zmieniony na Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="97cc4-132">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="97cc4-133">3.0</span><span class="sxs-lookup"><span data-stu-id="97cc4-133">3.0</span></span> |
| [<span data-ttu-id="97cc4-134">Modernizacja FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="97cc4-134">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="97cc4-135">3.0</span><span class="sxs-lookup"><span data-stu-id="97cc4-135">3.0</span></span> |
| [<span data-ttu-id="97cc4-136">SerializableAttribute usunięte z niektórych typów Windows Forms</span><span class="sxs-lookup"><span data-stu-id="97cc4-136">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="97cc4-137">3.0</span><span class="sxs-lookup"><span data-stu-id="97cc4-137">3.0</span></span> |
| [<span data-ttu-id="97cc4-138">Nieobsługiwany przełącznik zgodności AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="97cc4-138">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="97cc4-139">3.0</span><span class="sxs-lookup"><span data-stu-id="97cc4-139">3.0</span></span> |
| [<span data-ttu-id="97cc4-140">Przełącznik zgodności DomainUpDown. UseLegacyScrolling nie jest obsługiwany</span><span class="sxs-lookup"><span data-stu-id="97cc4-140">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="97cc4-141">3.0</span><span class="sxs-lookup"><span data-stu-id="97cc4-141">3.0</span></span> |
| [<span data-ttu-id="97cc4-142">Nieobsługiwany przełącznik zgodności DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="97cc4-142">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="97cc4-143">3.0</span><span class="sxs-lookup"><span data-stu-id="97cc4-143">3.0</span></span> |
| [<span data-ttu-id="97cc4-144">Nieobsługiwany przełącznik zgodności DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="97cc4-144">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="97cc4-145">3.0</span><span class="sxs-lookup"><span data-stu-id="97cc4-145">3.0</span></span> |
| [<span data-ttu-id="97cc4-146">Nieobsługiwany przełącznik zgodności DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="97cc4-146">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="97cc4-147">3.0</span><span class="sxs-lookup"><span data-stu-id="97cc4-147">3.0</span></span> |
| [<span data-ttu-id="97cc4-148">Nieobsługiwany przełącznik zgodności EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="97cc4-148">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="97cc4-149">3.0</span><span class="sxs-lookup"><span data-stu-id="97cc4-149">3.0</span></span> |
| [<span data-ttu-id="97cc4-150">Nieobsługiwany przełącznik zgodności UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="97cc4-150">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="97cc4-151">3.0</span><span class="sxs-lookup"><span data-stu-id="97cc4-151">3.0</span></span> |
| [<span data-ttu-id="97cc4-152">Nieobsługiwany przełącznik zgodności UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="97cc4-152">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="97cc4-153">3.0</span><span class="sxs-lookup"><span data-stu-id="97cc4-153">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="97cc4-154">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="97cc4-154">.NET 5.0</span></span>

[!INCLUDE [modifystring-field-of-textformatflags-obsolete](../../../includes/core-changes/windowsforms/5.0/modifystring-field-of-textformatflags-obsolete.md)]

***

[!INCLUDE [datagridview-doesnt-reset-custom-font-settings](../../../includes/core-changes/windowsforms/5.0/datagridview-doesnt-reset-custom-font-settings.md)]

<span data-ttu-id="97cc4-155">\*\*_</span><span class="sxs-lookup"><span data-stu-id="97cc4-155">\*\*_</span></span>

[!INCLUDE [automatically-infer-winexe-output-type](../../../includes/core-changes/windowsforms/5.0/automatically-infer-winexe-output-type.md)]

_*_

[!INCLUDE [null-owner-causes-invalidoperationexception](../../../includes/core-changes/windowsforms/5.0/null-owner-causes-invalidoperationexception.md)]

_*_

[!INCLUDE [sdk-and-target-framework-change](../../../includes/core-changes/windowsforms/5.0/sdk-and-target-framework-change.md)]

_*_

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

_*_

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

_*_

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

_*_

[!INCLUDE [invalid-args-cause-argumentoutofrangeexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentoutofrangeexception.md)]

_*_

## <a name="net-core-31"></a><span data-ttu-id="97cc4-156">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="97cc4-156">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

_*_

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

_*_

## <a name="net-core-30"></a><span data-ttu-id="97cc4-157">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="97cc4-157">.NET Core 3.0</span></span>

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

<span data-ttu-id="97cc4-158">_\*\*</span><span class="sxs-lookup"><span data-stu-id="97cc4-158">_\*\*</span></span>

## <a name="see-also"></a><span data-ttu-id="97cc4-159">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="97cc4-159">See also</span></span>

- [<span data-ttu-id="97cc4-160">Port aplikacji Windows Forms do programu .NET Core</span><span class="sxs-lookup"><span data-stu-id="97cc4-160">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
