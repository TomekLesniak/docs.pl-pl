---
title: System.TimeSpan, metody
ms.date: 03/30/2017
ms.assetid: 9333fee8-1454-4374-855b-8c14c002f48f
ms.openlocfilehash: 15b6c8bd5c9cce8e6d1bac030c6b7f6b40df6cd4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155591"
---
# <a name="systemtimespan-methods"></a><span data-ttu-id="c68d0-102">System.TimeSpan, metody</span><span class="sxs-lookup"><span data-stu-id="c68d0-102">System.TimeSpan Methods</span></span>

<span data-ttu-id="c68d0-103">Obsługa elementów członkowskich <xref:System.TimeSpan?displayProperty=nameWithType> znacznie zależy od wersji .NET Framework i Microsoft SQL Server, z których korzystasz.</span><span class="sxs-lookup"><span data-stu-id="c68d0-103">Member support for <xref:System.TimeSpan?displayProperty=nameWithType> greatly depends on the versions of the .NET Framework and Microsoft SQL Server that you are using.</span></span>  
  
 <span data-ttu-id="c68d0-104">Gdy metoda, operator lub właściwość jest nieobsługiwana; oznacza to, że LINQ to SQL nie może przetłumaczyć elementu członkowskiego na wykonanie na SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c68d0-104">When a method, operator, or property is unsupported; it means that LINQ to SQL cannot translate the member for execution on the SQL Server.</span></span> <span data-ttu-id="c68d0-105">Nadal możesz korzystać z tych elementów członkowskich w kodzie.</span><span class="sxs-lookup"><span data-stu-id="c68d0-105">You may still be able to use these members in your code.</span></span> <span data-ttu-id="c68d0-106">Jednak muszą być oceniane przed przekazaniem zapytania do języka Transact-SQL lub po pobraniu wyników z bazy danych.</span><span class="sxs-lookup"><span data-stu-id="c68d0-106">However, they must be evaluated before the query is translated to Transact-SQL or after the results have been retrieved from the database.</span></span>  
  
## <a name="previous-limitations"></a><span data-ttu-id="c68d0-107">Poprzednie ograniczenia</span><span class="sxs-lookup"><span data-stu-id="c68d0-107">Previous Limitations</span></span>  

 <span data-ttu-id="c68d0-108">W przypadku korzystania z LINQ to SQL z wersjami .NET Framework przed .NET Framework 3,5 SP1 nie można mapować SQL Server pól bazy danych na <xref:System.TimeSpan?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="c68d0-108">When using LINQ to SQL with versions of the .NET Framework prior to .NET Framework 3.5 SP1, you cannot map SQL Server database fields to <xref:System.TimeSpan?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c68d0-109">Jednak operacje na <xref:System.TimeSpan> są obsługiwane, ponieważ <xref:System.TimeSpan> wartości mogą być zwracane z <xref:System.DateTime> odejmowania lub wprowadzane do wyrażenia jako literału lub zmiennej powiązanej.</span><span class="sxs-lookup"><span data-stu-id="c68d0-109">However, operations on <xref:System.TimeSpan> are supported because <xref:System.TimeSpan> values can be returned from <xref:System.DateTime> subtraction or introduced into an expression as a literal or bound variable.</span></span>  
  
## <a name="supported-systemtimespan-member-support"></a><span data-ttu-id="c68d0-110">Obsługiwane wsparcie składowej system. TimeSpan</span><span class="sxs-lookup"><span data-stu-id="c68d0-110">Supported System.TimeSpan member support</span></span>

 <span data-ttu-id="c68d0-111">Poniższe LINQ to SQL-obsługiwane metody, operatory i właściwości są dostępne do użycia w zapytaniach LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="c68d0-111">The following LINQ to SQL-supported methods, operators, and properties are available for you to use in your LINQ to SQL queries.</span></span> <span data-ttu-id="c68d0-112">Po zmapowaniu w modelu obiektów lub zewnętrznym pliku mapowania LINQ to SQL umożliwia wywoływanie wielu <xref:System.TimeSpan?displayProperty=nameWithType> elementów członkowskich wewnątrz zapytań LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="c68d0-112">Once mapped in the object model or external mapping file, LINQ to SQL allows you to call many of the <xref:System.TimeSpan?displayProperty=nameWithType> members inside your LINQ to SQL queries.</span></span>  
  
