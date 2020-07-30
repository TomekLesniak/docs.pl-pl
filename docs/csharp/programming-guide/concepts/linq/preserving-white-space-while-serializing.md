---
title: Zachowywanie białych znaków podczas Serializing3
description: Dowiedz się, jak sterować białym znakiem podczas serializowania drzewa XML przy użyciu metod w klasach XElement i XDocument.
ms.date: 07/20/2015
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
ms.openlocfilehash: 01e68671e2fde1a2b5b1d0bc429841077ba0205f
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303416"
---
# <a name="preserving-white-space-while-serializing"></a><span data-ttu-id="afb71-103">Zachowywanie białych znaków podczas serializowania</span><span class="sxs-lookup"><span data-stu-id="afb71-103">Preserving White Space While Serializing</span></span>
<span data-ttu-id="afb71-104">W tym temacie opisano, jak sterować białym znakiem podczas serializowania drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="afb71-104">This topic describes how to control white space when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="afb71-105">Typowym scenariuszem jest odczytywanie wcięć XML, tworzenie drzewa XML w pamięci bez żadnych białych węzłów tekstowych (to nie zachowuje białych znaków), wykonywanie niektórych operacji na pliku XML, a następnie zapisywanie kodu XML z wcięciem.</span><span class="sxs-lookup"><span data-stu-id="afb71-105">A common scenario is to read indented XML, create an in-memory XML tree without any white-space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="afb71-106">Podczas serializacji pliku XML z formatowaniem zachowywana jest tylko znaczący biały znak w drzewie XML.</span><span class="sxs-lookup"><span data-stu-id="afb71-106">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="afb71-107">Jest to zachowanie domyślne dla programu [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="afb71-107">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="afb71-108">Inny typowy scenariusz polega na odczytaniu i zmodyfikowaniu kodu XML, który został już celowo wcięty.</span><span class="sxs-lookup"><span data-stu-id="afb71-108">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="afb71-109">W żaden sposób nie trzeba zmieniać tego wcięcia.</span><span class="sxs-lookup"><span data-stu-id="afb71-109">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="afb71-110">W tym celu [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] należy zachować biały znak podczas ładowania lub analizowania kodu XML i wyłączyć formatowanie podczas serializacji XML.</span><span class="sxs-lookup"><span data-stu-id="afb71-110">To do this in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a><span data-ttu-id="afb71-111">Białe zachowanie metod, które serializować drzewa XML</span><span class="sxs-lookup"><span data-stu-id="afb71-111">White-Space Behavior of Methods that Serialize XML Trees</span></span>  
 <span data-ttu-id="afb71-112">Następujące metody w <xref:System.Xml.Linq.XElement> i <xref:System.Xml.Linq.XDocument> klasy serializacji drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="afb71-112">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes serialize an XML tree.</span></span> <span data-ttu-id="afb71-113">Można serializować drzewo XML do pliku, a <xref:System.IO.TextReader> lub <xref:System.Xml.XmlReader> .</span><span class="sxs-lookup"><span data-stu-id="afb71-113">You can serialize an XML tree to a file, a <xref:System.IO.TextReader>, or an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="afb71-114">`ToString`Metoda jest serializowana do ciągu.</span><span class="sxs-lookup"><span data-stu-id="afb71-114">The `ToString` method serializes to a string.</span></span>  
  
- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
- [<span data-ttu-id="afb71-115">XElement. ToString ()</span><span class="sxs-lookup"><span data-stu-id="afb71-115">XElement.ToString()</span></span>](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)
  
- [<span data-ttu-id="afb71-116">XDocument. ToString ()</span><span class="sxs-lookup"><span data-stu-id="afb71-116">XDocument.ToString()</span></span>](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)
  
 <span data-ttu-id="afb71-117">Jeśli metoda nie przyjmuje <xref:System.Xml.Linq.SaveOptions> argumentu, metoda będzie formatować (wcięcie) serializacji XML.</span><span class="sxs-lookup"><span data-stu-id="afb71-117">If the method does not take <xref:System.Xml.Linq.SaveOptions> as an argument, then the method will format (indent) the serialized XML.</span></span> <span data-ttu-id="afb71-118">W takim przypadku wszystkie nieznaczące białe znaki w drzewie XML są odrzucane.</span><span class="sxs-lookup"><span data-stu-id="afb71-118">In this case, all insignificant white space in the XML tree is discarded.</span></span>  
  
 <span data-ttu-id="afb71-119">Jeśli metoda przyjmuje <xref:System.Xml.Linq.SaveOptions> jako argument, można określić, że metoda nie formatuje (wcięcie) serializacji XML.</span><span class="sxs-lookup"><span data-stu-id="afb71-119">If the method does take <xref:System.Xml.Linq.SaveOptions> as an argument, then you can specify that the method not format (indent) the serialized XML.</span></span> <span data-ttu-id="afb71-120">W takim przypadku wszystkie odstępy w drzewie XML są zachowywane.</span><span class="sxs-lookup"><span data-stu-id="afb71-120">In this case, all white space in the XML tree is preserved.</span></span>  
