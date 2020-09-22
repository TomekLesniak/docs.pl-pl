---
title: Wystąpiły błędy podczas kompilowania schematów XML w projekcie
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 17c31301e28c757954e72ba103254f038905671f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874355"
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="9c109-102">Wystąpiły błędy podczas kompilowania schematów XML w projekcie</span><span class="sxs-lookup"><span data-stu-id="9c109-102">Errors occurred while compiling the XML schemas in the project</span></span>

<span data-ttu-id="9c109-103">Wystąpiły błędy podczas kompilowania schematów XML w projekcie.</span><span class="sxs-lookup"><span data-stu-id="9c109-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="9c109-104">Z tego powodu funkcja IntelliSense języka XML jest niedostępna.</span><span class="sxs-lookup"><span data-stu-id="9c109-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="9c109-105">Wystąpił błąd w schemacie definicji schematu XML (XSD) zawartym w projekcie.</span><span class="sxs-lookup"><span data-stu-id="9c109-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="9c109-106">Ten błąd występuje po dodaniu pliku schematu XSD (XSD), który powoduje konflikt z istniejącym zestawem schematu XSD dla projektu.</span><span class="sxs-lookup"><span data-stu-id="9c109-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="9c109-107">**Identyfikator błędu:** BC36810</span><span class="sxs-lookup"><span data-stu-id="9c109-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9c109-108">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="9c109-108">To correct this error</span></span>  
  
- <span data-ttu-id="9c109-109">Kliknij dwukrotnie ostrzeżenie w oknie **Lista błędów** .</span><span class="sxs-lookup"><span data-stu-id="9c109-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="9c109-110">Visual Basic przejdzie do lokalizacji w pliku XSD, który jest źródłem ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="9c109-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="9c109-111">Popraw błąd w schemacie XSD.</span><span class="sxs-lookup"><span data-stu-id="9c109-111">Correct the error in the XSD schema.</span></span>  
  
- <span data-ttu-id="9c109-112">Upewnij się, że w projekcie są zawarte wszystkie wymagane pliki schematu XSD (XSD).</span><span class="sxs-lookup"><span data-stu-id="9c109-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="9c109-113">Może być konieczne kliknięcie przycisku **Pokaż wszystkie pliki** w menu **projekt** , aby wyświetlić pliki XSD w **Eksplorator rozwiązań**.</span><span class="sxs-lookup"><span data-stu-id="9c109-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="9c109-114">Kliknij prawym przyciskiem myszy plik XSD, a następnie kliknij pozycję **Dołącz w projekcie** , aby dołączyć plik do projektu.</span><span class="sxs-lookup"><span data-stu-id="9c109-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
- <span data-ttu-id="9c109-115">Jeśli używasz Kreatora XML do schematu, ten błąd może wystąpić w przypadku wywnioskowania schematów więcej niż jeden raz z tego samego źródła.</span><span class="sxs-lookup"><span data-stu-id="9c109-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="9c109-116">W takim przypadku można usunąć istniejące pliki schematu XSD z projektu, dodać nowe XML do szablonu elementu schematu, a następnie udostępnić kreatora XML do schematu wszystkim odpowiednim źródłom XML dla projektu.</span><span class="sxs-lookup"><span data-stu-id="9c109-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
- <span data-ttu-id="9c109-117">Jeśli żaden błąd nie zostanie zidentyfikowany w schemacie XSD, kompilator XML może nie mieć wystarczającej ilości informacji, aby przedstawić szczegółowy komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="9c109-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="9c109-118">Jeśli masz pewność, że przestrzenie nazw XML dla plików XSD zawartych w projekcie są zgodne z przestrzeniami nazw XML określonymi dla zestawu schematu XML w programie Visual Studio, możesz uzyskać bardziej szczegółowe informacje o błędzie.</span><span class="sxs-lookup"><span data-stu-id="9c109-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c109-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9c109-119">See also</span></span>

- [<span data-ttu-id="9c109-120">Okno Lista błędów</span><span class="sxs-lookup"><span data-stu-id="9c109-120">Error List Window</span></span>](/visualstudio/ide/reference/error-list-window)
- [<span data-ttu-id="9c109-121">XML</span><span class="sxs-lookup"><span data-stu-id="9c109-121">XML</span></span>](../../programming-guide/language-features/xml/index.md)
