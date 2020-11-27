---
title: Implementacja wzorca formantu przekształcania automatyzacji interfejsu użytkownika
description: Przejrzyj wskazówki i konwencje w celu zaimplementowania wzorca kontroli transformacji w automatyzacji interfejsu użytkownika. Znajomość wymaganych członków interfejsu ITransformProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Transform
- Transform control pattern
- UI Automation, Transform control pattern
ms.assetid: 5f49d843-5845-4800-9d9c-56ce0d146844
ms.openlocfilehash: fc47170a08ff08f6cd8f67996ef8fbf19c40f819
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265651"
---
# <a name="implementing-the-ui-automation-transform-control-pattern"></a><span data-ttu-id="d1ff6-104">Implementacja wzorca formantu przekształcania automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="d1ff6-104">Implementing the UI Automation Transform Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="d1ff6-105">Ta dokumentacja jest przeznaczona dla .NET Framework deweloperów, którzy chcą korzystać z zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="d1ff6-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d1ff6-106">Aby uzyskać najnowsze informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , zobacz [interfejs API usługi Windows Automation: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="d1ff6-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="d1ff6-107">W tym temacie przedstawiono wskazówki i konwencje dotyczące wdrażania <xref:System.Windows.Automation.Provider.ITransformProvider> , w tym informacje o właściwościach, metodach i zdarzeniach.</span><span class="sxs-lookup"><span data-stu-id="d1ff6-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="d1ff6-108">Linki do dodatkowych odwołań znajdują się na końcu tematu.</span><span class="sxs-lookup"><span data-stu-id="d1ff6-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="d1ff6-109"><xref:System.Windows.Automation.TransformPattern>Wzorzec kontrolki służy do obsługi kontrolek, które można przenosić, zmieniać rozmiar lub obracać w przestrzeni dwuwymiarowej.</span><span class="sxs-lookup"><span data-stu-id="d1ff6-109">The <xref:System.Windows.Automation.TransformPattern> control pattern is used to support controls that can be moved, resized, or rotated within a two-dimensional space.</span></span> <span data-ttu-id="d1ff6-110">Aby zapoznać się z przykładami formantów implementujących ten wzorzec kontrolek, zobacz [Mapowanie wzorców formantów dla klientów automatyzacji interfejsu użytkownika](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="d1ff6-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="d1ff6-111">Wytyczne i konwencje dotyczące implementacji</span><span class="sxs-lookup"><span data-stu-id="d1ff6-111">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="d1ff6-112">Podczas implementowania wzorca kontroli transformacji należy zwrócić uwagę na następujące wytyczne i konwencje:</span><span class="sxs-lookup"><span data-stu-id="d1ff6-112">When implementing the Transform control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="d1ff6-113">Obsługa tego wzorca kontroli nie jest ograniczona do obiektów na pulpicie.</span><span class="sxs-lookup"><span data-stu-id="d1ff6-113">Support for this control pattern is not limited to objects on the desktop.</span></span> <span data-ttu-id="d1ff6-114">Ten wzorzec kontrolki musi być również obsługiwany przez elementy podrzędne obiektu kontenera, jeśli elementy podrzędne można przenosić, zmieniać rozmiar lub swobodnie obracać w granicach kontenera.</span><span class="sxs-lookup"><span data-stu-id="d1ff6-114">This control pattern must also be supported by the children of a container object if the children can be moved, resized, or rotated freely within the boundaries of the container.</span></span>  
  
