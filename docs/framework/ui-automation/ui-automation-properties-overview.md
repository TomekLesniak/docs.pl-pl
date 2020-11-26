---
title: Przegląd właściwości automatyzacji interfejsu użytkownika
description: Zobacz szeroki przegląd właściwości automatyzacji interfejsu użytkownika firmy Microsoft. Dowiedz się więcej na temat identyfikatorów właściwości, właściwości według kategorii, lokalizacji i właściwości i zdarzeń.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, properties
- properties, UI Automation
ms.assetid: a6c31d7b-b33e-49b3-b5c1-31a345f9b7c8
ms.openlocfilehash: 95729c1d26a9ae7fdec4fa4215f9478251612242
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240397"
---
# <a name="ui-automation-properties-overview"></a><span data-ttu-id="e8883-104">Przegląd właściwości automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="e8883-104">UI Automation Properties Overview</span></span>

> [!NOTE]
> <span data-ttu-id="e8883-105">Ta dokumentacja jest przeznaczona dla .NET Framework deweloperów, którzy chcą korzystać z zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="e8883-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e8883-106">Aby uzyskać najnowsze informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , zobacz [interfejs API usługi Windows Automation: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="e8883-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="e8883-107">Dostawcy automatyzacji interfejsu użytkownika uwidaczniają właściwości w [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elementach.</span><span class="sxs-lookup"><span data-stu-id="e8883-107">UI Automation providers expose properties on [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements.</span></span> <span data-ttu-id="e8883-108">Te właściwości umożliwiają aplikacjom klienckim automatyzacji interfejsu użytkownika odnajdywanie informacji o fragmentach [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] , zwłaszcza formantów, włącznie z danymi statycznymi i dynamicznymi.</span><span class="sxs-lookup"><span data-stu-id="e8883-108">These properties enable UI Automation client applications to discover information about pieces of the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], especially controls, including both static and dynamic data.</span></span>  
  
 <span data-ttu-id="e8883-109">Ta sekcja zawiera obszerne omówienie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] właściwości.</span><span class="sxs-lookup"><span data-stu-id="e8883-109">This section gives a broad overview of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] properties.</span></span> <span data-ttu-id="e8883-110">Bardziej szczegółowe informacje znajdują się w następujących tematach:</span><span class="sxs-lookup"><span data-stu-id="e8883-110">More specific information is given in the following topics:</span></span>  
  
- [<span data-ttu-id="e8883-111">Właściwości automatyzacji interfejsu użytkownika dla klientów</span><span class="sxs-lookup"><span data-stu-id="e8883-111">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)  
  
- [<span data-ttu-id="e8883-112">Implementacja dostawcy automatyzacji interfejsu użytkownika po stronie serwera</span><span class="sxs-lookup"><span data-stu-id="e8883-112">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)  
  
<a name="Property_Identifiers"></a>

