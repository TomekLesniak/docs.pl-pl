---
title: Windows Forms istotne zmiany
description: Wyświetla listę istotnych zmian w Windows Forms dla platform .NET Core i .NET 5.
ms.date: 09/08/2020
ms.openlocfilehash: c79fd28b5c3b81ae7ddf1ef3f470601108b87705
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440793"
---
# <a name="breaking-changes-in-windows-forms"></a>Istotne zmiany w Windows Forms

Obsługa Windows Forms została dodana do programu .NET Core w wersji 3,0. W tym artykule wymieniono istotne zmiany Windows Forms przez wersję programu .NET, w której zostały wprowadzone. W przypadku uaktualniania aplikacji Windows Forms z .NET Framework lub z poprzedniej wersji platformy .NET Core (3,0 lub nowszej) ten artykuł dotyczy Ciebie.

Następujące istotne zmiany zostały udokumentowane na tej stronie:

| Zmiana podziału | Wprowadzona wersja |
| - | :-: |
| [TextFormatFlags. ModifyString jest przestarzała](#textformatflagsmodifystring-is-obsolete) | 5,0 |
| [Formant DataGridView nie jest już resetowany czcionek dla niestandardowych stylów komórek](#datagridview-no-longer-resets-fonts-for-customized-cell-styles) | 5,0 |
| [OutputType ustawiony na WinExe dla aplikacji WPF i WinForms](#outputtype-set-to-winexe-for-wpf-and-winforms-apps) | 5,0 |
| [Interfejsy API związane z formantem DataGridView teraz zgłaszają InvalidOperationException](#datagridview-related-apis-now-throw-invalidoperationexception) | 5,0 |
| [WinForms i aplikacje WPF używają Microsoft. NET. Sdk](#winforms-and-wpf-apps-use-microsoftnetsdk) | 5,0 |
| [Usunięto kontrolki paska stanu](#removed-status-bar-controls) | 5,0 |
| [Metody WinForms teraz generują ArgumentException](#winforms-methods-now-throw-argumentexception) | 5,0 |
| [Metody WinForms teraz generują ArgumentNullException](#winforms-methods-now-throw-argumentnullexception) | 5,0 |
| [Właściwości WinForms teraz generują wyjątku ArgumentOutOfRangeException](#winforms-properties-now-throw-argumentoutofrangeexception) | 5,0 |
| [Usunięte kontrolki](#removed-controls) | 3,1 |
| [Zdarzenie CellFormatting nie zostało zgłoszone, jeśli jest wyświetlana etykietka narzędzia](#cellformatting-event-not-raised-if-tooltip-is-shown) | 3,1 |
| [Formant. DefaultFont został zmieniony na Segoe UI 9 pt](#default-control-font-changed-to-segoe-ui-9-pt) | 3.0 |
| [Modernizacja FolderBrowserDialog](#modernization-of-the-folderbrowserdialog) | 3.0 |
| [SerializableAttribute usunięte z niektórych typów Windows Forms](#serializableattribute-removed-from-some-windows-forms-types) | 3.0 |
| [Nieobsługiwany przełącznik zgodności AllowUpdateChildControlIndexForTabControls](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | 3.0 |
| [Przełącznik zgodności DomainUpDown. UseLegacyScrolling nie jest obsługiwany](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | 3.0 |
| [Nieobsługiwany przełącznik zgodności DoNotLoadLatestRichEditControl](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | 3.0 |
| [Nieobsługiwany przełącznik zgodności DoNotSupportSelectAllShortcutInMultilineTextBox](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | 3.0 |
| [Nieobsługiwany przełącznik zgodności DontSupportReentrantFilterMessage](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | 3.0 |
| [Nieobsługiwany przełącznik zgodności EnableVisualStyleValidation](#enablevisualstylevalidation-compatibility-switch-not-supported) | 3.0 |
| [Nieobsługiwany przełącznik zgodności UseLegacyContextMenuStripSourceControlValue](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | 3.0 |
| [Nieobsługiwany przełącznik zgodności UseLegacyImages](#uselegacyimages-compatibility-switch-not-supported) | 3.0 |

## <a name="net-50"></a>.NET 5,0

[!INCLUDE [modifystring-field-of-textformatflags-obsolete](../../../includes/core-changes/windowsforms/5.0/modifystring-field-of-textformatflags-obsolete.md)]

***

[!INCLUDE [datagridview-doesnt-reset-custom-font-settings](../../../includes/core-changes/windowsforms/5.0/datagridview-doesnt-reset-custom-font-settings.md)]

**_

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

## <a name="net-core-31"></a>.NET Core 3,1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

_*_

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

_*_

## <a name="net-core-30"></a>.NET Core 3.0

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

_**

## <a name="see-also"></a>Zobacz też

- [Port aplikacji Windows Forms do programu .NET Core](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)
