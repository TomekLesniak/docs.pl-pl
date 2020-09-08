---
title: Omówienie drzew XML zapytań-LINQ to XML
description: Dowiedz się, jak badać drzewo XML oraz jak łączyć zapytania i konstrukcje funkcjonalne, aby zmienić kształt drzewa.
ms.date: 07/20/2015
ms.assetid: 2e35c1ab-08c8-4378-9ca8-8ff344756eda
ms.openlocfilehash: 3529650aa5ee0575331653f5714c841d1fc1dfb5
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553705"
---
# <a name="query-xml-trees-overview-linq-to-xml"></a><span data-ttu-id="01980-103">Omówienie drzew XML zapytań (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="01980-103">Query XML trees overview (LINQ to XML)</span></span>

<span data-ttu-id="01980-104">Po utworzeniu wystąpienia drzewa XML, Pisanie zapytań jest najbardziej skutecznym sposobem wyodrębnienia danych z drzewa.</span><span class="sxs-lookup"><span data-stu-id="01980-104">After you've instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="01980-105">Ponadto zapytanie połączone z konstrukcją funkcjonalną umożliwia wygenerowanie nowego dokumentu XML, który ma inny kształt od oryginalnego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="01980-105">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>

<span data-ttu-id="01980-106">Aby uzyskać ogólne informacje na temat zapytań LINQ, zobacz:</span><span class="sxs-lookup"><span data-stu-id="01980-106">For background information about LINQ queries, see:</span></span>

- [<span data-ttu-id="01980-107">Wprowadzenie do kwerend LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="01980-107">Introduction to LINQ Queries (C#)</span></span>](../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [<span data-ttu-id="01980-108">Pisanie pierwszego zapytania LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01980-108">Writing Your First LINQ Query (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)

## <a name="in-this-section"></a><span data-ttu-id="01980-109">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="01980-109">In this section</span></span>

<span data-ttu-id="01980-110">W tej części artykułów przedstawiono informacje, w tym przykłady dotyczące LINQ to XML zapytań.</span><span class="sxs-lookup"><span data-stu-id="01980-110">This section of articles provides information, including examples, about LINQ to XML queries.</span></span> <span data-ttu-id="01980-111">Obejmuje następujące podsekcje:</span><span class="sxs-lookup"><span data-stu-id="01980-111">It comprises the following subsections:</span></span>

|<span data-ttu-id="01980-112">Artykuł</span><span class="sxs-lookup"><span data-stu-id="01980-112">Article</span></span>|<span data-ttu-id="01980-113">Opis</span><span class="sxs-lookup"><span data-stu-id="01980-113">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="01980-114">Zapytania podstawowe</span><span class="sxs-lookup"><span data-stu-id="01980-114">Basic queries</span></span>](find-element-specific-attribute.md)|<span data-ttu-id="01980-115">Zawiera typowe przykłady tworzenia zapytań dotyczących drzew XML.</span><span class="sxs-lookup"><span data-stu-id="01980-115">Provides common examples of querying XML trees.</span></span>|
|[<span data-ttu-id="01980-116">Projekcje i przekształcenia</span><span class="sxs-lookup"><span data-stu-id="01980-116">Projections and transformations</span></span>](work-dictionaries-linq-xml.md)|<span data-ttu-id="01980-117">Zawiera typowe przykłady projekcji i transformacji drzew XML.</span><span class="sxs-lookup"><span data-stu-id="01980-117">Provides common examples of projecting from and transforming XML trees.</span></span>|
|[<span data-ttu-id="01980-118">Zaawansowane techniki zapytań</span><span class="sxs-lookup"><span data-stu-id="01980-118">Advanced query techniques</span></span>](join-two-collections.md)|<span data-ttu-id="01980-119">Zapewnia techniki zapytań, które są przydatne w bardziej zaawansowanych scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="01980-119">Provides query techniques that are useful in more advanced scenarios.</span></span>|
|[<span data-ttu-id="01980-120">LINQ to XML dla użytkowników XPath</span><span class="sxs-lookup"><span data-stu-id="01980-120">LINQ to XML for XPath users</span></span>](comparison-xpath-linq-xml.md)|<span data-ttu-id="01980-121">Przedstawia liczbę wyrażeń XPath i ich LINQ to XML odpowiedniki.</span><span class="sxs-lookup"><span data-stu-id="01980-121">Presents a number of XPath expressions and their LINQ to XML equivalents.</span></span>|
|[<span data-ttu-id="01980-122">Wprowadzenie do czystych transformacji funkcjonalnych</span><span class="sxs-lookup"><span data-stu-id="01980-122">Introduction to pure functional transformations</span></span>](introduction-pure-functional-transformations.md)|<span data-ttu-id="01980-123">Prezentuje niewielki samouczek dotyczący pisania zapytań w stylu programowania funkcjonalnego.</span><span class="sxs-lookup"><span data-stu-id="01980-123">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|

## <a name="see-also"></a><span data-ttu-id="01980-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="01980-124">See also</span></span>

- [<span data-ttu-id="01980-125">Language-Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="01980-125">Language-Integrated Query (LINQ) (C#)</span></span>](../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="01980-126">Wprowadzenie do kwerend LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="01980-126">Introduction to LINQ Queries (C#)</span></span>](../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [<span data-ttu-id="01980-127">LINQ w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="01980-127">LINQ in Visual Basic</span></span>](../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="01980-128">Zapytanie zintegrowane z językiem (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01980-128">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="01980-129">Wprowadzenie do programu LINQ w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="01980-129">Getting Started with LINQ in Visual Basic</span></span>](../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="01980-130">Pisanie pierwszego zapytania LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01980-130">Writing Your First LINQ Query (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)
