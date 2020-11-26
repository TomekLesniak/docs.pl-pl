---
title: Konwencje kodowania
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: eae283c757ddeb1290c15d82a41c8028a8941e63
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91059161"
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="516e7-102">Visual Basic — Konwencje kodowania</span><span class="sxs-lookup"><span data-stu-id="516e7-102">Visual Basic Coding Conventions</span></span>

<span data-ttu-id="516e7-103">Firma Microsoft opracowuje przykłady i dokumentację, które są zgodne z wytycznymi w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="516e7-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="516e7-104">Jeśli przestrzegasz tych samych konwencji kodowania, możesz uzyskać następujące korzyści:</span><span class="sxs-lookup"><span data-stu-id="516e7-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
- <span data-ttu-id="516e7-105">Twój kod będzie miał spójny wygląd, dzięki czemu czytelnicy mogą lepiej skupić się na zawartości, a nie na układzie.</span><span class="sxs-lookup"><span data-stu-id="516e7-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
- <span data-ttu-id="516e7-106">Czytelnicy mogą szybciej zrozumieć swój kod, ponieważ może to spowodować założenie założeń na podstawie poprzedniego środowiska.</span><span class="sxs-lookup"><span data-stu-id="516e7-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
- <span data-ttu-id="516e7-107">Można łatwo kopiować, zmieniać i konserwować kod.</span><span class="sxs-lookup"><span data-stu-id="516e7-107">You can copy, change, and maintain the code more easily.</span></span>  
  
- <span data-ttu-id="516e7-108">W celu zagwarantowania, że kod demonstruje "najlepsze rozwiązania" Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="516e7-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="516e7-109">Konwencje nazewnictwa</span><span class="sxs-lookup"><span data-stu-id="516e7-109">Naming Conventions</span></span>  
  
- <span data-ttu-id="516e7-110">Aby uzyskać informacje na temat określania zasad nazewnictwa, zobacz temat Omówienie [nazewnictwa](../../../standard/design-guidelines/naming-guidelines.md) .</span><span class="sxs-lookup"><span data-stu-id="516e7-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
- <span data-ttu-id="516e7-111">Nie należy używać "my" ani "my" jako części nazwy zmiennej.</span><span class="sxs-lookup"><span data-stu-id="516e7-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="516e7-112">To rozwiązanie tworzy pomyłkę z `My` obiektami.</span><span class="sxs-lookup"><span data-stu-id="516e7-112">This practice creates confusion with the `My` objects.</span></span>  
  
- <span data-ttu-id="516e7-113">Nie trzeba zmieniać nazw obiektów w generowanym automatycznie kodzie, aby dopasować je do wytycznych.</span><span class="sxs-lookup"><span data-stu-id="516e7-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="516e7-114">Konwencje układu</span><span class="sxs-lookup"><span data-stu-id="516e7-114">Layout Conventions</span></span>  
  
- <span data-ttu-id="516e7-115">Wstaw tabulatory jako spacje i używaj inteligentnych wcięć z czterema znakami odstępu.</span><span class="sxs-lookup"><span data-stu-id="516e7-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
- <span data-ttu-id="516e7-116">Korzystaj **z** przeglądarki, aby ponownie formatować kod w edytorze kodu.</span><span class="sxs-lookup"><span data-stu-id="516e7-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="516e7-117">Aby uzyskać więcej informacji, zobacz [Opcje, Edytor tekstu, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="516e7-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
- <span data-ttu-id="516e7-118">Używaj tylko jednej instrukcji w wierszu.</span><span class="sxs-lookup"><span data-stu-id="516e7-118">Use only one statement per line.</span></span> <span data-ttu-id="516e7-119">Nie używaj znaku separatora wiersza Visual Basic (:).</span><span class="sxs-lookup"><span data-stu-id="516e7-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
- <span data-ttu-id="516e7-120">Unikaj używania jawnego znaku kontynuacji wiersza "_" na rzecz niejawnej kontynuacji wiersza wszędzie tam, gdzie język ten zezwala.</span><span class="sxs-lookup"><span data-stu-id="516e7-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
- <span data-ttu-id="516e7-121">Użyj tylko jednej deklaracji na wiersz.</span><span class="sxs-lookup"><span data-stu-id="516e7-121">Use only one declaration per line.</span></span>  
  