## <a name="property-identifiers"></a><span data-ttu-id="e8883-113">Identyfikatory właściwości</span><span class="sxs-lookup"><span data-stu-id="e8883-113">Property Identifiers</span></span>  

 <span data-ttu-id="e8883-114">Każda właściwość jest identyfikowana przez liczbę i nazwę.</span><span class="sxs-lookup"><span data-stu-id="e8883-114">Every property is identified by a number and a name.</span></span> <span data-ttu-id="e8883-115">Nazwy właściwości są używane tylko do debugowania i diagnostyki.</span><span class="sxs-lookup"><span data-stu-id="e8883-115">The names of properties are used only for debugging and diagnosis.</span></span> <span data-ttu-id="e8883-116">Dostawcy używają identyfikatorów liczbowych do identyfikowania przychodzących żądań właściwości.</span><span class="sxs-lookup"><span data-stu-id="e8883-116">Providers use the numeric IDs to identify incoming property requests.</span></span> <span data-ttu-id="e8883-117">Jednak aplikacje klienckie, <xref:System.Windows.Automation.AutomationProperty> które hermetyzują liczbę i nazwę, identyfikują właściwości, które chcą pobrać.</span><span class="sxs-lookup"><span data-stu-id="e8883-117">Client applications, however, only use <xref:System.Windows.Automation.AutomationProperty>, which encapsulates the number and name, to identify properties they wish to retrieve.</span></span>  
  
 <span data-ttu-id="e8883-118"><xref:System.Windows.Automation.AutomationProperty> obiekty reprezentujące określone właściwości są dostępne jako pola w różnych klasach.</span><span class="sxs-lookup"><span data-stu-id="e8883-118"><xref:System.Windows.Automation.AutomationProperty> objects representing particular properties are available as fields in various classes.</span></span> <span data-ttu-id="e8883-119">Ze względów bezpieczeństwa dostawcy automatyzacji interfejsu użytkownika uzyskują te obiekty z oddzielnego zestawu klas, które znajdują się w Uiautomationtypes.dll.</span><span class="sxs-lookup"><span data-stu-id="e8883-119">For security reasons, UI Automation providers obtain these objects from a separate set of classes that are contained in Uiautomationtypes.dll.</span></span>  
  
 <span data-ttu-id="e8883-120">Poniższa tabela zawiera kategorie właściwości według klas, które zawierają <xref:System.Windows.Automation.AutomationProperty> identyfikatory.</span><span class="sxs-lookup"><span data-stu-id="e8883-120">The following table categorizes properties by the classes that contain the <xref:System.Windows.Automation.AutomationProperty>IDs.</span></span>  
  
