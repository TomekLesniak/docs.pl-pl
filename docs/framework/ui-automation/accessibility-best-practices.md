---
title: Najlepsze praktyki dotyczące ułatwień dostępu
description: Poznaj najlepsze rozwiązania dotyczące ułatwień dostępu w programie .NET. Eksploruj dostęp programistyczny, ustawienia użytkownika, Visual graficzny projekt interfejsu użytkownika, nawigację i interfejsy Multimodal.
ms.date: 03/30/2017
helpviewer_keywords:
- best practices for accessibility
- accessibility, best practices for
ms.assetid: e6d5cd98-21a3-4b01-999c-fb953556d0e6
ms.openlocfilehash: 30961c83bdacf816856205322ac2b627d0f2594c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235691"
---
# <a name="accessibility-best-practices"></a><span data-ttu-id="7d551-104">Najlepsze rozwiązania dotyczące ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="7d551-104">Accessibility best practices</span></span>

> [!NOTE]
> <span data-ttu-id="7d551-105">Ten artykuł jest przeznaczony .NET Framework dla deweloperów, którzy chcą korzystać z klas automatyzacji zarządzanego interfejsu użytkownika zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="7d551-105">This article is intended for .NET Framework developers who want to use the managed UI Automation classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="7d551-106">Najnowsze informacje o automatyzacji interfejsu użytkownika znajdują się w temacie [Windows Automation API: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="7d551-106">For the latest information about UI Automation, see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="7d551-107">Wdrożenie następujących najlepszych rozwiązań w zakresie kontroli lub aplikacji poprawi ich dostępność dla osób korzystających z urządzeń z technologią pomocniczą.</span><span class="sxs-lookup"><span data-stu-id="7d551-107">Implementing the following best practices in controls or applications will improve their accessibility for people who use assistive technology devices.</span></span> <span data-ttu-id="7d551-108">Wiele z tych najlepszych rozwiązań koncentruje się na dobrym projekcie interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7d551-108">Many of these best practices focus on good user interface (UI) design.</span></span> <span data-ttu-id="7d551-109">Każde najlepsze rozwiązanie obejmuje informacje o implementacji dla formantów i aplikacji Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="7d551-109">Each best practice includes implementation information for Windows Presentation Foundation (WPF) controls or applications.</span></span> <span data-ttu-id="7d551-110">W wielu przypadkach pracy, która spełnia te najlepsze rozwiązania, jest już zawarty w kontrolkach WPF.</span><span class="sxs-lookup"><span data-stu-id="7d551-110">In many cases, the work to meet these best practices is already included in WPF controls.</span></span>  
  
<a name="Programmatic_Access"></a>

## <a name="programmatic-access"></a><span data-ttu-id="7d551-111">Dostęp programowy</span><span class="sxs-lookup"><span data-stu-id="7d551-111">Programmatic Access</span></span>  

 <span data-ttu-id="7d551-112">Dostęp programistyczny polega na zapewnieniu, że wszystkie elementy interfejsu użytkownika są oznaczone etykietami, wartości właściwości są ujawniane i wywoływane są odpowiednie zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="7d551-112">Programmatic access involves ensuring that all UI elements are labeled, property values are exposed, and appropriate events are raised.</span></span> <span data-ttu-id="7d551-113">W przypadku standardowych formantów WPF większość tej pracy jest już wykonywana przez program <xref:System.Windows.Automation.Peers.AutomationPeer> .</span><span class="sxs-lookup"><span data-stu-id="7d551-113">For standard WPF controls, most of this work is already done through <xref:System.Windows.Automation.Peers.AutomationPeer>.</span></span> <span data-ttu-id="7d551-114">Niestandardowe kontrolki wymagają dodatkowej pracy, aby zapewnić, że dostęp programistyczny jest prawidłowo zaimplementowany.</span><span class="sxs-lookup"><span data-stu-id="7d551-114">Custom controls require additional work to ensure that programmatic access is correctly implemented.</span></span>  
  
<a name="Enable_Programmatic_Access_to_all_UI_Elements_and_Text"></a>

### <a name="enable-programmatic-access-to-all-ui-elements-and-text"></a><span data-ttu-id="7d551-115">Włącz dostęp programistyczny do wszystkich elementów interfejsu użytkownika i tekstu</span><span class="sxs-lookup"><span data-stu-id="7d551-115">Enable Programmatic Access to all UI Elements and Text</span></span>  

 <span data-ttu-id="7d551-116">Elementy interfejsu użytkownika powinny włączać dostęp programistyczny.</span><span class="sxs-lookup"><span data-stu-id="7d551-116">User interface (UI) elements should enable programmatic access.</span></span> <span data-ttu-id="7d551-117">Jeśli interfejs użytkownika jest standardową kontrolką WPF, obsługa dostępu programowego jest zawarta w kontrolce.</span><span class="sxs-lookup"><span data-stu-id="7d551-117">If the UI is a standard WPF control, support for programmatic access is included in the control.</span></span> <span data-ttu-id="7d551-118">Jeśli formant jest formantem niestandardowym — formantem, który został poddany do podklasy ze wspólnej kontrolki lub kontrolki, która została poddana kontroli, należy sprawdzić <xref:System.Windows.Automation.Peers.AutomationPeer> implementację obszarów, które mogą wymagać modyfikacji.</span><span class="sxs-lookup"><span data-stu-id="7d551-118">If the control is a custom control – a control that has been subclassed from a common control or a control that has been subclassed from Control – then you must check the <xref:System.Windows.Automation.Peers.AutomationPeer> implementation for areas that may need modification.</span></span>  
  
 <span data-ttu-id="7d551-119">Zgodnie z tym najlepszym rozwiązaniem dostawcy technologii pomocniczej mogą identyfikować elementy interfejsu użytkownika produktu i manipulować nimi.</span><span class="sxs-lookup"><span data-stu-id="7d551-119">Following this best practice allows assistive technology vendors to identify and manipulate elements of your product's UI.</span></span>  
  
<a name="Place_Names__Titles_and_Descriptions_on_UI_Objects_"></a>

### <a name="place-names-titles-and-descriptions-on-ui-objects-frames-and-pages"></a><span data-ttu-id="7d551-120">Umieszczaj nazwy, tytuły i opisy dotyczące obiektów, ramek i stron interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="7d551-120">Place Names, Titles, and Descriptions on UI Objects, Frames, and Pages</span></span>  

 <span data-ttu-id="7d551-121">Technologie pomocnicze, zwłaszcza czytniki ekranu, wykorzystują tytuł, aby zrozumieć lokalizację ramki, obiektu lub strony w schemacie nawigacji.</span><span class="sxs-lookup"><span data-stu-id="7d551-121">Assistive technologies, especially screen readers, use the title to understand the location of the frame, object, or page in the navigation scheme.</span></span> <span data-ttu-id="7d551-122">W związku z tym tytuł musi być opisowy.</span><span class="sxs-lookup"><span data-stu-id="7d551-122">Therefore, the title must be descriptive.</span></span> <span data-ttu-id="7d551-123">Na przykład tytuł strony sieci Web "Strona sieci Web firmy Microsoft" jest bezużyteczny, jeśli użytkownik przejdzie głęboko do określonego obszaru.</span><span class="sxs-lookup"><span data-stu-id="7d551-123">For example, a Web page title of "Microsoft Web Page" is useless if the user has navigated deeply into some particular area.</span></span> <span data-ttu-id="7d551-124">Opisowy tytuł ma krytyczne znaczenie dla użytkowników niewidomych i niezależnych od czytników zawartości ekranu.</span><span class="sxs-lookup"><span data-stu-id="7d551-124">A descriptive title is critical for users who are blind and depend on screen readers.</span></span> <span data-ttu-id="7d551-125">Podobnie w przypadku formantów WPF <xref:System.Windows.Automation.AutomationProperties.NameProperty> i <xref:System.Windows.Automation.AutomationProperties.HelpTextProperty> są ważne w przypadku urządzeń z technologią pomocniczą.</span><span class="sxs-lookup"><span data-stu-id="7d551-125">Similarly, for WPF controls, <xref:System.Windows.Automation.AutomationProperties.NameProperty> and <xref:System.Windows.Automation.AutomationProperties.HelpTextProperty> are important for assistive technology devices.</span></span>  
  
 <span data-ttu-id="7d551-126">Korzystając z tej najlepszej wskazówki, można używać technologii pomocniczych do identyfikowania i manipulowania interfejsem użytkownika w przykładowych formantach i aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="7d551-126">Following this best practice allows assistive technologies to identify and manipulate UI in sample controls and applications.</span></span>  
  
<a name="Ensure_Programmatic_Events_are_Triggered_by_all_UI"></a>

### <a name="ensure-programmatic-events-are-triggered-by-all-ui-activities"></a><span data-ttu-id="7d551-127">Upewnij się, że zdarzenia programistyczne są wyzwalane przez wszystkie działania interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="7d551-127">Ensure Programmatic Events Are Triggered by All UI Activities</span></span>  

 <span data-ttu-id="7d551-128">Zgodnie z tym najlepszym rozwiązaniem, technologie wspomagające umożliwiają nasłuchiwanie zmian w interfejsie użytkownika i powiadamianie użytkownika o tych zmianach.</span><span class="sxs-lookup"><span data-stu-id="7d551-128">Following this best practice allows assistive technologies to listen for changes in the UI and notify the user about these changes.</span></span>  
  
<a name="User_Settings"></a>

## <a name="user-settings"></a><span data-ttu-id="7d551-129">Ustawienia użytkownika</span><span class="sxs-lookup"><span data-stu-id="7d551-129">User Settings</span></span>  

 <span data-ttu-id="7d551-130">Najlepszym rozwiązaniem w tej sekcji jest zagwarantowanie, że formanty lub aplikacje nie zastępują ustawień użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7d551-130">The best practice in this section ensures that controls or applications do not override user settings.</span></span>  
  
<a name="Respect_all_System_Wide_Settings_and_do_not_Interfere"></a>

### <a name="respect-all-system-wide-settings-and-do-not-interfere-with-accessibility-functions"></a><span data-ttu-id="7d551-131">Uwzględnij wszystkie ustawienia System-Wide i nie zakłócaj działania funkcji ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="7d551-131">Respect All System-Wide Settings and Do Not Interfere with Accessibility Functions</span></span>  

 <span data-ttu-id="7d551-132">Użytkownicy mogą używać panelu sterowania do ustawiania niektórych flag dla całego systemu; inne flagi można ustawić programowo.</span><span class="sxs-lookup"><span data-stu-id="7d551-132">Users can use the Control Panel to set some system-wide flags; other flags can be set programmatically.</span></span> <span data-ttu-id="7d551-133">Tych ustawień nie należy zmieniać przez kontrolki ani aplikacje.</span><span class="sxs-lookup"><span data-stu-id="7d551-133">These settings should not be changed by controls or applications.</span></span> <span data-ttu-id="7d551-134">Ponadto aplikacje muszą obsługiwać ustawienia ułatwień dostępu dla swojego systemu operacyjnego hosta.</span><span class="sxs-lookup"><span data-stu-id="7d551-134">Also, applications must support the accessibility settings of their host operating system.</span></span>  
  
 <span data-ttu-id="7d551-135">Zgodnie z tym najlepszym rozwiązaniem użytkownicy mogą ustawiać ustawienia ułatwień dostępu i wiedzieć, że te ustawienia nie zostaną zmienione przez aplikacje.</span><span class="sxs-lookup"><span data-stu-id="7d551-135">Following this best practice allows users to set accessibility settings and know that those settings will not be changed by applications.</span></span>  
  
<a name="Visual_UI_Design"></a>

## <a name="visual-ui-design"></a><span data-ttu-id="7d551-136">Projekt wizualnego interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="7d551-136">Visual UI Design</span></span>  

 <span data-ttu-id="7d551-137">Najlepsze rozwiązania w tej sekcji zapewniają, że kontrolki lub aplikacje wykorzystują kolor i obrazy efektywnie i mogą być używane przez technologie pomocnicze.</span><span class="sxs-lookup"><span data-stu-id="7d551-137">Best Practices in this section ensure that controls or applications use color and images effectively and are able to be used by Assistive technologies.</span></span>  
  
<a name="Don_t_Hard_Code_Colors"></a>

### <a name="dont-hard-code-colors"></a><span data-ttu-id="7d551-138">Nie należy trwale kodować kolorów</span><span class="sxs-lookup"><span data-stu-id="7d551-138">Don't Hard-Code Colors</span></span>  

 <span data-ttu-id="7d551-139">Osoby, które są w kolorze niewidomym, mają słabą wizję lub używają czerni i białych ekranów, mogą nie być w stanie używać aplikacji z ustalonymi kolorami.</span><span class="sxs-lookup"><span data-stu-id="7d551-139">People who are color blind, have low vision, or are using a black and white screen might not be able to use applications with hard-coded colors.</span></span>  
  
 <span data-ttu-id="7d551-140">Zgodnie z tym najlepszym rozwiązaniem użytkownicy dostosowują kombinacje kolorów na podstawie indywidualnych potrzeb.</span><span class="sxs-lookup"><span data-stu-id="7d551-140">Following this best practice allows users to adjust color combinations based on individual needs.</span></span>  
  
<a name="Support_High_Contrast_and_all_System_Display_Attributes"></a>

### <a name="support-high-contrast-and-all-system-display-attributes"></a><span data-ttu-id="7d551-141">Obsługa duży kontrast i wszystkie atrybuty wyświetlania systemu</span><span class="sxs-lookup"><span data-stu-id="7d551-141">Support High Contrast and all System Display Attributes</span></span>  

 <span data-ttu-id="7d551-142">Aplikacje nie powinny zakłócać ani wyłączać wybranych przez użytkownika ustawień kontrastu systemu, kolorów ani opcji wyświetlania w całym systemie.</span><span class="sxs-lookup"><span data-stu-id="7d551-142">Applications should not disrupt or disable user-selected, system-wide contrast settings, color selections, or other system-wide display settings and attributes.</span></span> <span data-ttu-id="7d551-143">Ustawienia dotyczące całego systemu przyjęte przez użytkownika rozszerzają dostępność aplikacji, dlatego nie powinny być wyłączone ani nieuznawane przez aplikacje.</span><span class="sxs-lookup"><span data-stu-id="7d551-143">System-wide settings adopted by a user enhance the accessibility of applications, so they should not be disabled or disregarded by applications.</span></span> <span data-ttu-id="7d551-144">Kolor powinien być używany w odpowiedniej kombinacji pierwszego planu w tle, aby zapewnić odpowiedni kontrast.</span><span class="sxs-lookup"><span data-stu-id="7d551-144">Color should be used in their correct foreground-on-background combination to provide proper contrast.</span></span> <span data-ttu-id="7d551-145">Nie mieszaj niepowiązanych kolorów i nie odwracaj kolorów.</span><span class="sxs-lookup"><span data-stu-id="7d551-145">Don't mix unrelated colors, and don't reverse colors.</span></span>  
  
 <span data-ttu-id="7d551-146">Wielu użytkowników wymaga określonych kombinacji o wysokim kontraście, takich jak biały tekst na czarnym tle.</span><span class="sxs-lookup"><span data-stu-id="7d551-146">Many users require specific high-contrast combinations, such as white text on a black background.</span></span> <span data-ttu-id="7d551-147">Rysowanie odpisano, jako czarny tekst na białym tle powoduje, że tło spada na pierwszy plan i może utrudnić odczyt dla niektórych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="7d551-147">Drawing these reversed, as black text on a white background causes the background to bleed over the foreground and can make reading difficult for some users.</span></span>  
  
<a name="Ensure_all_UI_Correctly_Scales_by_any_DPI_Setting"></a>

### <a name="ensure-all-ui-correctly-scales-by-any-dpi-setting"></a><span data-ttu-id="7d551-148">Upewnij się, że wszystkie elementy interfejsu użytkownika są prawidłowo skalowane według dowolnego ustawienia DPI</span><span class="sxs-lookup"><span data-stu-id="7d551-148">Ensure All UI Correctly Scales by Any DPI Setting</span></span>  

 <span data-ttu-id="7d551-149">Upewnij się, że wszystkie elementy interfejsu użytkownika mogą być prawidłowo skalowane przy użyciu dowolnego ustawienia DPI.</span><span class="sxs-lookup"><span data-stu-id="7d551-149">Ensure that all UI can correctly scale by any dots per inch (dpi) setting.</span></span> <span data-ttu-id="7d551-150">Upewnij się również, że elementy interfejsu użytkownika mieszczą się na ekranie 1024 x 768 z 120 kropkami na cal (dpi).</span><span class="sxs-lookup"><span data-stu-id="7d551-150">Also, ensure that UI elements fit in a screen of 1024 x 768 with 120 dots per inch (dpi).</span></span>  
  
<a name="Navigation"></a>

## <a name="navigation"></a><span data-ttu-id="7d551-151">Nawigacja</span><span class="sxs-lookup"><span data-stu-id="7d551-151">Navigation</span></span>  

 <span data-ttu-id="7d551-152">Najlepsze rozwiązania w tej sekcji zapewniają, że nawigacja została zastosowana w przypadku formantów i aplikacji.</span><span class="sxs-lookup"><span data-stu-id="7d551-152">Best Practices in this section ensure that navigation has been addressed for controls and applications.</span></span>  
  
<a name="Provide_Keyboard_Interface_for_all_UI_Elements"></a>

### <a name="provide-keyboard-interface-for-all-ui-elements"></a><span data-ttu-id="7d551-153">Zapewnianie interfejsu klawiatury dla wszystkich elementów interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="7d551-153">Provide Keyboard Interface for All UI Elements</span></span>  

 <span data-ttu-id="7d551-154">Tabulatory, szczególnie w przypadku starannego planowania, umożliwiają użytkownikom innym sposobem nawigowania po interfejsie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7d551-154">Tab stops, especially when carefully planned, give users another way to navigate the UI.</span></span>  
  
 <span data-ttu-id="7d551-155">Aplikacje powinny udostępniać następujące interfejsy klawiatury:</span><span class="sxs-lookup"><span data-stu-id="7d551-155">Applications should provide the following keyboard interfaces:</span></span>  
  
- <span data-ttu-id="7d551-156">tabulatory dla wszystkich kontrolek, z którymi użytkownik może korzystać, takich jak przyciski, linki lub pola listy</span><span class="sxs-lookup"><span data-stu-id="7d551-156">tab stops for all controls that the user can interact with, such as buttons, links, or list boxes</span></span>  
  
- <span data-ttu-id="7d551-157">kolejność tabulacji logicznej</span><span class="sxs-lookup"><span data-stu-id="7d551-157">logical tab order</span></span>  
  
<a name="Show_the_Keyboard_Focus"></a>

### <a name="show-the-keyboard-focus"></a><span data-ttu-id="7d551-158">Pokaż fokus klawiatury</span><span class="sxs-lookup"><span data-stu-id="7d551-158">Show the Keyboard Focus</span></span>  

 <span data-ttu-id="7d551-159">Użytkownicy muszą wiedzieć, który obiekt ma fokus klawiatury, aby można było przewidzieć efekt ich naciśnięć klawiszy.</span><span class="sxs-lookup"><span data-stu-id="7d551-159">Users need to know which object has the keyboard focus so that they can anticipate the effect of their keystrokes.</span></span> <span data-ttu-id="7d551-160">Aby wyróżnić fokus klawiatury, Użyj kolorów, czcionek lub grafiki, takich jak prostokąty lub powiększenia.</span><span class="sxs-lookup"><span data-stu-id="7d551-160">To highlight the keyboard focus, use colors, fonts, or graphics such as rectangles or magnification.</span></span> <span data-ttu-id="7d551-161">Aby audibly wyróżnić fokus klawiatury, Zmień głośność, gęstość lub jakość tonalną.</span><span class="sxs-lookup"><span data-stu-id="7d551-161">To audibly highlight the keyboard focus, change the volume, pitch, or tonal quality.</span></span>  
  
 <span data-ttu-id="7d551-162">Aby uniknąć pomyłek, aplikacje powinny ukrywać wszystkie wskaźniki fokusu wizualnego i przyciemniać zaznaczenia, które znajdują się w nieaktywnym systemie Windows (lub okienka).</span><span class="sxs-lookup"><span data-stu-id="7d551-162">To avoid confusion, applications should hide all visual focus indicators and dim selections that are located in inactive windows (or panes).</span></span>  
  
 <span data-ttu-id="7d551-163">Aplikacje powinny wykonać następujące czynności z fokusem klawiatury:</span><span class="sxs-lookup"><span data-stu-id="7d551-163">Applications should do the following with keyboard focus:</span></span>  
  
- <span data-ttu-id="7d551-164">jeden element powinien zawsze mieć fokus klawiatury</span><span class="sxs-lookup"><span data-stu-id="7d551-164">one item should always have keyboard focus</span></span>  
  
- <span data-ttu-id="7d551-165">fokus klawiatury powinien być widoczny i oczywisty</span><span class="sxs-lookup"><span data-stu-id="7d551-165">keyboard focus should be visible and obvious</span></span>  
  
- <span data-ttu-id="7d551-166">Wybory i/lub elementy skoncentrowane powinny być wyróżnione wizualnie</span><span class="sxs-lookup"><span data-stu-id="7d551-166">selections and/or focused items should be visually highlighted</span></span>  
  
<a name="Support_Navigation_Standards_and_Powerful_Navigation"></a>

### <a name="support-navigation-standards-and-powerful-navigation-schemes"></a><span data-ttu-id="7d551-167">Obsługuj standardy nawigacji i zaawansowane schematy nawigacji</span><span class="sxs-lookup"><span data-stu-id="7d551-167">Support Navigation Standards and Powerful Navigation Schemes</span></span>  

 <span data-ttu-id="7d551-168">Różne aspekty nawigacji klawiaturowej zapewniają różne sposoby nawigowania po interfejsie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7d551-168">Different aspects of keyboard navigation provide different ways for users to navigate the UI.</span></span>  
  
 <span data-ttu-id="7d551-169">Aplikacje powinny udostępniać następujące interfejsy klawiatury:</span><span class="sxs-lookup"><span data-stu-id="7d551-169">Applications should provide the following keyboard interfaces:</span></span>  
  
- <span data-ttu-id="7d551-170">klawisze skrótów i podkreślone klawisze dostępu dla wszystkich poleceń, menu i kontrolek</span><span class="sxs-lookup"><span data-stu-id="7d551-170">shortcut keys and underlined access keys for all commands, menus, and controls</span></span>  
  
- <span data-ttu-id="7d551-171">skróty klawiaturowe do ważnych linków</span><span class="sxs-lookup"><span data-stu-id="7d551-171">keyboard shortcuts to important links</span></span>  
  
- <span data-ttu-id="7d551-172">wszystkie elementy menu mają klucz dostępu; wszystkie przyciski mają klawisze skrótów, a wszystkie polecenia mają klawisz akceleratora.</span><span class="sxs-lookup"><span data-stu-id="7d551-172">all menu items have an access key; all buttons have accelerator keys, all commands have an accelerator key.</span></span>  
  
<a name="Do_not_let_Mouse_Location_Interfere_with_Keyboard"></a>

### <a name="do-not-let-mouse-location-interfere-with-keyboard-navigation"></a><span data-ttu-id="7d551-173">Nie Zezwalaj na zakłócanie lokalizacji myszy przy użyciu klawiatury</span><span class="sxs-lookup"><span data-stu-id="7d551-173">Do Not Let Mouse Location Interfere with Keyboard Navigation</span></span>  

 <span data-ttu-id="7d551-174">Lokalizacja myszy nie powinna zakłócać nawigowania po klawiaturze.</span><span class="sxs-lookup"><span data-stu-id="7d551-174">Mouse location should not interfere with keyboard navigation.</span></span> <span data-ttu-id="7d551-175">Jeśli na przykład mysz jest umieszczona w pewnym miejscu i użytkownik przechodzi przy użyciu klawiatury, kliknięcie myszą nie powinno nastąpić, chyba że zostanie zainicjowany przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7d551-175">For example, if the mouse is positioned some place and the user is navigating with the keyboard, a mouse click should not happen unless initiated by the user.</span></span>  
  
<a name="Multimodal_Interface"></a>

## <a name="multimodal-interface"></a><span data-ttu-id="7d551-176">Multimodal, interfejs</span><span class="sxs-lookup"><span data-stu-id="7d551-176">Multimodal Interface</span></span>  

 <span data-ttu-id="7d551-177">Najlepsze rozwiązania w tej sekcji zapewniają, że interfejs użytkownika aplikacji zawiera alternatywy dla elementów wizualizacji.</span><span class="sxs-lookup"><span data-stu-id="7d551-177">Best Practices in this section ensure that application UI includes alternatives for visual elements.</span></span>  
  
<a name="Provide_User_Selectable_Equivalents_for_Non_Text"></a>

### <a name="provide-user-selectable-equivalents-for-non-text-elements"></a><span data-ttu-id="7d551-178">Podaj User-Selectable odpowiedniki dla elementów innych niż tekstowe</span><span class="sxs-lookup"><span data-stu-id="7d551-178">Provide User-Selectable Equivalents for Non-Text Elements</span></span>  

 <span data-ttu-id="7d551-179">Dla każdego elementu nie będącego tekstem, należy wybrać odpowiedni dla użytkownika tekst, transkrypcje lub opisy audio, takie jak tekst alternatywny, napisy lub wizualne Opinie.</span><span class="sxs-lookup"><span data-stu-id="7d551-179">For each non-text element, provide a user-selectable equivalent for text, transcripts, or audio descriptions, such as alt text, captions, or visual feedback.</span></span>  
  
 <span data-ttu-id="7d551-180">Elementy inne niż tekstowe obejmują szeroką gamę elementów interfejsu użytkownika, takich jak obrazy, regiony mapy obrazu, animacje, applety, ramki, skrypty, przyciski graficzne, dźwięki, autonomiczne pliki audio i wideo.</span><span class="sxs-lookup"><span data-stu-id="7d551-180">Non-text elements cover a wide range of UI elements including: images, image map regions, animations, applets, frames, scripts, graphical buttons, sounds, stand-alone audio files, and video.</span></span> <span data-ttu-id="7d551-181">Elementy inne niż tekstowe są ważne, gdy zawierają informacje wizualne, mowę lub ogólne informacje o dźwięku, do których użytkownik potrzebuje dostępu, aby zrozumieć zawartość interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7d551-181">Non-text elements are important when they contain visual information, speech, or general audio information that the user needs access to in order to understand the content of the UI.</span></span>  
  
<a name="Use_Color_but_also_Provide_Alternatives_to_Color"></a>

### <a name="use-color-but-also-provide-alternatives-to-color"></a><span data-ttu-id="7d551-182">Użyj koloru, ale również Podaj alternatywy dla koloru</span><span class="sxs-lookup"><span data-stu-id="7d551-182">Use Color but Also Provide Alternatives to Color</span></span>  

 <span data-ttu-id="7d551-183">Użyj koloru, aby ulepszyć, wyróżnić lub powtórzyć powtarzanie informacji, które są wyświetlane w inny sposób, ale nie Komunikuj się z informacjami przy użyciu samego koloru.</span><span class="sxs-lookup"><span data-stu-id="7d551-183">Use color to enhance, emphasize, or reiterate information shown by other means, but do not communicate information by using color alone.</span></span> <span data-ttu-id="7d551-184">Użytkownicy, którzy są kolorami niewidomymi lub mają wyświetlacz monochromatyczny, potrzebują alternatywy do kolorowania.</span><span class="sxs-lookup"><span data-stu-id="7d551-184">Users who are color blind or have a monochrome display need alternatives to color.</span></span>  
  
<a name="Use_Standard_Input_APIs_with_Devices_Independent"></a>

### <a name="use-standard-input-apis-with-device-independent-calls"></a><span data-ttu-id="7d551-185">Używanie standardowych interfejsów API danych wejściowych z wywołaniami Device-Independent</span><span class="sxs-lookup"><span data-stu-id="7d551-185">Use Standard Input APIs with Device-Independent Calls</span></span>  

 <span data-ttu-id="7d551-186">Wywołania niezależne od urządzenia zapewniają równość funkcji klawiatury i myszy, a jednocześnie zapewniają technologię pomocniczą z wymaganymi informacjami o interfejsie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7d551-186">Device-independent calls ensure keyboard and mouse feature equality, while providing assistive technology with needed information about the UI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d551-187">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7d551-187">See also</span></span>

- <xref:System.Windows.Automation.Peers>
- <span data-ttu-id="7d551-188">[NumericUpDown kontrolkę niestandardową z motywem i przykładem obsługi automatyzacji interfejsu użytkownika](/previous-versions/dotnet/netframework-3.5/ms771573(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="7d551-188">[NumericUpDown Custom Control with Theme and UI Automation Support Sample](/previous-versions/dotnet/netframework-3.5/ms771573(v=vs.90))</span></span>
- [<span data-ttu-id="7d551-189">Wskazówki dotyczące projektowania interfejsu użytkownika klawiatury</span><span class="sxs-lookup"><span data-stu-id="7d551-189">Guidelines for Keyboard User Interface Design</span></span>](/previous-versions/windows/desktop/dnacc/guidelines-for-keyboard-user-interface-design)