- <span data-ttu-id="516e7-122">Jeśli podczas tworzenia **listy (ponowne formatowanie) kodu** nie są automatycznie formatowane linie kontynuacji, ręcznie Zwiększ wcięcie wierszy kontynuacji o jeden tabulator.</span><span class="sxs-lookup"><span data-stu-id="516e7-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="516e7-123">Jednak zawsze należy wyrównać elementy na liście.</span><span class="sxs-lookup"><span data-stu-id="516e7-123">However, always left-align items in a list.</span></span>  
  
    ```vb  
    a As Integer,  
    b As Integer  
    ```  
  
- <span data-ttu-id="516e7-124">Dodaj co najmniej jeden pusty wiersz między definicją metody i właściwości.</span><span class="sxs-lookup"><span data-stu-id="516e7-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="516e7-125">Konwencje komentowania</span><span class="sxs-lookup"><span data-stu-id="516e7-125">Commenting Conventions</span></span>  
  
- <span data-ttu-id="516e7-126">Umieść komentarze w osobnym wierszu zamiast na końcu wiersza kodu.</span><span class="sxs-lookup"><span data-stu-id="516e7-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
- <span data-ttu-id="516e7-127">Zacznij komentować tekst komentarza z wielką literą i Zakończ tekst komentarza z kropką.</span><span class="sxs-lookup"><span data-stu-id="516e7-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
- <span data-ttu-id="516e7-128">Wstaw jedną spację między ogranicznikiem komentarza (') a tekstem komentarza.</span><span class="sxs-lookup"><span data-stu-id="516e7-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#2)]  
  
- <span data-ttu-id="516e7-129">Nie otaczaj komentarzy sformatowanymi blokami gwiazdek.</span><span class="sxs-lookup"><span data-stu-id="516e7-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="516e7-130">Struktura programu</span><span class="sxs-lookup"><span data-stu-id="516e7-130">Program Structure</span></span>  
  
- <span data-ttu-id="516e7-131">Korzystając z `Main` metody, należy użyć domyślnej konstrukcji dla nowych aplikacji konsolowych i użyć `My` dla argumentów wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="516e7-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#3)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="516e7-132">Wytyczne dotyczące języka</span><span class="sxs-lookup"><span data-stu-id="516e7-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="516e7-133">Typ danych ciągu</span><span class="sxs-lookup"><span data-stu-id="516e7-133">String Data Type</span></span>  
  
- <span data-ttu-id="516e7-134">Użyj [interpolacji ciągów](../language-features/strings/interpolated-strings.md) , aby połączyć krótkie ciągi, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="516e7-134">Use [string interpolation](../language-features/strings/interpolated-strings.md) to concatenate short strings, as shown in the following code.</span></span>
  
     ```vb
     MsgBox($"hello{vbCrLf}goodbye")
     ```
  
- <span data-ttu-id="516e7-135">Aby dołączyć ciągi w pętlach, użyj <xref:System.Text.StringBuilder> obiektu.</span><span class="sxs-lookup"><span data-stu-id="516e7-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#5)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="516e7-136">Elementy delegowane swobodne w obsłudze zdarzeń</span><span class="sxs-lookup"><span data-stu-id="516e7-136">Relaxed Delegates in Event Handlers</span></span>  

 <span data-ttu-id="516e7-137">Nie należy jawnie kwalifikować argumentów (Object i EventArgs) do programów obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="516e7-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="516e7-138">Jeśli nie używasz argumentów zdarzeń, które są przekazane do zdarzenia (na przykład nadawcy jako obiekt, e jako EventArgs), użyj swobodnych delegatów i pozostaw argumenty zdarzeń w kodzie:</span><span class="sxs-lookup"><span data-stu-id="516e7-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#7)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="516e7-139">Typ danych bez znaku</span><span class="sxs-lookup"><span data-stu-id="516e7-139">Unsigned Data Type</span></span>  
  
- <span data-ttu-id="516e7-140">Używaj `Integer` zamiast niepodpisanych typów, z wyjątkiem sytuacji, w których jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="516e7-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="516e7-141">Tablice</span><span class="sxs-lookup"><span data-stu-id="516e7-141">Arrays</span></span>  
  
- <span data-ttu-id="516e7-142">Podczas inicjowania tablic w wierszu deklaracji należy użyć krótkiej składni.</span><span class="sxs-lookup"><span data-stu-id="516e7-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="516e7-143">Na przykład użyj następującej składni.</span><span class="sxs-lookup"><span data-stu-id="516e7-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#8)]  
  
     <span data-ttu-id="516e7-144">Nie należy używać następującej składni.</span><span class="sxs-lookup"><span data-stu-id="516e7-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#9)]  
  
- <span data-ttu-id="516e7-145">Umieść oznaczenie tablicy na typie, a nie na zmiennej.</span><span class="sxs-lookup"><span data-stu-id="516e7-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="516e7-146">Na przykład użyj następującej składni:</span><span class="sxs-lookup"><span data-stu-id="516e7-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#11)]  
  
     <span data-ttu-id="516e7-147">Nie należy używać następującej składni:</span><span class="sxs-lookup"><span data-stu-id="516e7-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#10)]  
  
- <span data-ttu-id="516e7-148">Użyj składni {} podczas deklarowania i inicjowania tablic podstawowych typów danych.</span><span class="sxs-lookup"><span data-stu-id="516e7-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="516e7-149">Na przykład użyj następującej składni:</span><span class="sxs-lookup"><span data-stu-id="516e7-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#12)]  
  
     <span data-ttu-id="516e7-150">Nie należy używać następującej składni:</span><span class="sxs-lookup"><span data-stu-id="516e7-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#13)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="516e7-151">Używanie słowa kluczowego with</span><span class="sxs-lookup"><span data-stu-id="516e7-151">Use the With Keyword</span></span>  

 <span data-ttu-id="516e7-152">Podczas wykonywania serii wywołań do jednego obiektu, rozważ użycie `With` słowa kluczowego:</span><span class="sxs-lookup"><span data-stu-id="516e7-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#15)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="516e7-153">Użyj try... Instrukcje catch i Using w przypadku korzystania z obsługi wyjątków</span><span class="sxs-lookup"><span data-stu-id="516e7-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  

 <span data-ttu-id="516e7-154">Nie należy używać `On Error Goto` .</span><span class="sxs-lookup"><span data-stu-id="516e7-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="516e7-155">Użycie słowa kluczowego IsNot</span><span class="sxs-lookup"><span data-stu-id="516e7-155">Use the IsNot Keyword</span></span>  

 <span data-ttu-id="516e7-156">Użyj `IsNot` słowa kluczowego zamiast `Not...Is Nothing` .</span><span class="sxs-lookup"><span data-stu-id="516e7-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="516e7-157">New — słowo kluczowe</span><span class="sxs-lookup"><span data-stu-id="516e7-157">New Keyword</span></span>  
  
- <span data-ttu-id="516e7-158">Użyj krótkiego tworzenia wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="516e7-158">Use short instantiation.</span></span> <span data-ttu-id="516e7-159">Na przykład użyj następującej składni:</span><span class="sxs-lookup"><span data-stu-id="516e7-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#21)]  
  
     <span data-ttu-id="516e7-160">Poprzedni wiersz jest równoważny z:</span><span class="sxs-lookup"><span data-stu-id="516e7-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#22)]  
  
- <span data-ttu-id="516e7-161">Użyj inicjatorów obiektów dla nowych obiektów zamiast konstruktora bez parametrów:</span><span class="sxs-lookup"><span data-stu-id="516e7-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#23)]  
  
### <a name="event-handling"></a><span data-ttu-id="516e7-162">Obsługa zdarzeń</span><span class="sxs-lookup"><span data-stu-id="516e7-162">Event Handling</span></span>  
  
- <span data-ttu-id="516e7-163">Użyj `Handles` zamiast `AddHandler` :</span><span class="sxs-lookup"><span data-stu-id="516e7-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#24)]  
  
- <span data-ttu-id="516e7-164">Użyj `AddressOf` i nie twórz wystąpienia delegata jawnie:</span><span class="sxs-lookup"><span data-stu-id="516e7-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#25)]  
  
- <span data-ttu-id="516e7-165">Podczas definiowania zdarzenia Użyj krótkiej składni i pozwól kompilatorowi definiować delegata:</span><span class="sxs-lookup"><span data-stu-id="516e7-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#26)]  
  
- <span data-ttu-id="516e7-166">Nie sprawdzaj, czy zdarzenie jest `Nothing` (null) przed wywołaniem `RaiseEvent` metody.</span><span class="sxs-lookup"><span data-stu-id="516e7-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="516e7-167">`RaiseEvent` sprawdza `Nothing` przed podjęciem zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="516e7-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="516e7-168">Korzystanie z udostępnionych elementów członkowskich</span><span class="sxs-lookup"><span data-stu-id="516e7-168">Using Shared Members</span></span>  

 <span data-ttu-id="516e7-169">Wywołaj `Shared` członków przy użyciu nazwy klasy, a nie z zmiennej wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="516e7-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="516e7-170">Użyj literałów XML</span><span class="sxs-lookup"><span data-stu-id="516e7-170">Use XML Literals</span></span>  

 <span data-ttu-id="516e7-171">Literały XML upraszczają Najczęstsze zadania, które można napotkać podczas pracy z XML (na przykład ładowania, wykonywania zapytań i przekształcania).</span><span class="sxs-lookup"><span data-stu-id="516e7-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="516e7-172">Opracowując with XML, postępuj zgodnie z następującymi wskazówkami:</span><span class="sxs-lookup"><span data-stu-id="516e7-172">When you develop with XML, follow these guidelines:</span></span>  
  
- <span data-ttu-id="516e7-173">Za pomocą literałów XML można tworzyć dokumenty i fragmenty XML, zamiast bezpośrednio wywoływanie interfejsów API XML.</span><span class="sxs-lookup"><span data-stu-id="516e7-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
- <span data-ttu-id="516e7-174">Zaimportuj przestrzenie nazw XML na poziomie pliku lub projektu, aby skorzystać z optymalizacji wydajności dla literałów XML.</span><span class="sxs-lookup"><span data-stu-id="516e7-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
- <span data-ttu-id="516e7-175">Użyj właściwości osi XML, aby uzyskać dostęp do elementów i atrybutów w dokumencie XML.</span><span class="sxs-lookup"><span data-stu-id="516e7-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
- <span data-ttu-id="516e7-176">Użyj osadzonych wyrażeń, aby dołączyć wartości i utworzyć XML z istniejących wartości zamiast używać wywołań interfejsu API, takich jak `Add` Metoda:</span><span class="sxs-lookup"><span data-stu-id="516e7-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#27)]  
  
### <a name="linq-queries"></a><span data-ttu-id="516e7-177">Zapytania LINQ</span><span class="sxs-lookup"><span data-stu-id="516e7-177">LINQ Queries</span></span>  
  
- <span data-ttu-id="516e7-178">Użyj znaczących nazw dla zmiennych zapytania:</span><span class="sxs-lookup"><span data-stu-id="516e7-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#28)]  
  
- <span data-ttu-id="516e7-179">Podaj nazwy dla elementów w zapytaniu, aby upewnić się, że nazwy właściwości typów anonimowych są prawidłowo pisane wielkimi literami przy użyciu wielkości liter w Pascalu:</span><span class="sxs-lookup"><span data-stu-id="516e7-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#29)]  
  
- <span data-ttu-id="516e7-180">Zmień nazwę właściwości, gdy nazwy właściwości w wyniku byłyby niejednoznaczne.</span><span class="sxs-lookup"><span data-stu-id="516e7-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="516e7-181">Na przykład, jeśli zapytanie zwraca nazwę klienta i identyfikator zamówienia, zmień ich nazwy zamiast opuszczania ich jako `Name` i `ID` w wyniku:</span><span class="sxs-lookup"><span data-stu-id="516e7-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#30)]  
  
- <span data-ttu-id="516e7-182">Użyj wnioskowania o typie w deklaracji zmiennych zapytania i zmiennych zakresu:</span><span class="sxs-lookup"><span data-stu-id="516e7-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#31)]  
  
- <span data-ttu-id="516e7-183">Wyrównaj klauzule zapytania w `From` instrukcji:</span><span class="sxs-lookup"><span data-stu-id="516e7-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#32)]  
  
- <span data-ttu-id="516e7-184">`Where`Klauzule use przed innymi klauzulami zapytań, tak aby późniejsze klauzule zapytań działały na filtrowanym zestawie danych:</span><span class="sxs-lookup"><span data-stu-id="516e7-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#33)]  
  
- <span data-ttu-id="516e7-185">Użyj `Join` klauzuli, aby jawnie zdefiniować operację Join zamiast używać `Where` klauzuli do niejawnego definiowania operacji JOIN:</span><span class="sxs-lookup"><span data-stu-id="516e7-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="516e7-186">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="516e7-186">See also</span></span>

- [<span data-ttu-id="516e7-187">Wytyczne dotyczące bezpiecznego programowania</span><span class="sxs-lookup"><span data-stu-id="516e7-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