|<span data-ttu-id="e8883-121">Rodzaje właściwości</span><span class="sxs-lookup"><span data-stu-id="e8883-121">Kinds of properties</span></span>|<span data-ttu-id="e8883-122">Klienci otrzymują identyfikatory z</span><span class="sxs-lookup"><span data-stu-id="e8883-122">Clients get IDs from</span></span>|<span data-ttu-id="e8883-123">Dostawcy pobierają identyfikatory z</span><span class="sxs-lookup"><span data-stu-id="e8883-123">Providers get IDs from</span></span>|  
|-------------------------|--------------------------|----------------------------|  
|<span data-ttu-id="e8883-124">Właściwości wspólne dla wszystkich elementów (zobacz następujące tabele)</span><span class="sxs-lookup"><span data-stu-id="e8883-124">Properties common to all elements (see following tables)</span></span>|<xref:System.Windows.Automation.AutomationElement>|<xref:System.Windows.Automation.AutomationElementIdentifiers>|  
|<span data-ttu-id="e8883-125">Pozycja okna dokującego</span><span class="sxs-lookup"><span data-stu-id="e8883-125">Position of a docking window</span></span>|<xref:System.Windows.Automation.DockPattern>|<xref:System.Windows.Automation.DockPatternIdentifiers>|  
|<span data-ttu-id="e8883-126">Stan elementu, który można rozwinąć i zwinąć</span><span class="sxs-lookup"><span data-stu-id="e8883-126">State of an element that can expand and collapse</span></span>|<xref:System.Windows.Automation.ExpandCollapsePattern>|<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers>|  
|<span data-ttu-id="e8883-127">Właściwości elementu w siatce</span><span class="sxs-lookup"><span data-stu-id="e8883-127">Properties of an item in a grid</span></span>|<xref:System.Windows.Automation.GridItemPattern>|<xref:System.Windows.Automation.GridItemPatternIdentifiers>|  
|<span data-ttu-id="e8883-128">Właściwości siatki</span><span class="sxs-lookup"><span data-stu-id="e8883-128">Properties of a grid</span></span>|<xref:System.Windows.Automation.GridPattern>|<xref:System.Windows.Automation.GridPatternIdentifiers>|  
|<span data-ttu-id="e8883-129">Bieżący i obsługiwany widok elementu, który ma wiele widoków</span><span class="sxs-lookup"><span data-stu-id="e8883-129">Current and supported view of an element that has multiple views</span></span>|<xref:System.Windows.Automation.MultipleViewPattern>|<xref:System.Windows.Automation.MultipleViewPatternIdentifiers>|  
|<span data-ttu-id="e8883-130">Właściwości elementu, który przenosi się na zakres wartości, na przykład suwak</span><span class="sxs-lookup"><span data-stu-id="e8883-130">Properties of an element that moves over a range of values, such as a slider</span></span>|<xref:System.Windows.Automation.RangeValuePattern>|<xref:System.Windows.Automation.RangeValuePatternIdentifiers>|  
|<span data-ttu-id="e8883-131">Właściwości okna przewijania</span><span class="sxs-lookup"><span data-stu-id="e8883-131">Properties of a scrolling window</span></span>|<xref:System.Windows.Automation.ScrollPattern>|<xref:System.Windows.Automation.ScrollPatternIdentifiers>|  
|<span data-ttu-id="e8883-132">Stan i kontener elementu, który można wybrać, jak na liście</span><span class="sxs-lookup"><span data-stu-id="e8883-132">Status and container of an item that can be selected, as in a list</span></span>|<xref:System.Windows.Automation.SelectionItemPattern>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers>|  
|<span data-ttu-id="e8883-133">Właściwości kontrolki zawierającej elementy zaznaczenia</span><span class="sxs-lookup"><span data-stu-id="e8883-133">Properties of a control that contains selection items</span></span>|<xref:System.Windows.Automation.SelectionPattern>|<xref:System.Windows.Automation.SelectionPatternIdentifiers>|  
|<span data-ttu-id="e8883-134">Nagłówki kolumn i wierszy elementu w tabeli</span><span class="sxs-lookup"><span data-stu-id="e8883-134">Column and row headers of an item in a table</span></span>|<xref:System.Windows.Automation.TableItemPattern>|<xref:System.Windows.Automation.TableItemPatternIdentifiers>|  
|<span data-ttu-id="e8883-135">Nagłówki kolumn i wierszy oraz orientacja tabeli</span><span class="sxs-lookup"><span data-stu-id="e8883-135">Column and row headers, and orientation, of a table</span></span>|<xref:System.Windows.Automation.TablePattern>|<xref:System.Windows.Automation.TablePatternIdentifiers>|  
|<span data-ttu-id="e8883-136">Stan kontrolki przełączania</span><span class="sxs-lookup"><span data-stu-id="e8883-136">State of a toggle control</span></span>|<xref:System.Windows.Automation.TogglePattern>|<xref:System.Windows.Automation.TogglePatternIdentifiers>|  
|<span data-ttu-id="e8883-137">Możliwości elementu, który można przenieść, obrócić lub zmienić jego rozmiar</span><span class="sxs-lookup"><span data-stu-id="e8883-137">Capabilities of an element that can be moved, rotated, or resized</span></span>|<xref:System.Windows.Automation.TransformPattern>|<xref:System.Windows.Automation.TransformPatternIdentifiers>|  
|<span data-ttu-id="e8883-138">Możliwości wartości i odczytu/zapisu elementu, który ma wartość</span><span class="sxs-lookup"><span data-stu-id="e8883-138">Value and read/write capabilities of an element that has a value</span></span>|<xref:System.Windows.Automation.ValuePattern>|<xref:System.Windows.Automation.ValuePatternIdentifiers>|  
|<span data-ttu-id="e8883-139">Możliwości i stan okna</span><span class="sxs-lookup"><span data-stu-id="e8883-139">Capabilities and state of a window</span></span>|<xref:System.Windows.Automation.WindowPattern>|<xref:System.Windows.Automation.WindowPatternIdentifiers>|  
  
<a name="Properties_by_Category"></a>

