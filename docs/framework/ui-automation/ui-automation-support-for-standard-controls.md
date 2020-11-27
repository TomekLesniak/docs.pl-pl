---
title: Obsługa automatyzacji interfejsu użytkownika dla standardowych formantów
description: Uzyskaj informacje na temat obsługi automatyzacji interfejsu użytkownika dla standardowych kontrolek w aplikacjach utworzonych dla Windows Presentation Foundation (WPF), Win32 i Windows Forms.
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 0a5a0b61a6492d9efb62799fa610859b247cf26e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261075"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="0d8a6-103">Obsługa automatyzacji interfejsu użytkownika dla standardowych formantów</span><span class="sxs-lookup"><span data-stu-id="0d8a6-103">UI Automation Support for Standard Controls</span></span>

> [!NOTE]
> <span data-ttu-id="0d8a6-104">Ta dokumentacja jest przeznaczona dla .NET Framework deweloperów, którzy chcą korzystać z zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="0d8a6-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="0d8a6-105">Aby uzyskać najnowsze informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , zobacz [interfejs API usługi Windows Automation: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="0d8a6-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="0d8a6-106">Ten temat zawiera informacje o [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] obsłudze standardowych formantów w aplikacjach opracowanych dla [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] środowisk, Win32 i Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0d8a6-106">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>

## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="0d8a6-107">Kontrolki Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="0d8a6-107">Windows Presentation Foundation Controls</span></span>  

 <span data-ttu-id="0d8a6-108">Wszystkie [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] elementy sterujące, które dostarczają informacji lub pomocy technicznej dla interakcji użytkownika, mają pełną obsługę natywną [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d8a6-108">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="0d8a6-109">Inne elementy, takie jak panele, nie są widoczne dla programu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d8a6-109">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>

## <a name="win32-controls"></a><span data-ttu-id="0d8a6-110">Kontrolki Win32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-110">Win32 Controls</span></span>  

 <span data-ttu-id="0d8a6-111">Większość formantów Win32 jest narażonych [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] przez dostawców po stronie klienta w UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="0d8a6-111">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="0d8a6-112">Ten zestaw jest automatycznie rejestrowany do użytku z aplikacjami klienckimi automatyzacji interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0d8a6-112">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="0d8a6-113">Pełna pomoc techniczna jest świadczona tylko w przypadku formantów z wersji 6 programu *ComCtrl32.dll*.</span><span class="sxs-lookup"><span data-stu-id="0d8a6-113">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="0d8a6-114">Obsługiwane są następujące kontrolki.</span><span class="sxs-lookup"><span data-stu-id="0d8a6-114">The following controls are supported.</span></span>  
  
|<span data-ttu-id="0d8a6-115">Nazwa klasy</span><span class="sxs-lookup"><span data-stu-id="0d8a6-115">Class name</span></span>|<span data-ttu-id="0d8a6-116">Typ formantu</span><span class="sxs-lookup"><span data-stu-id="0d8a6-116">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="0d8a6-117">Przycisk</span><span class="sxs-lookup"><span data-stu-id="0d8a6-117">Button</span></span>|<span data-ttu-id="0d8a6-118">Przycisk</span><span class="sxs-lookup"><span data-stu-id="0d8a6-118">Button</span></span>|  
|<span data-ttu-id="0d8a6-119">Przycisk</span><span class="sxs-lookup"><span data-stu-id="0d8a6-119">Button</span></span>|<span data-ttu-id="0d8a6-120">RadioButton</span><span class="sxs-lookup"><span data-stu-id="0d8a6-120">RadioButton</span></span>|  
|<span data-ttu-id="0d8a6-121">Przycisk</span><span class="sxs-lookup"><span data-stu-id="0d8a6-121">Button</span></span>|<span data-ttu-id="0d8a6-122">Grupa</span><span class="sxs-lookup"><span data-stu-id="0d8a6-122">Group</span></span>|  
|<span data-ttu-id="0d8a6-123">Przycisk</span><span class="sxs-lookup"><span data-stu-id="0d8a6-123">Button</span></span>|<span data-ttu-id="0d8a6-124">CheckBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-124">CheckBox</span></span>|  
|<span data-ttu-id="0d8a6-125">Przycisk</span><span class="sxs-lookup"><span data-stu-id="0d8a6-125">Button</span></span>|<span data-ttu-id="0d8a6-126">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="0d8a6-126">Hyperlink</span></span>|  
|<span data-ttu-id="0d8a6-127">Przycisk</span><span class="sxs-lookup"><span data-stu-id="0d8a6-127">Button</span></span>|<span data-ttu-id="0d8a6-128">SplitButton</span><span class="sxs-lookup"><span data-stu-id="0d8a6-128">SplitButton</span></span>|  
|<span data-ttu-id="0d8a6-129">Przycisk</span><span class="sxs-lookup"><span data-stu-id="0d8a6-129">Button</span></span>|<span data-ttu-id="0d8a6-130">CheckBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-130">CheckBox</span></span>|  
|<span data-ttu-id="0d8a6-131">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-131">ComboBoxEx32</span></span>|<span data-ttu-id="0d8a6-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-132">ComboBox</span></span>|  
|<span data-ttu-id="0d8a6-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-133">ComboBox</span></span>|<span data-ttu-id="0d8a6-134">ComboBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-134">ComboBox</span></span>|  
|<span data-ttu-id="0d8a6-135">Edytuj</span><span class="sxs-lookup"><span data-stu-id="0d8a6-135">Edit</span></span>|<span data-ttu-id="0d8a6-136">Dokument</span><span class="sxs-lookup"><span data-stu-id="0d8a6-136">Document</span></span>|  
|<span data-ttu-id="0d8a6-137">Edytuj</span><span class="sxs-lookup"><span data-stu-id="0d8a6-137">Edit</span></span>|<span data-ttu-id="0d8a6-138">Edytuj</span><span class="sxs-lookup"><span data-stu-id="0d8a6-138">Edit</span></span>|  
|<span data-ttu-id="0d8a6-139">SysLink</span><span class="sxs-lookup"><span data-stu-id="0d8a6-139">SysLink</span></span>|<span data-ttu-id="0d8a6-140">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="0d8a6-140">Hyperlink</span></span>|  
|<span data-ttu-id="0d8a6-141">Static</span><span class="sxs-lookup"><span data-stu-id="0d8a6-141">Static</span></span>|<span data-ttu-id="0d8a6-142">Tekst</span><span class="sxs-lookup"><span data-stu-id="0d8a6-142">Text</span></span>|  
|<span data-ttu-id="0d8a6-143">Static</span><span class="sxs-lookup"><span data-stu-id="0d8a6-143">Static</span></span>|<span data-ttu-id="0d8a6-144">Obraz</span><span class="sxs-lookup"><span data-stu-id="0d8a6-144">Image</span></span>|  
|<span data-ttu-id="0d8a6-145">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-145">SysIPAddress32</span></span>|<span data-ttu-id="0d8a6-146">Niestandardowy</span><span class="sxs-lookup"><span data-stu-id="0d8a6-146">Custom</span></span>|  
|<span data-ttu-id="0d8a6-147">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-147">SysHeader32</span></span>|<span data-ttu-id="0d8a6-148">Nagłówek/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="0d8a6-148">Header/HeaderItem</span></span>|  
|<span data-ttu-id="0d8a6-149">SysListView32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-149">SysListView32</span></span>|<span data-ttu-id="0d8a6-150">DataGrid</span><span class="sxs-lookup"><span data-stu-id="0d8a6-150">DataGrid</span></span>|  
|<span data-ttu-id="0d8a6-151">SysListView32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-151">SysListView32</span></span>|<span data-ttu-id="0d8a6-152">Lista</span><span class="sxs-lookup"><span data-stu-id="0d8a6-152">List</span></span>|  
|<span data-ttu-id="0d8a6-153">ListBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-153">ListBox</span></span>|<span data-ttu-id="0d8a6-154">Lista</span><span class="sxs-lookup"><span data-stu-id="0d8a6-154">List</span></span>|  
|<span data-ttu-id="0d8a6-155">ListBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-155">ListBox</span></span>|<span data-ttu-id="0d8a6-156">Metodę</span><span class="sxs-lookup"><span data-stu-id="0d8a6-156">ListItem</span></span>|  
|<span data-ttu-id="0d8a6-157">#32768</span><span class="sxs-lookup"><span data-stu-id="0d8a6-157">#32768</span></span>|<span data-ttu-id="0d8a6-158">Menu</span><span class="sxs-lookup"><span data-stu-id="0d8a6-158">Menu</span></span>|  
|<span data-ttu-id="0d8a6-159">#32768</span><span class="sxs-lookup"><span data-stu-id="0d8a6-159">#32768</span></span>|<span data-ttu-id="0d8a6-160">MenuItem</span><span class="sxs-lookup"><span data-stu-id="0d8a6-160">MenuItem</span></span>|  
|<span data-ttu-id="0d8a6-161">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-161">msctls_progress32</span></span>|<span data-ttu-id="0d8a6-162">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="0d8a6-162">ProgressBar</span></span>|  
|<span data-ttu-id="0d8a6-163">RichEdit</span><span class="sxs-lookup"><span data-stu-id="0d8a6-163">RichEdit</span></span>|<span data-ttu-id="0d8a6-164">Dokumentu.</span><span class="sxs-lookup"><span data-stu-id="0d8a6-164">Document.</span></span> <span data-ttu-id="0d8a6-165">Zobacz Uwaga.</span><span class="sxs-lookup"><span data-stu-id="0d8a6-165">See note.</span></span>|  
|<span data-ttu-id="0d8a6-166">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="0d8a6-166">RichEdit20A</span></span>|<span data-ttu-id="0d8a6-167">Dokument</span><span class="sxs-lookup"><span data-stu-id="0d8a6-167">Document</span></span>|  
|<span data-ttu-id="0d8a6-168">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="0d8a6-168">RichEdit20W</span></span>|<span data-ttu-id="0d8a6-169">Dokument</span><span class="sxs-lookup"><span data-stu-id="0d8a6-169">Document</span></span>|  
|<span data-ttu-id="0d8a6-170">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="0d8a6-170">RichEdit50W</span></span>|<span data-ttu-id="0d8a6-171">Dokument</span><span class="sxs-lookup"><span data-stu-id="0d8a6-171">Document</span></span>|  
|<span data-ttu-id="0d8a6-172">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="0d8a6-172">ScrollBar</span></span>|<span data-ttu-id="0d8a6-173">Suwak</span><span class="sxs-lookup"><span data-stu-id="0d8a6-173">Slider</span></span>|  
|<span data-ttu-id="0d8a6-174">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-174">msctls_trackbar32</span></span>|<span data-ttu-id="0d8a6-175">Suwak</span><span class="sxs-lookup"><span data-stu-id="0d8a6-175">Slider</span></span>|  
|<span data-ttu-id="0d8a6-176">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-176">msctls_updown32</span></span>|<span data-ttu-id="0d8a6-177">pokrętło</span><span class="sxs-lookup"><span data-stu-id="0d8a6-177">Spinner</span></span>|  
|<span data-ttu-id="0d8a6-178">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-178">msctls_statusbar32</span></span>|<span data-ttu-id="0d8a6-179">StatusBar</span><span class="sxs-lookup"><span data-stu-id="0d8a6-179">StatusBar</span></span>|  
|<span data-ttu-id="0d8a6-180">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-180">SysTabControl32</span></span>|<span data-ttu-id="0d8a6-181">Tab</span><span class="sxs-lookup"><span data-stu-id="0d8a6-181">Tab</span></span>|  
|<span data-ttu-id="0d8a6-182">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-182">SysTabControl32</span></span>|<span data-ttu-id="0d8a6-183">TabItem</span><span class="sxs-lookup"><span data-stu-id="0d8a6-183">TabItem</span></span>|  
|<span data-ttu-id="0d8a6-184">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-184">ToolbarWindow32</span></span>|<span data-ttu-id="0d8a6-185">ToolBar</span><span class="sxs-lookup"><span data-stu-id="0d8a6-185">ToolBar</span></span>|  
|<span data-ttu-id="0d8a6-186">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-186">ToolbarWindow32</span></span>|<span data-ttu-id="0d8a6-187">MenuItem</span><span class="sxs-lookup"><span data-stu-id="0d8a6-187">MenuItem</span></span>|  
|<span data-ttu-id="0d8a6-188">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-188">ToolbarWindow32</span></span>|<span data-ttu-id="0d8a6-189">Przycisk</span><span class="sxs-lookup"><span data-stu-id="0d8a6-189">Button</span></span>|  
|<span data-ttu-id="0d8a6-190">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-190">ToolbarWindow32</span></span>|<span data-ttu-id="0d8a6-191">CheckBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-191">CheckBox</span></span>|  
|<span data-ttu-id="0d8a6-192">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-192">ToolbarWindow32</span></span>|<span data-ttu-id="0d8a6-193">RadioButton</span><span class="sxs-lookup"><span data-stu-id="0d8a6-193">RadioButton</span></span>|  
|<span data-ttu-id="0d8a6-194">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-194">ToolbarWindow32</span></span>|<span data-ttu-id="0d8a6-195">Separator</span><span class="sxs-lookup"><span data-stu-id="0d8a6-195">Separator</span></span>|  
|<span data-ttu-id="0d8a6-196">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-196">tooltips_class32</span></span>|<span data-ttu-id="0d8a6-197">ToolTip</span><span class="sxs-lookup"><span data-stu-id="0d8a6-197">ToolTip</span></span>|  
|<span data-ttu-id="0d8a6-198">#32774</span><span class="sxs-lookup"><span data-stu-id="0d8a6-198">#32774</span></span>|<span data-ttu-id="0d8a6-199">ToolTip</span><span class="sxs-lookup"><span data-stu-id="0d8a6-199">ToolTip</span></span>|  
|<span data-ttu-id="0d8a6-200">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-200">ReBarWindow32</span></span>|<span data-ttu-id="0d8a6-201">Pasek narzędzi</span><span class="sxs-lookup"><span data-stu-id="0d8a6-201">Toolbar</span></span>|  
|<span data-ttu-id="0d8a6-202">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-202">SysTreeView32</span></span>|<span data-ttu-id="0d8a6-203">Drzewo</span><span class="sxs-lookup"><span data-stu-id="0d8a6-203">Tree</span></span>|  
|<span data-ttu-id="0d8a6-204">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-204">SysTreeView32</span></span>|<span data-ttu-id="0d8a6-205">TreeItem</span><span class="sxs-lookup"><span data-stu-id="0d8a6-205">TreeItem</span></span>|  
  
 <span data-ttu-id="0d8a6-206">**Uwaga** Formant RichEdit jest obsługiwany tylko w przypadku wersji dostarczonych z systemem Windows Vista (w RichEd20.dll w wersji 3,1 lub nowszej oraz MsftEdit.dll wersji 4,1 i nowszych).</span><span class="sxs-lookup"><span data-stu-id="0d8a6-206">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="0d8a6-207">Następujące kontrolki nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="0d8a6-207">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="0d8a6-208">Nazwa klasy</span><span class="sxs-lookup"><span data-stu-id="0d8a6-208">Class name</span></span>|<span data-ttu-id="0d8a6-209">Typ kontrolki</span><span class="sxs-lookup"><span data-stu-id="0d8a6-209">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="0d8a6-210">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-210">SysAnimate32</span></span>|<span data-ttu-id="0d8a6-211">Obraz</span><span class="sxs-lookup"><span data-stu-id="0d8a6-211">Image</span></span>|  
|<span data-ttu-id="0d8a6-212">SysPager</span><span class="sxs-lookup"><span data-stu-id="0d8a6-212">SysPager</span></span>|<span data-ttu-id="0d8a6-213">pokrętło</span><span class="sxs-lookup"><span data-stu-id="0d8a6-213">Spinner</span></span>|  
|<span data-ttu-id="0d8a6-214">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-214">SysDateTimePick32</span></span>|<span data-ttu-id="0d8a6-215">Niestandardowy</span><span class="sxs-lookup"><span data-stu-id="0d8a6-215">Custom</span></span>|  
|<span data-ttu-id="0d8a6-216">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="0d8a6-216">SysMonthCal32</span></span>|<span data-ttu-id="0d8a6-217">Kalendarz</span><span class="sxs-lookup"><span data-stu-id="0d8a6-217">Calendar</span></span>|  
|<span data-ttu-id="0d8a6-218">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="0d8a6-218">MS_WINNOTE</span></span>|<span data-ttu-id="0d8a6-219">Etykietka narzędzia</span><span class="sxs-lookup"><span data-stu-id="0d8a6-219">Tooltip</span></span>|  
|<span data-ttu-id="0d8a6-220">VBBubble</span><span class="sxs-lookup"><span data-stu-id="0d8a6-220">VBBubble</span></span>|<span data-ttu-id="0d8a6-221">Etykietka narzędzia</span><span class="sxs-lookup"><span data-stu-id="0d8a6-221">Tooltip</span></span>|  
|<span data-ttu-id="0d8a6-222">Pasek przewijania (używany jako formant autonomiczny)</span><span class="sxs-lookup"><span data-stu-id="0d8a6-222">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="0d8a6-223">Suwak</span><span class="sxs-lookup"><span data-stu-id="0d8a6-223">Slider</span></span>|  
|<span data-ttu-id="0d8a6-224">Podsiatka</span><span class="sxs-lookup"><span data-stu-id="0d8a6-224">SuperGrid</span></span>|<span data-ttu-id="0d8a6-225">Niestandardowy</span><span class="sxs-lookup"><span data-stu-id="0d8a6-225">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>

## <a name="windows-forms-controls"></a><span data-ttu-id="0d8a6-226">Formanty formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="0d8a6-226">Windows Forms Controls</span></span>  

 <span data-ttu-id="0d8a6-227">Kontrolki Windows Forms są dostępne dla [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] dostawców po stronie klienta w programie UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="0d8a6-227">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="0d8a6-228">Ten zestaw jest automatycznie rejestrowany do użytku z aplikacjami klienckimi automatyzacji interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0d8a6-228">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="0d8a6-229">Zazwyczaj formanty Windows Forms, które są otokami zarządzanymi dla formantów standardowych Win32, są obsługiwane przez program [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d8a6-229">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="0d8a6-230">Obsługiwane są następujące kontrolki.</span><span class="sxs-lookup"><span data-stu-id="0d8a6-230">The following controls are supported.</span></span>  
  
|<span data-ttu-id="0d8a6-231">Nazwa klasy</span><span class="sxs-lookup"><span data-stu-id="0d8a6-231">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="0d8a6-232">Przycisk</span><span class="sxs-lookup"><span data-stu-id="0d8a6-232">Button</span></span>|  
|<span data-ttu-id="0d8a6-233">CheckBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-233">CheckBox</span></span>|  
|<span data-ttu-id="0d8a6-234">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-234">CheckedListBox</span></span>|  
|<span data-ttu-id="0d8a6-235">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="0d8a6-235">ColorDialog</span></span>|  
|<span data-ttu-id="0d8a6-236">ComboBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-236">ComboBox</span></span>|  
|<span data-ttu-id="0d8a6-237">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="0d8a6-237">FolderBrowser</span></span>|  
|<span data-ttu-id="0d8a6-238">FontDialog</span><span class="sxs-lookup"><span data-stu-id="0d8a6-238">FontDialog</span></span>|  
|<span data-ttu-id="0d8a6-239">GroupBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-239">GroupBox</span></span>|  
|<span data-ttu-id="0d8a6-240">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="0d8a6-240">HscrollBar</span></span>|  
|<span data-ttu-id="0d8a6-241">Obrazów</span><span class="sxs-lookup"><span data-stu-id="0d8a6-241">ImageList</span></span>|  
|<span data-ttu-id="0d8a6-242">Etykieta</span><span class="sxs-lookup"><span data-stu-id="0d8a6-242">Label</span></span>|  
|<span data-ttu-id="0d8a6-243">ListBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-243">ListBox</span></span>|  
|<span data-ttu-id="0d8a6-244">ListView</span><span class="sxs-lookup"><span data-stu-id="0d8a6-244">ListView</span></span>|  
|<span data-ttu-id="0d8a6-245">MainMenu/</span><span class="sxs-lookup"><span data-stu-id="0d8a6-245">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="0d8a6-246">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="0d8a6-246">MonthCalendar</span></span>|  
|<span data-ttu-id="0d8a6-247">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="0d8a6-247">NotifyIcon</span></span>|  
|<span data-ttu-id="0d8a6-248">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="0d8a6-248">OpenFileDialog</span></span>|  
|<span data-ttu-id="0d8a6-249">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="0d8a6-249">PageSetupDialog</span></span>|  
|<span data-ttu-id="0d8a6-250">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="0d8a6-250">PrintDialog</span></span>|  
|<span data-ttu-id="0d8a6-251">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="0d8a6-251">ProgressBar</span></span>|  
|<span data-ttu-id="0d8a6-252">RadioButton</span><span class="sxs-lookup"><span data-stu-id="0d8a6-252">RadioButton</span></span>|  
|<span data-ttu-id="0d8a6-253">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-253">RichTextBox</span></span>|  
|<span data-ttu-id="0d8a6-254">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="0d8a6-254">SaveFileDialog</span></span>|  
|<span data-ttu-id="0d8a6-255">Elementu ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="0d8a6-255">ScrollableControl</span></span>|  
|<span data-ttu-id="0d8a6-256">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="0d8a6-256">SoundPlayer</span></span>|  
|<span data-ttu-id="0d8a6-257">StatusBar</span><span class="sxs-lookup"><span data-stu-id="0d8a6-257">StatusBar</span></span>|  
|<span data-ttu-id="0d8a6-258">Elementy TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="0d8a6-258">TabControl/TabPage</span></span>|  
|<span data-ttu-id="0d8a6-259">TextBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-259">TextBox</span></span>|  
|<span data-ttu-id="0d8a6-260">Czasomierz</span><span class="sxs-lookup"><span data-stu-id="0d8a6-260">Timer</span></span>|  
|<span data-ttu-id="0d8a6-261">Pasek narzędzi</span><span class="sxs-lookup"><span data-stu-id="0d8a6-261">Toolbar</span></span>|  
|<span data-ttu-id="0d8a6-262">ToolTip</span><span class="sxs-lookup"><span data-stu-id="0d8a6-262">ToolTip</span></span>|  
|<span data-ttu-id="0d8a6-263">TrackBar</span><span class="sxs-lookup"><span data-stu-id="0d8a6-263">TrackBar</span></span>|  
|<span data-ttu-id="0d8a6-264">TreeView</span><span class="sxs-lookup"><span data-stu-id="0d8a6-264">TreeView</span></span>|  
|<span data-ttu-id="0d8a6-265">VScrollBar —</span><span class="sxs-lookup"><span data-stu-id="0d8a6-265">VscrollBar</span></span>|  
|<span data-ttu-id="0d8a6-266">Kontrol</span><span class="sxs-lookup"><span data-stu-id="0d8a6-266">WebBrowser</span></span>|  
  
 <span data-ttu-id="0d8a6-267">Następujące kontrolki są dostępne [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tylko w ramach obsługi usługi Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="0d8a6-267">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="0d8a6-268">Niektóre funkcje mogą być niedostępne.</span><span class="sxs-lookup"><span data-stu-id="0d8a6-268">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="0d8a6-269">Nazwa kontrolki</span><span class="sxs-lookup"><span data-stu-id="0d8a6-269">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="0d8a6-270">BindingSource</span><span class="sxs-lookup"><span data-stu-id="0d8a6-270">BindingSource</span></span>|  
|<span data-ttu-id="0d8a6-271">DataGrid</span><span class="sxs-lookup"><span data-stu-id="0d8a6-271">DataGrid</span></span>|  
|<span data-ttu-id="0d8a6-272">DataGridView</span><span class="sxs-lookup"><span data-stu-id="0d8a6-272">DataGridView</span></span>|  
|<span data-ttu-id="0d8a6-273">Nawigator datanavigator</span><span class="sxs-lookup"><span data-stu-id="0d8a6-273">DataNavigator</span></span>|  
|<span data-ttu-id="0d8a6-274">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="0d8a6-274">DomainUpDown</span></span>|  
|<span data-ttu-id="0d8a6-275">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="0d8a6-275">ErrorProvider</span></span>|  
|<span data-ttu-id="0d8a6-276">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0d8a6-276">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="0d8a6-277">Formularz</span><span class="sxs-lookup"><span data-stu-id="0d8a6-277">Form</span></span>|  
|<span data-ttu-id="0d8a6-278">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="0d8a6-278">LinkLabel</span></span>|  
|<span data-ttu-id="0d8a6-279">HelpProvider —</span><span class="sxs-lookup"><span data-stu-id="0d8a6-279">HelpProvider</span></span>|  
|<span data-ttu-id="0d8a6-280">Formantem MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="0d8a6-280">MaskedTextBox</span></span>|  
|<span data-ttu-id="0d8a6-281">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="0d8a6-281">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="0d8a6-282">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="0d8a6-282">NumericUpDown</span></span>|  
|<span data-ttu-id="0d8a6-283">Panel</span><span class="sxs-lookup"><span data-stu-id="0d8a6-283">Panel</span></span>|  
|<span data-ttu-id="0d8a6-284">Elemencie</span><span class="sxs-lookup"><span data-stu-id="0d8a6-284">PictureBox</span></span>|  
|<span data-ttu-id="0d8a6-285">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="0d8a6-285">PrintDocument</span></span>|  
|<span data-ttu-id="0d8a6-286">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="0d8a6-286">PrintPreview-Control</span></span>|  
|<span data-ttu-id="0d8a6-287">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="0d8a6-287">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="0d8a6-288">Używany</span><span class="sxs-lookup"><span data-stu-id="0d8a6-288">PropertyGrid</span></span>|  
|<span data-ttu-id="0d8a6-289">UserControl</span><span class="sxs-lookup"><span data-stu-id="0d8a6-289">UserControl</span></span>|  
|<span data-ttu-id="0d8a6-290">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="0d8a6-290">ToolStrip</span></span>|  
|<span data-ttu-id="0d8a6-291">Element TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0d8a6-291">TableLayoutPanel</span></span>|  
|<span data-ttu-id="0d8a6-292">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="0d8a6-292">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="0d8a6-293">Rozdzielacz</span><span class="sxs-lookup"><span data-stu-id="0d8a6-293">Splitter</span></span>|  
|<span data-ttu-id="0d8a6-294">Elemencie RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="0d8a6-294">RaftingContainer</span></span>|  
|<span data-ttu-id="0d8a6-295">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="0d8a6-295">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0d8a6-296">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0d8a6-296">See also</span></span>

- [<span data-ttu-id="0d8a6-297">Typy formantów automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="0d8a6-297">UI Automation Control Types</span></span>](ui-automation-control-types.md)
