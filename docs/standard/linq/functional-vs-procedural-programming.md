---
title: Programowanie funkcjonalne a proceduralne
description: LINQ to XML obsługuje zarówno technik konstruowania funkcjonalnego, jak i proceduralnego tworzenia aplikacji XML. Konstrukcja funkcjonalna jest podejściem deklaratywnym. Techniki proceduralne obsługują modyfikację drzew XML w pamięci.
ms.date: 07/20/2015
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
ms.openlocfilehash: a2753a31e88fd338dad61063f559431869b9e17f
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552996"
---
# <a name="functional-vs-procedural-programming-linq-to-xml"></a><span data-ttu-id="a40cd-105">Programowanie funkcjonalne a proceduralne (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="a40cd-105">Functional vs. procedural programming (LINQ to XML)</span></span>

<span data-ttu-id="a40cd-106">Istnieją różne typy aplikacji XML:</span><span class="sxs-lookup"><span data-stu-id="a40cd-106">There are various types of XML applications:</span></span>

- <span data-ttu-id="a40cd-107">Niektóre aplikacje pobierają źródłowe dokumenty XML i generują nowe dokumenty XML, które znajdują się w innym kształcie niż dokumenty źródłowe.</span><span class="sxs-lookup"><span data-stu-id="a40cd-107">Some applications take source XML documents, and produce new XML documents that are in a different shape than the source documents.</span></span>
- <span data-ttu-id="a40cd-108">Niektóre aplikacje pobierają źródłowe dokumenty XML i generują dokumenty z wynikami całkowicie różnymi formularzami, takimi jak pliki tekstowe HTML lub CSV.</span><span class="sxs-lookup"><span data-stu-id="a40cd-108">Some applications take source XML documents, and produce result documents in an entirely different form, such as HTML or CSV text files.</span></span>
- <span data-ttu-id="a40cd-109">Niektóre aplikacje pobierają źródłowe dokumenty XML i wstawiają rekordy do bazy danych.</span><span class="sxs-lookup"><span data-stu-id="a40cd-109">Some applications take source XML documents, and insert records into a database.</span></span>
- <span data-ttu-id="a40cd-110">Niektóre aplikacje pobierają dane z innego źródła, takiego jak baza danych, i tworzy z niego dokumenty XML.</span><span class="sxs-lookup"><span data-stu-id="a40cd-110">Some applications take data from another source, such as a database, and create XML documents from it.</span></span>

<span data-ttu-id="a40cd-111">Nie wszystkie typy aplikacji XML, ale są to reprezentatywny zestaw typów funkcji, które programista XML musi zaimplementować.</span><span class="sxs-lookup"><span data-stu-id="a40cd-111">These aren't all of the types of XML applications, but these are a representative set of the types of functionality that an XML programmer has to implement.</span></span>

<span data-ttu-id="a40cd-112">W przypadku wszystkich typów aplikacji istnieją dwie podejścia z kontrastem, które może podjąć Deweloper:</span><span class="sxs-lookup"><span data-stu-id="a40cd-112">With all of these types of applications, there are two contrasting approaches that a developer can take:</span></span>

- <span data-ttu-id="a40cd-113">Funkcjonalne konstruowanie przy użyciu podejścia deklaratywnego.</span><span class="sxs-lookup"><span data-stu-id="a40cd-113">Functional construction using a declarative approach.</span></span>
- <span data-ttu-id="a40cd-114">Modyfikowanie drzewa XML w pamięci przy użyciu kodu proceduralnego.</span><span class="sxs-lookup"><span data-stu-id="a40cd-114">In-memory XML tree modification using procedural code.</span></span>

<span data-ttu-id="a40cd-115">LINQ to XML obsługuje oba podejścia.</span><span class="sxs-lookup"><span data-stu-id="a40cd-115">LINQ to XML supports both approaches.</span></span>

<span data-ttu-id="a40cd-116">Korzystając z podejścia funkcjonalnego, należy napisać przekształcenia, które pobierają dokumenty źródłowe i generować zupełnie nowe dokumenty wynikowe z żądanym kształtem.</span><span class="sxs-lookup"><span data-stu-id="a40cd-116">When using the functional approach, you write transformations that take the source documents and generate completely new result documents with the desired shape.</span></span>

<span data-ttu-id="a40cd-117">Podczas modyfikowania drzewa XML w miejscu należy napisać kod, który przechodzi przez węzły w drzewie XML w pamięci, wstawiając, usuwając i modyfikując węzły, w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="a40cd-117">When modifying an XML tree in place, you write code that traverses and navigates through nodes in an in-memory XML tree, inserting, deleting, and modifying nodes as necessary.</span></span>

<span data-ttu-id="a40cd-118">Możesz użyć LINQ to XML z dowolnego podejścia.</span><span class="sxs-lookup"><span data-stu-id="a40cd-118">You can use LINQ to XML with either approach.</span></span> <span data-ttu-id="a40cd-119">Używasz tych samych klas, a w niektórych przypadkach te same metody.</span><span class="sxs-lookup"><span data-stu-id="a40cd-119">You use the same classes, and in some cases the same methods.</span></span> <span data-ttu-id="a40cd-120">Jednak struktura i cele obu tych metod są różne.</span><span class="sxs-lookup"><span data-stu-id="a40cd-120">However, the structure and goals of the two approaches are different.</span></span> <span data-ttu-id="a40cd-121">Na przykład w różnych sytuacjach jedno lub inne podejście często ma lepszą wydajność i będzie używać więcej lub mniej pamięci.</span><span class="sxs-lookup"><span data-stu-id="a40cd-121">For example, in different situations, one or the other approach will often have better performance, and use more or less memory.</span></span> <span data-ttu-id="a40cd-122">Ponadto jedno lub inne podejście będzie łatwiejsze do pisania i uzyskania bardziej możliwego do utrzymania kodu.</span><span class="sxs-lookup"><span data-stu-id="a40cd-122">In addition, one or the other approach will be easier to write and yield more maintainable code.</span></span>

<span data-ttu-id="a40cd-123">Aby wyświetlić dwa podejścia z kontrastem, zobacz [Modyfikowanie drzewa XML w pamięci a konstrukcja funkcjonalna](in-memory-xml-tree-modification-vs-functional-construction.md).</span><span class="sxs-lookup"><span data-stu-id="a40cd-123">To see the two approaches contrasted, see [In-memory XML tree modification vs. functional construction](in-memory-xml-tree-modification-vs-functional-construction.md).</span></span>

<span data-ttu-id="a40cd-124">Aby zapoznać się z samouczkiem dotyczącym pisania transformacji funkcjonalnych, zobacz [wprowadzenie do czystych transformacji funkcjonalnych](introduction-pure-functional-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="a40cd-124">For a tutorial on writing functional transformations, see [Introduction to pure functional transformations](introduction-pure-functional-transformations.md).</span></span>
