---
title: Zachowaj biały znak podczas serializacji-LINQ to XML
description: W przypadku serializowania drzewa XML można kontrolować biały znak na różne sposoby.
ms.date: 07/20/2015
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
ms.openlocfilehash: 6d907e68a2df3905794b555954330f31b5e75655
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553074"
---
# <a name="preserve-white-space-while-serializing-linq-to-xml"></a><span data-ttu-id="8ae47-103">Zachowaj biały znak podczas serializacji (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="8ae47-103">Preserve white space while serializing (LINQ to XML)</span></span>

<span data-ttu-id="8ae47-104">W tym artykule opisano sposób sterowania białym znakiem podczas serializowania drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="8ae47-104">This article describes how to control white space when serializing an XML tree.</span></span>

<span data-ttu-id="8ae47-105">Typowym scenariuszem jest odczytywanie wciętych plików XML, tworzenie drzewa XML w pamięci bez jakichkolwiek białych węzłów tekstowych (to nie zachowuje białych znaków), wykonywanie niektórych operacji na pliku XML, a następnie zapisywanie kodu XML z wcięciem.</span><span class="sxs-lookup"><span data-stu-id="8ae47-105">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), do some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="8ae47-106">Podczas serializacji pliku XML z formatowaniem zachowywana jest tylko znaczący biały znak w drzewie XML.</span><span class="sxs-lookup"><span data-stu-id="8ae47-106">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="8ae47-107">Jest to domyślne zachowanie LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="8ae47-107">This is the default behavior for LINQ to XML.</span></span>

<span data-ttu-id="8ae47-108">Inny typowy scenariusz polega na odczytaniu i zmodyfikowaniu kodu XML, który został już celowo wcięty.</span><span class="sxs-lookup"><span data-stu-id="8ae47-108">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="8ae47-109">W żaden sposób nie trzeba zmieniać tego wcięcia.</span><span class="sxs-lookup"><span data-stu-id="8ae47-109">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="8ae47-110">W tym celu w LINQ to XML jest zachowywany biały znak podczas ładowania lub analizowania kodu XML i wyłączania formatowania podczas serializacji XML.</span><span class="sxs-lookup"><span data-stu-id="8ae47-110">To do this in LINQ to XML, you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>

## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a><span data-ttu-id="8ae47-111">Białe zachowanie metod, które serializować drzewa XML</span><span class="sxs-lookup"><span data-stu-id="8ae47-111">White-space behavior of methods that serialize XML trees</span></span>

<span data-ttu-id="8ae47-112">Następujące metody w <xref:System.Xml.Linq.XElement> i <xref:System.Xml.Linq.XDocument> klasy serializacji drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="8ae47-112">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes serialize an XML tree.</span></span> <span data-ttu-id="8ae47-113">Można serializować drzewo XML do pliku, a <xref:System.IO.TextReader> lub <xref:System.Xml.XmlReader> .</span><span class="sxs-lookup"><span data-stu-id="8ae47-113">You can serialize an XML tree to a file, a <xref:System.IO.TextReader>, or an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="8ae47-114">`ToString`Metoda jest serializowana do ciągu.</span><span class="sxs-lookup"><span data-stu-id="8ae47-114">The `ToString` method serializes to a string.</span></span>

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8ae47-115">XElement. ToString ()</span><span class="sxs-lookup"><span data-stu-id="8ae47-115">XElement.ToString()</span></span>](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)
- [<span data-ttu-id="8ae47-116">XDocument. ToString ()</span><span class="sxs-lookup"><span data-stu-id="8ae47-116">XDocument.ToString()</span></span>](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)

<span data-ttu-id="8ae47-117">Jeśli metoda nie przyjmuje <xref:System.Xml.Linq.SaveOptions> jako argument, metoda będzie formatować (wcięcie) serializacji XML.</span><span class="sxs-lookup"><span data-stu-id="8ae47-117">If the method doesn't take <xref:System.Xml.Linq.SaveOptions> as an argument, then the method will format (indent) the serialized XML.</span></span> <span data-ttu-id="8ae47-118">W takim przypadku wszystkie nieznaczące białe znaki w drzewie XML są odrzucane.</span><span class="sxs-lookup"><span data-stu-id="8ae47-118">In this case, all insignificant white space in the XML tree is discarded.</span></span>

<span data-ttu-id="8ae47-119">Jeśli metoda przyjmuje <xref:System.Xml.Linq.SaveOptions> jako argument, można określić, że metoda nie formatuje (wcięcie) serializacji XML.</span><span class="sxs-lookup"><span data-stu-id="8ae47-119">If the method does take <xref:System.Xml.Linq.SaveOptions> as an argument, then you can specify that the method not format (indent) the serialized XML.</span></span> <span data-ttu-id="8ae47-120">W takim przypadku wszystkie odstępy w drzewie XML są zachowywane.</span><span class="sxs-lookup"><span data-stu-id="8ae47-120">In this case, all white space in the XML tree is preserved.</span></span>
