---
title: Istotne zmiany — .NET Framework do platformy .NET Core
titleSuffix: ''
description: Wyświetla listę istotnych zmian z .NET Framework do programu .NET Core 1,0-3,1.
ms.date: 05/05/2020
ms.openlocfilehash: 5904a359813b6d07bd2a27d882ade4395efe3256
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656369"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a><span data-ttu-id="5027a-103">Istotne zmiany dotyczące migracji z .NET Framework do platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="5027a-103">Breaking changes for migration from .NET Framework to .NET Core</span></span>

<span data-ttu-id="5027a-104">Jeśli migrujesz aplikację z .NET Framework do programu .NET Core w wersji 1,0 do 3,1, istotne zmiany wymienione w tym artykule mogą mieć wpływ na użytkownika.</span><span class="sxs-lookup"><span data-stu-id="5027a-104">If you're migrating an app from .NET Framework to .NET Core versions 1.0 through 3.1, the breaking changes listed in this article may affect you.</span></span> <span data-ttu-id="5027a-105">Istotne zmiany są pogrupowane według kategorii i w ramach tych kategorii według wersji platformy .NET Core, w której zostały wprowadzone.</span><span class="sxs-lookup"><span data-stu-id="5027a-105">Breaking changes are grouped by category, and within those categories, by the version of .NET Core in which they were introduced.</span></span>

> [!NOTE]
> <span data-ttu-id="5027a-106">Ten artykuł nie jest pełną listą istotnych zmian między .NET Framework i .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5027a-106">This article is not a complete list of breaking changes between .NET Framework and .NET Core.</span></span> <span data-ttu-id="5027a-107">Najważniejsze zmiany zostaną dodane w tym miejscu w miarę ich istnienia.</span><span class="sxs-lookup"><span data-stu-id="5027a-107">The most important breaking changes are added here as we become aware of them.</span></span>

## <a name="core-net-libraries"></a><span data-ttu-id="5027a-108">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="5027a-108">Core .NET libraries</span></span>

- [<span data-ttu-id="5027a-109">Zmień wartość domyślną UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="5027a-109">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute)
- [<span data-ttu-id="5027a-110">UnauthorizedAccessException zgłoszone przez FileSystemInfo. Attributes</span><span class="sxs-lookup"><span data-stu-id="5027a-110">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes)
- [<span data-ttu-id="5027a-111">Obsługa wyjątków uszkodzonego stanu procesu nie jest obsługiwana</span><span class="sxs-lookup"><span data-stu-id="5027a-111">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported)
- [<span data-ttu-id="5027a-112">Właściwości UriBuilder nie dołączają już znaków wiodących</span><span class="sxs-lookup"><span data-stu-id="5027a-112">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters)
- [<span data-ttu-id="5027a-113">Proces. element StartInfo zgłasza InvalidOperationException dla procesów, które nie zostały uruchomione</span><span class="sxs-lookup"><span data-stu-id="5027a-113">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start)

### <a name="net-core-21"></a><span data-ttu-id="5027a-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5027a-114">.NET Core 2.1</span></span>

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

### <a name="net-core-10"></a><span data-ttu-id="5027a-115">.NET Core 1,0</span><span class="sxs-lookup"><span data-stu-id="5027a-115">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***

## <a name="cryptography"></a><span data-ttu-id="5027a-116">Kryptografia</span><span class="sxs-lookup"><span data-stu-id="5027a-116">Cryptography</span></span>

- [<span data-ttu-id="5027a-117">Parametr logiczny elementu SignedCms. ComputeSignature jest przestrzegany</span><span class="sxs-lookup"><span data-stu-id="5027a-117">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected)

### <a name="net-core-21"></a><span data-ttu-id="5027a-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5027a-118">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***

## <a name="msbuild"></a><span data-ttu-id="5027a-119">MSBuild</span><span class="sxs-lookup"><span data-stu-id="5027a-119">MSBuild</span></span>

- [<span data-ttu-id="5027a-120">Zmiana nazwy pliku manifestu zasobu</span><span class="sxs-lookup"><span data-stu-id="5027a-120">Resource manifest file name change</span></span>](#resource-manifest-file-name-change)

### <a name="net-core-30"></a><span data-ttu-id="5027a-121">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="5027a-121">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***

## <a name="networking"></a><span data-ttu-id="5027a-122">Networking</span><span class="sxs-lookup"><span data-stu-id="5027a-122">Networking</span></span>

- [<span data-ttu-id="5027a-123">Klient WebClient. CancelAsync nie zawsze anuluje natychmiast</span><span class="sxs-lookup"><span data-stu-id="5027a-123">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately)

### <a name="net-core-20"></a><span data-ttu-id="5027a-124">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="5027a-124">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***

## <a name="windows-forms"></a><span data-ttu-id="5027a-125">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5027a-125">Windows Forms</span></span>

<span data-ttu-id="5027a-126">Obsługa Windows Forms została dodana do programu .NET Core w wersji 3,0.</span><span class="sxs-lookup"><span data-stu-id="5027a-126">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="5027a-127">W przypadku migrowania aplikacji Windows Forms z .NET Framework do platformy .NET Core zmiany wymienione w tym miejscu mogą mieć wpływ na aplikację.</span><span class="sxs-lookup"><span data-stu-id="5027a-127">If you're migrating a Windows Forms app from .NET Framework to .NET Core, the breaking changes listed here may affect your app.</span></span>

- [<span data-ttu-id="5027a-128">Usunięte kontrolki</span><span class="sxs-lookup"><span data-stu-id="5027a-128">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="5027a-129">Zdarzenie CellFormatting nie zostało zgłoszone, jeśli jest wyświetlana etykietka narzędzia</span><span class="sxs-lookup"><span data-stu-id="5027a-129">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="5027a-130">Formant. DefaultFont został zmieniony na Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="5027a-130">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="5027a-131">Modernizacja FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="5027a-131">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="5027a-132">SerializableAttribute usunięte z niektórych typów Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5027a-132">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="5027a-133">Nieobsługiwany przełącznik zgodności AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="5027a-133">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="5027a-134">Przełącznik zgodności DomainUpDown. UseLegacyScrolling nie jest obsługiwany</span><span class="sxs-lookup"><span data-stu-id="5027a-134">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="5027a-135">Nieobsługiwany przełącznik zgodności DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="5027a-135">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="5027a-136">Nieobsługiwany przełącznik zgodności DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="5027a-136">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="5027a-137">Nieobsługiwany przełącznik zgodności DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="5027a-137">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="5027a-138">Nieobsługiwany przełącznik zgodności EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="5027a-138">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="5027a-139">Nieobsługiwany przełącznik zgodności UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="5027a-139">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="5027a-140">Nieobsługiwany przełącznik zgodności UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="5027a-140">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)

### <a name="net-core-31"></a><span data-ttu-id="5027a-141">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="5027a-141">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a><span data-ttu-id="5027a-142">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="5027a-142">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9 pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

## <a name="see-also"></a><span data-ttu-id="5027a-143">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5027a-143">See also</span></span>

- [<span data-ttu-id="5027a-144">Interfejsy API, które zawsze generują wyjątki w programie .NET Core</span><span class="sxs-lookup"><span data-stu-id="5027a-144">APIs that always throw exceptions on .NET Core</span></span>](unsupported-apis.md)
- [<span data-ttu-id="5027a-145">Technologie .NET Framework niedostępne w programie .NET Core</span><span class="sxs-lookup"><span data-stu-id="5027a-145">.NET Framework technologies unavailable on .NET Core</span></span>](../porting/net-framework-tech-unavailable.md)