## <a name="properties-by-category"></a><span data-ttu-id="e8883-140">Właściwości według kategorii</span><span class="sxs-lookup"><span data-stu-id="e8883-140">Properties by Category</span></span>  

 <span data-ttu-id="e8883-141">W poniższych tabelach wymieniono właściwości, których identyfikatory znajdują się w <xref:System.Windows.Automation.AutomationElement> i <xref:System.Windows.Automation.AutomationElementIdentifiers> .</span><span class="sxs-lookup"><span data-stu-id="e8883-141">The following tables categorize the properties whose IDs are found in <xref:System.Windows.Automation.AutomationElement> and <xref:System.Windows.Automation.AutomationElementIdentifiers>.</span></span> <span data-ttu-id="e8883-142">Te właściwości są wspólne dla wszystkich kontrolek.</span><span class="sxs-lookup"><span data-stu-id="e8883-142">These properties are common to all controls.</span></span> <span data-ttu-id="e8883-143">Wszystkie oprócz kilku z nich mogą być statyczne w okresie istnienia aplikacji dostawcy. Większość właściwości dynamicznych jest skojarzonych ze wzorcami kontrolek.</span><span class="sxs-lookup"><span data-stu-id="e8883-143">All but a few of them are likely to be static over the lifetime of the provider application; most dynamic properties are associated with control patterns.</span></span>  
  
 <span data-ttu-id="e8883-144">W kolumnie **dostęp do właściwości** są wyświetlane wszystkie inne metody dostępu dla każdej właściwości, a także do <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> i <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> .</span><span class="sxs-lookup"><span data-stu-id="e8883-144">The **Property Access** column lists any other accessors for each property, in addition to <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> and <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>.</span></span> <span data-ttu-id="e8883-145">Aby uzyskać więcej informacji na temat pobierania właściwości w aplikacji klienckiej, zobacz [właściwości automatyzacji interfejsu użytkownika dla klientów](ui-automation-properties-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="e8883-145">For more information on getting properties in a client application, see [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8883-146">Aby uzyskać szczegółowe informacje na temat każdej właściwości, Użyj linku w kolumnie **dostęp do właściwości** .</span><span class="sxs-lookup"><span data-stu-id="e8883-146">For specific information about each property, follow the link in the **Property Access** column.</span></span>  
  
### <a name="display-characteristics"></a><span data-ttu-id="e8883-147">Właściwości wyświetlania</span><span class="sxs-lookup"><span data-stu-id="e8883-147">Display Characteristics</span></span>  
  
|<span data-ttu-id="e8883-148">Identyfikator właściwości</span><span class="sxs-lookup"><span data-stu-id="e8883-148">Property identifier</span></span>|<span data-ttu-id="e8883-149">Dostęp do właściwości</span><span class="sxs-lookup"><span data-stu-id="e8883-149">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>|  
|<xref:System.Windows.Automation.AutomationElement.CultureProperty>|<span data-ttu-id="e8883-150">n/d</span><span class="sxs-lookup"><span data-stu-id="e8883-150">n/a</span></span>|  
|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsOffscreen%2A>|  
|<xref:System.Windows.Automation.AutomationElement.OrientationProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Orientation%2A>|  
  
### <a name="element-type"></a><span data-ttu-id="e8883-151">Typ elementu</span><span class="sxs-lookup"><span data-stu-id="e8883-151">Element Type</span></span>  
  
|<span data-ttu-id="e8883-152">Identyfikator właściwości</span><span class="sxs-lookup"><span data-stu-id="e8883-152">Property identifier</span></span>|<span data-ttu-id="e8883-153">Dostęp do właściwości</span><span class="sxs-lookup"><span data-stu-id="e8883-153">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsContentElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsControlElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LocalizedControlType%2A>|  
  
### <a name="identification"></a><span data-ttu-id="e8883-154">Identyfikacja</span><span class="sxs-lookup"><span data-stu-id="e8883-154">Identification</span></span>  
  
|<span data-ttu-id="e8883-155">Identyfikator właściwości</span><span class="sxs-lookup"><span data-stu-id="e8883-155">Property identifier</span></span>|<span data-ttu-id="e8883-156">Dostęp do właściwości</span><span class="sxs-lookup"><span data-stu-id="e8883-156">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AutomationId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClassNameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ClassName%2A>|  
|<xref:System.Windows.Automation.AutomationElement.FrameworkIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.FrameworkId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LabeledByProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LabeledBy%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ProcessIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ProcessId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.RuntimeIdProperty>|<xref:System.Windows.Automation.AutomationElement.GetRuntimeId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NativeWindowHandleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.NativeWindowHandle%2A>|  
  
### <a name="interaction"></a><span data-ttu-id="e8883-157">Interakcja</span><span class="sxs-lookup"><span data-stu-id="e8883-157">Interaction</span></span>  
  
|<span data-ttu-id="e8883-158">Identyfikator właściwości</span><span class="sxs-lookup"><span data-stu-id="e8883-158">Property identifier</span></span>|<span data-ttu-id="e8883-159">Dostęp do właściwości</span><span class="sxs-lookup"><span data-stu-id="e8883-159">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AcceleratorKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AccessKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>|<xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>|  
|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HasKeyboardFocus%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsEnabled%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsKeyboardFocusable%2A>|  
  
### <a name="support-for-patterns"></a><span data-ttu-id="e8883-160">Obsługa wzorców</span><span class="sxs-lookup"><span data-stu-id="e8883-160">Support for Patterns</span></span>  
  
|<span data-ttu-id="e8883-161">Identyfikator właściwości</span><span class="sxs-lookup"><span data-stu-id="e8883-161">Property identifier</span></span>|<span data-ttu-id="e8883-162">Dostęp do właściwości</span><span class="sxs-lookup"><span data-stu-id="e8883-162">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsDockPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsExpandCollapsePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsInvokePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsMultipleViewPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsRangeValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTableItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTablePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTogglePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTransformPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsWindowPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
  
### <a name="miscellaneous"></a><span data-ttu-id="e8883-163">Różne</span><span class="sxs-lookup"><span data-stu-id="e8883-163">Miscellaneous</span></span>  
  
|<span data-ttu-id="e8883-164">Identyfikator właściwości</span><span class="sxs-lookup"><span data-stu-id="e8883-164">Property identifier</span></span>|<span data-ttu-id="e8883-165">Dostęp do właściwości</span><span class="sxs-lookup"><span data-stu-id="e8883-165">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsRequiredForFormProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsRequiredForForm%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsPassword%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemStatusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemStatus%2A>|  
  
<a name="Localization"></a>

## <a name="localization"></a><span data-ttu-id="e8883-166">Localization</span><span class="sxs-lookup"><span data-stu-id="e8883-166">Localization</span></span>  

 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="e8883-167">dostawcy powinni przedstawić następujące właściwości w języku systemu operacyjnego:</span><span class="sxs-lookup"><span data-stu-id="e8883-167">providers should present the following properties in the language of the operating system:</span></span>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>  
  
<a name="Properties_and_Events"></a>

## <a name="properties-and-events"></a><span data-ttu-id="e8883-168">Właściwości i zdarzenia</span><span class="sxs-lookup"><span data-stu-id="e8883-168">Properties and Events</span></span>  

 <span data-ttu-id="e8883-169">Ściśle powiązane z właściwościami w [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] to koncepcja zdarzeń zmieniających właściwości.</span><span class="sxs-lookup"><span data-stu-id="e8883-169">Closely tied in with the properties in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is the concept of property-changed events.</span></span> <span data-ttu-id="e8883-170">W przypadku właściwości dynamicznych aplikacja kliencka musi wiedzieć, że wartość właściwości została zmieniona, dzięki czemu może ona aktualizować pamięć podręczną informacji lub reagować na nowe informacje w inny sposób.</span><span class="sxs-lookup"><span data-stu-id="e8883-170">For dynamic properties, the client application needs a way to know that a property value has changed, so that it can update its cache of information or react to the new information in some other way.</span></span>  
  
 <span data-ttu-id="e8883-171">Dostawcy zgłaszają zdarzenia, gdy coś w [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] zmianach.</span><span class="sxs-lookup"><span data-stu-id="e8883-171">Providers raise events when something in the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] changes.</span></span> <span data-ttu-id="e8883-172">Na przykład jeśli pole wyboru jest zaznaczone lub wyczyszczone, zdarzenie zmiany właściwości jest zgłaszane przez implementację wzorca przełączania przez dostawcę.</span><span class="sxs-lookup"><span data-stu-id="e8883-172">For example, if a check box is selected or cleared, a property-changed event is raised by the provider's implementation of the Toggle pattern.</span></span> <span data-ttu-id="e8883-173">Dostawcy mogą wybiórczo zgłaszać zdarzenia w zależności od tego, czy klienci oczekują na zdarzenia, czy nasłuchują określonych zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="e8883-173">Providers can raise events selectively, depending on whether any clients are listening for events, or listening for specific events.</span></span>  
  
 <span data-ttu-id="e8883-174">Nie wszystkie zmiany właściwości powodują wystąpienie zdarzeń; jest to całkowicie do implementacji dostawcy automatyzacji interfejsu użytkownika dla elementu.</span><span class="sxs-lookup"><span data-stu-id="e8883-174">Not all property changes raise events; that is entirely up to the implementation of the UI Automation provider for the element.</span></span> <span data-ttu-id="e8883-175">Na przykład standardowy dostawca proxy dla pól listy nie zgłasza zdarzenia po <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> wprowadzeniu zmian.</span><span class="sxs-lookup"><span data-stu-id="e8883-175">For example, the standard proxy providers for list boxes do not raise an event when the <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> changes.</span></span> <span data-ttu-id="e8883-176">W takim przypadku aplikacja musi nasłuchiwać przez <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent> .</span><span class="sxs-lookup"><span data-stu-id="e8883-176">In this case, the application instead must listen for an <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>.</span></span>  
  
 <span data-ttu-id="e8883-177">Klienci nasłuchują zdarzeń, subskrybując je.</span><span class="sxs-lookup"><span data-stu-id="e8883-177">Clients listen for events by subscribing to them.</span></span> <span data-ttu-id="e8883-178">Subskrybowanie zdarzeń oznacza utworzenie metod delegatów, które mogą obsłużyć zdarzenia, a następnie przekazanie metod do [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] określonych zdarzeń, które będą rozpatrywane w tych metodach.</span><span class="sxs-lookup"><span data-stu-id="e8883-178">Subscribing to events means creating delegate methods that can handle the events, and then passing the methods to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] along with the specific events that will be dealt with in those methods.</span></span> <span data-ttu-id="e8883-179">W szczególności dla zdarzeń ze zmienionymi właściwościami klienci muszą zaimplementować <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="e8883-179">For property-changed events in particular, clients must implement <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8883-180">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e8883-180">See also</span></span>

- [<span data-ttu-id="e8883-181">Buforowanie w klientach automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="e8883-181">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
- [<span data-ttu-id="e8883-182">Właściwości automatyzacji interfejsu użytkownika dla klientów</span><span class="sxs-lookup"><span data-stu-id="e8883-182">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)
- [<span data-ttu-id="e8883-183">Implementacja dostawcy automatyzacji interfejsu użytkownika po stronie serwera</span><span class="sxs-lookup"><span data-stu-id="e8883-183">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)
- [<span data-ttu-id="e8883-184">Znajdź element automatyzacji interfejsu użytkownika na podstawie warunku właściwości</span><span class="sxs-lookup"><span data-stu-id="e8883-184">Find a UI Automation Element Based on a Property Condition</span></span>](find-a-ui-automation-element-based-on-a-property-condition.md)
- [<span data-ttu-id="e8883-185">Zwracanie właściwości od dostawcy automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="e8883-185">Return Properties from a UI Automation Provider</span></span>](return-properties-from-a-ui-automation-provider.md)
- [<span data-ttu-id="e8883-186">Wywoływanie zdarzeń od dostawcy automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="e8883-186">Raise Events from a UI Automation Provider</span></span>](raise-events-from-a-ui-automation-provider.md)
