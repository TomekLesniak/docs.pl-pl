---
title: Wprowadzenie do LINQ
ms.date: 07/20/2015
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
ms.openlocfilehash: e99da74eb69511b92ddccfb42f8002adc7be83d1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91098284"
---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="9c2b9-102">Wprowadzenie do LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c2b9-102">Introduction to LINQ (Visual Basic)</span></span>

<span data-ttu-id="9c2b9-103">Language-Integrated Query (LINQ) to innowacje wprowadzone w .NET Framework w wersji 3,5, która mostkuje przerwy między światem obiektów a światem danych.</span><span class="sxs-lookup"><span data-stu-id="9c2b9-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="9c2b9-104">Tradycyjnie zapytania dotyczące danych są wyrażane jako proste ciągi bez sprawdzania typu w czasie kompilacji lub obsłudze IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="9c2b9-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="9c2b9-105">Ponadto należy poznać inny język zapytań dla każdego typu źródła danych: bazy danych SQL, dokumenty XML, różne usługi sieci Web itd.</span><span class="sxs-lookup"><span data-stu-id="9c2b9-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="9c2b9-106">LINQ wykonuje *zapytanie* do konstrukcji języka pierwszej klasy w Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9c2b9-106">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="9c2b9-107">Zapytania są pisane względem jednoznacznie wpisanych kolekcji obiektów przy użyciu słów kluczowych języka i znanych operatorów.</span><span class="sxs-lookup"><span data-stu-id="9c2b9-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="9c2b9-108">Zapytania LINQ można pisać w Visual Basic dla SQL Server baz danych, dokumentów XML, ADO.NET danych i dowolnej kolekcji obiektów, które obsługują <xref:System.Collections.IEnumerable> lub <xref:System.Collections.Generic.IEnumerable%601> interfejs ogólny.</span><span class="sxs-lookup"><span data-stu-id="9c2b9-108">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="9c2b9-109">Wsparcie LINQ jest również udostępniane przez inne firmy dla wielu usług sieci Web i innych implementacji baz danych.</span><span class="sxs-lookup"><span data-stu-id="9c2b9-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="9c2b9-110">Można używać zapytań LINQ w nowych projektach lub obok zapytań innych niż LINQ w istniejących projektach.</span><span class="sxs-lookup"><span data-stu-id="9c2b9-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="9c2b9-111">Jedynym wymaganiem jest, że projekt docelowy .NET Framework 3,5 lub nowszy.</span><span class="sxs-lookup"><span data-stu-id="9c2b9-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="9c2b9-112">Poniższa ilustracja z programu Visual Studio pokazuje częściowo ukończone zapytanie LINQ względem bazy danych SQL Server w języku C# i Visual Basic za pomocą sprawdzania pełnego typu i obsługi technologii IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="9c2b9-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 ![Diagram przedstawiający zapytanie LINQ z technologią IntelliSense.](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a><span data-ttu-id="9c2b9-114">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="9c2b9-114">Next Steps</span></span>  

 <span data-ttu-id="9c2b9-115">Aby dowiedzieć się więcej na temat programu LINQ, Zacznij od zapoznania się z niektórymi podstawowymi koncepcjami w sekcji Wprowadzenie [wprowadzenie za pomocą LINQ w Visual Basic](getting-started-with-linq.md), a następnie zapoznaj się z dokumentacją technologii LINQ, w której Cię interesujesz:</span><span class="sxs-lookup"><span data-stu-id="9c2b9-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
- <span data-ttu-id="9c2b9-116">Bazy danych SQL Server: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="9c2b9-116">SQL Server databases: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span></span>  
  
- <span data-ttu-id="9c2b9-117">Dokumenty XML: [LINQ to XML (Visual Basic)](../../../../standard/linq/linq-xml-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9c2b9-117">XML documents: [LINQ to XML (Visual Basic)](../../../../standard/linq/linq-xml-overview.md)</span></span>  
  
- <span data-ttu-id="9c2b9-118">ADO.NET zbiory danych: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="9c2b9-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
- <span data-ttu-id="9c2b9-119">Kolekcje .NET, pliki, ciągi i tak dalej: [LINQ to Objects (Visual Basic)](linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="9c2b9-119">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c2b9-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9c2b9-120">See also</span></span>

- [<span data-ttu-id="9c2b9-121">Zapytanie zintegrowane z językiem (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c2b9-121">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](index.md)