- <span data-ttu-id="d1ff6-115">Nie można przenieść, zmienić rozmiaru ani obrócić obiektu, tak aby jego lokalizacja ekranu była całkowicie poza granicami jego kontenera i w związku z tym był niedostępny dla klawiatury lub myszy (na przykład po przesunięciu okna najwyższego poziomu do trybu offline lub przeniesieniu obiektu podrzędnego poza granice okienka ekranu kontenera).</span><span class="sxs-lookup"><span data-stu-id="d1ff6-115">An object cannot be moved, resized, or rotated such that its resulting screen location would be completely outside the coordinates of its container and therefore inaccessible to the keyboard or mouse (for example, when a top-level window is moved off-screen or a child object is moved outside the boundaries of the container's viewport).</span></span> <span data-ttu-id="d1ff6-116">W takich przypadkach obiekt jest umieszczany w pobliżu żądanych współrzędnych ekranu, a współrzędne górne lub lewe są zastępowane w granicach kontenera.</span><span class="sxs-lookup"><span data-stu-id="d1ff6-116">In these cases, the object is placed as close to the requested screen coordinates as possible with the top or left coordinates overridden to be within the container boundaries.</span></span>  
  
- <span data-ttu-id="d1ff6-117">W przypadku systemów z obsługą kilku monitorów, jeśli obiekt jest przenoszony, zmieniany jest rozmiar lub obracany całkowicie poza połączone Współrzędne ekranu pulpitu, obiekt zostanie umieszczony na monitorze podstawowym jako blisko żądanych współrzędnych.</span><span class="sxs-lookup"><span data-stu-id="d1ff6-117">For multi-monitor systems, if an object is moved, resized, or rotated completely outside the combined desktop screen coordinates, the object is placed on the primary monitor as close to the requested coordinates as possible.</span></span>  
  
- <span data-ttu-id="d1ff6-118">Wszystkie parametry i wartości właściwości są bezwzględne i niezależne od ustawień regionalnych.</span><span class="sxs-lookup"><span data-stu-id="d1ff6-118">All parameters and property values are absolute and independent of locale.</span></span>  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>

## <a name="required-members-for-itransformprovider"></a><span data-ttu-id="d1ff6-119">Wymagane elementy członkowskie dla ITransformProvider</span><span class="sxs-lookup"><span data-stu-id="d1ff6-119">Required Members for ITransformProvider</span></span>  

 <span data-ttu-id="d1ff6-120">Następujące właściwości i metody są wymagane do zaimplementowania <xref:System.Windows.Automation.Provider.ITransformProvider> .</span><span class="sxs-lookup"><span data-stu-id="d1ff6-120">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>.</span></span>  
  
|<span data-ttu-id="d1ff6-121">Wymagane elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="d1ff6-121">Required members</span></span>|<span data-ttu-id="d1ff6-122">Typ elementu członkowskiego</span><span class="sxs-lookup"><span data-stu-id="d1ff6-122">Member type</span></span>|<span data-ttu-id="d1ff6-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d1ff6-123">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanMove%2A>|<span data-ttu-id="d1ff6-124">Właściwość</span><span class="sxs-lookup"><span data-stu-id="d1ff6-124">Property</span></span>|<span data-ttu-id="d1ff6-125">Brak</span><span class="sxs-lookup"><span data-stu-id="d1ff6-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanResize%2A>|<span data-ttu-id="d1ff6-126">Właściwość</span><span class="sxs-lookup"><span data-stu-id="d1ff6-126">Property</span></span>|<span data-ttu-id="d1ff6-127">Brak</span><span class="sxs-lookup"><span data-stu-id="d1ff6-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanRotate%2A>|<span data-ttu-id="d1ff6-128">Właściwość</span><span class="sxs-lookup"><span data-stu-id="d1ff6-128">Property</span></span>|<span data-ttu-id="d1ff6-129">Brak</span><span class="sxs-lookup"><span data-stu-id="d1ff6-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A>|<span data-ttu-id="d1ff6-130">Metoda</span><span class="sxs-lookup"><span data-stu-id="d1ff6-130">Method</span></span>|<span data-ttu-id="d1ff6-131">Brak</span><span class="sxs-lookup"><span data-stu-id="d1ff6-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A>|<span data-ttu-id="d1ff6-132">Metoda</span><span class="sxs-lookup"><span data-stu-id="d1ff6-132">Method</span></span>|<span data-ttu-id="d1ff6-133">Brak</span><span class="sxs-lookup"><span data-stu-id="d1ff6-133">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A>|<span data-ttu-id="d1ff6-134">Metoda</span><span class="sxs-lookup"><span data-stu-id="d1ff6-134">Method</span></span>|<span data-ttu-id="d1ff6-135">Brak</span><span class="sxs-lookup"><span data-stu-id="d1ff6-135">None</span></span>|  
  
 <span data-ttu-id="d1ff6-136">Ten wzorzec kontrolki nie ma skojarzonych zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="d1ff6-136">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="d1ff6-137">Wyjątki</span><span class="sxs-lookup"><span data-stu-id="d1ff6-137">Exceptions</span></span>  

 <span data-ttu-id="d1ff6-138">Dostawcy muszą zgłosić następujące wyjątki.</span><span class="sxs-lookup"><span data-stu-id="d1ff6-138">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="d1ff6-139">Typ wyjątku</span><span class="sxs-lookup"><span data-stu-id="d1ff6-139">Exception Type</span></span>|<span data-ttu-id="d1ff6-140">Warunek</span><span class="sxs-lookup"><span data-stu-id="d1ff6-140">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A><br /><br /> <span data-ttu-id="d1ff6-141">-Jeśli <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> ma wartość false.</span><span class="sxs-lookup"><span data-stu-id="d1ff6-141">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A><br /><br /> <span data-ttu-id="d1ff6-142">-Jeśli <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> ma wartość false.</span><span class="sxs-lookup"><span data-stu-id="d1ff6-142">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A><br /><br /> <span data-ttu-id="d1ff6-143">-Jeśli <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> ma wartość false.</span><span class="sxs-lookup"><span data-stu-id="d1ff6-143">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> is false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1ff6-144">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d1ff6-144">See also</span></span>

- [<span data-ttu-id="d1ff6-145">Wzorce formantów automatyzacji interfejsu użytkownika — omówienie</span><span class="sxs-lookup"><span data-stu-id="d1ff6-145">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="d1ff6-146">Obsługa wzorców formantów dostawcy automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="d1ff6-146">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="d1ff6-147">Wzorce kontrolek automatyzacji interfejsu użytkownika dla klientów</span><span class="sxs-lookup"><span data-stu-id="d1ff6-147">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="d1ff6-148">Przegląd drzewa automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="d1ff6-148">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="d1ff6-149">Używanie buforowania w automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="d1ff6-149">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