|<span data-ttu-id="c68d0-113">Obsługiwane <xref:System.TimeSpan> metody</span><span class="sxs-lookup"><span data-stu-id="c68d0-113">Supported <xref:System.TimeSpan> Methods</span></span>|<span data-ttu-id="c68d0-114">Obsługiwane <xref:System.TimeSpan> Operatory</span><span class="sxs-lookup"><span data-stu-id="c68d0-114">Supported <xref:System.TimeSpan> Operators</span></span>|<span data-ttu-id="c68d0-115">Obsługiwane <xref:System.TimeSpan> właściwości</span><span class="sxs-lookup"><span data-stu-id="c68d0-115">Supported <xref:System.TimeSpan> Properties</span></span>|  
|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.TimeSpan.Compare%2A>|<xref:System.TimeSpan.op_Equality%2A>|<xref:System.TimeSpan.Days%2A>|  
|<xref:System.TimeSpan.CompareTo%28System.TimeSpan%29>|<xref:System.TimeSpan.op_GreaterThan%2A>|<xref:System.TimeSpan.Hours%2A>|  
|<xref:System.TimeSpan.Duration%2A>|<xref:System.TimeSpan.op_GreaterThanOrEqual%2A>|<xref:System.TimeSpan.MaxValue>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%2CSystem.TimeSpan%29>|<xref:System.TimeSpan.op_Inequality%2A>|<xref:System.TimeSpan.Milliseconds%2A>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%29>|<xref:System.TimeSpan.op_LessThan%2A>|<xref:System.TimeSpan.Minutes%2A>|  
||<xref:System.TimeSpan.op_LessThanOrEqual%2A>|<xref:System.TimeSpan.MinValue>|  
  
> [!NOTE]
> <span data-ttu-id="c68d0-116">Możliwość mapowania <xref:System.TimeSpan?displayProperty=nameWithType> do `TIME` kolumny SQL z LINQ to SQL wymaga .NET Framework 3,5 z dodatkiem SP1 i poza nią.</span><span class="sxs-lookup"><span data-stu-id="c68d0-116">The ability to map <xref:System.TimeSpan?displayProperty=nameWithType> to a SQL `TIME` column with LINQ to SQL requires the .NET Framework 3.5 SP1 and beyond.</span></span> <span data-ttu-id="c68d0-117">`TIME`Typ danych SQL jest dostępny tylko w Microsoft SQL Server 2008 i więcej.</span><span class="sxs-lookup"><span data-stu-id="c68d0-117">The SQL `TIME` data type is only available in Microsoft SQL Server 2008 and beyond.</span></span>  
  
### <a name="addition-and-subtraction"></a><span data-ttu-id="c68d0-118">Dodawanie i odejmowanie</span><span class="sxs-lookup"><span data-stu-id="c68d0-118">Addition and Subtraction</span></span>  

 <span data-ttu-id="c68d0-119">Chociaż typ CLR obsługuje <xref:System.TimeSpan?displayProperty=nameWithType> Dodawanie i odejmowanie, typ SQL nie `TIME` jest.</span><span class="sxs-lookup"><span data-stu-id="c68d0-119">Although the CLR <xref:System.TimeSpan?displayProperty=nameWithType> type does support addition and subtraction, the SQL `TIME` type does not.</span></span> <span data-ttu-id="c68d0-120">W związku z tym zapytania LINQ to SQL generują błędy, jeśli spróbują Dodawanie i odejmowanie, gdy są one mapowane na typ SQL `TIME` .</span><span class="sxs-lookup"><span data-stu-id="c68d0-120">Because of this, your LINQ to SQL queries will generate errors if they attempt addition and subtraction when they are mapped to the SQL `TIME` type.</span></span> <span data-ttu-id="c68d0-121">Inne zagadnienia dotyczące pracy z typami dat i godzin SQL można znaleźć w [mapowaniu typu SQL-CLR](sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="c68d0-121">You can find other considerations for working with SQL date and time types in [SQL-CLR Type Mapping](sql-clr-type-mapping.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c68d0-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c68d0-122">See also</span></span>

- [<span data-ttu-id="c68d0-123">Pojęcia dotyczące zapytań</span><span class="sxs-lookup"><span data-stu-id="c68d0-123">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="c68d0-124">Tworzenie modelu obiektu</span><span class="sxs-lookup"><span data-stu-id="c68d0-124">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="c68d0-125">Mapowania typów środowiska SQL-CLR</span><span class="sxs-lookup"><span data-stu-id="c68d0-125">SQL-CLR Type Mapping</span></span>](sql-clr-type-mapping.md)
- [<span data-ttu-id="c68d0-126">Typy danych i funkcje</span><span class="sxs-lookup"><span data-stu-id="c68d0-126">Data Types and Functions</span></span>](data-types-and-functions.md)
