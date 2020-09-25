---
title: System.DateTime, metody
ms.date: 03/30/2017
ms.assetid: 4f80700c-e83f-4ab6-af0f-1c9a606e1133
ms.openlocfilehash: e3bffb1f47c19ccf7ea59151cd3545a15d59f1f2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203491"
---
# <a name="systemdatetime-methods"></a><span data-ttu-id="edfca-102">System.DateTime, metody</span><span class="sxs-lookup"><span data-stu-id="edfca-102">System.DateTime Methods</span></span>

<span data-ttu-id="edfca-103">Poniższe LINQ to SQL-obsługiwane metody, operatory i właściwości są dostępne do użycia w LINQ to SQL zapytaniach.</span><span class="sxs-lookup"><span data-stu-id="edfca-103">The following LINQ to SQL-supported methods, operators, and properties are available to use in LINQ to SQL queries.</span></span> <span data-ttu-id="edfca-104">Gdy metoda, operator lub właściwość nie jest obsługiwana, LINQ to SQL nie może przetłumaczyć elementu członkowskiego na wykonanie na SQL Server.</span><span class="sxs-lookup"><span data-stu-id="edfca-104">When a method, operator or property is unsupported, LINQ to SQL cannot translate the member for execution on the SQL Server.</span></span> <span data-ttu-id="edfca-105">Możesz użyć tych członków w kodzie, ale muszą one być oceniane przed przetłumaczeniem zapytania na Transact-SQL lub po pobraniu wyników z bazy danych.</span><span class="sxs-lookup"><span data-stu-id="edfca-105">You may use these members in your code, however, they must be evaluated before the query is translated to Transact-SQL or after the results have been retrieved from the database.</span></span>  
  
## <a name="supported-systemdatetime-members"></a><span data-ttu-id="edfca-106">Obsługiwane elementy członkowskie system. DateTime</span><span class="sxs-lookup"><span data-stu-id="edfca-106">Supported System.DateTime Members</span></span>  

 <span data-ttu-id="edfca-107">Po zmapowaniu w modelu obiektów lub zewnętrznym pliku mapowania LINQ to SQL umożliwia wywoływanie następujących <xref:System.DateTime?displayProperty=nameWithType> elementów członkowskich wewnątrz zapytań LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="edfca-107">Once mapped in the object model or external mapping file, LINQ to SQL allows you to call the following <xref:System.DateTime?displayProperty=nameWithType> members inside LINQ to SQL queries.</span></span>  
  
|<span data-ttu-id="edfca-108">Obsługiwane <xref:System.DateTime> metody</span><span class="sxs-lookup"><span data-stu-id="edfca-108">Supported <xref:System.DateTime> Methods</span></span>|<span data-ttu-id="edfca-109">Obsługiwane <xref:System.DateTime> Operatory</span><span class="sxs-lookup"><span data-stu-id="edfca-109">Supported <xref:System.DateTime> Operators</span></span>|<span data-ttu-id="edfca-110">Obsługiwane <xref:System.DateTime> właściwości</span><span class="sxs-lookup"><span data-stu-id="edfca-110">Supported <xref:System.DateTime> Properties</span></span>|  
|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.DateTime.Add%2A>|<xref:System.DateTime.op_Addition%2A>|<xref:System.DateTime.Date%2A>|  
|<xref:System.DateTime.AddDays%2A>|<xref:System.DateTime.op_Equality%2A>|<xref:System.DateTime.Day%2A>|  
|<xref:System.DateTime.AddHours%2A>|<xref:System.DateTime.op_GreaterThan%2A>|<xref:System.DateTime.DayOfWeek%2A>|  
|<xref:System.DateTime.AddMilliseconds%2A>|<xref:System.DateTime.op_GreaterThanOrEqual%2A>|<xref:System.DateTime.DayOfYear%2A>|  
|<xref:System.DateTime.AddMinutes%2A>|<xref:System.DateTime.op_Inequality%2A>|<xref:System.DateTime.Hour%2A>|  
|<xref:System.DateTime.AddMonths%2A>|<xref:System.DateTime.op_LessThan%2A>|<xref:System.DateTime.Millisecond%2A>|  
|<xref:System.DateTime.AddSeconds%2A>|<xref:System.DateTime.op_LessThanOrEqual%2A>|<xref:System.DateTime.Minute%2A>|  
|<xref:System.DateTime.AddTicks%2A>|<xref:System.DateTime.op_Subtraction%2A>|<xref:System.DateTime.Month%2A>|  
|<xref:System.DateTime.AddYears%2A>||<xref:System.DateTime.Now%2A>|  
|<xref:System.DateTime.Compare%2A>||<xref:System.DateTime.Second%2A>|  
|<xref:System.DateTime.CompareTo%28System.DateTime%29>||<xref:System.DateTime.TimeOfDay%2A>|  
|<xref:System.DateTime.Equals%28System.DateTime%29>||<xref:System.DateTime.Today%2A>|  
|||<xref:System.DateTime.Year%2A>|  
  
## <a name="members-not-supported-by-linq-to-sql"></a><span data-ttu-id="edfca-111">Elementy członkowskie nieobsługiwane przez LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="edfca-111">Members Not Supported by LINQ to SQL</span></span>  

 <span data-ttu-id="edfca-112">Następujące elementy członkowskie nie są obsługiwane wewnątrz zapytań LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="edfca-112">The following members are not supported inside LINQ to SQL queries.</span></span>  
  
|||  
|-|-|  
|<xref:System.DateTime.IsDaylightSavingTime%2A>|<xref:System.DateTime.IsLeapYear%2A>|  
|<xref:System.DateTime.DaysInMonth%2A>|<xref:System.DateTime.ToBinary%2A>|  
|<xref:System.DateTime.ToFileTime%2A>|<xref:System.DateTime.ToFileTimeUtc%2A>|  
|<xref:System.DateTime.ToLongDateString%2A>|<xref:System.DateTime.ToLongTimeString%2A>|  
|<xref:System.DateTime.ToOADate%2A>|<xref:System.DateTime.ToShortDateString%2A>|  
|<xref:System.DateTime.ToShortTimeString%2A>|<xref:System.DateTime.ToUniversalTime%2A>|  
|<xref:System.DateTime.FromBinary%2A>|<xref:System.DateTime.UtcNow%2A>|  
|<xref:System.DateTime.FromFileTime%2A>|<xref:System.DateTime.FromFileTimeUtc%2A>|  
|<xref:System.DateTime.FromOADate%2A>|<xref:System.DateTime.GetDateTimeFormats%2A>|  
  
## <a name="method-translation-example"></a><span data-ttu-id="edfca-113">Przykład tłumaczenia metody</span><span class="sxs-lookup"><span data-stu-id="edfca-113">Method Translation Example</span></span>  

 <span data-ttu-id="edfca-114">Wszystkie metody obsługiwane przez LINQ to SQL są tłumaczone na Transact-SQL przed wysłaniem do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="edfca-114">All methods supported by LINQ to SQL are translated to Transact-SQL before they are sent to   SQL Server.</span></span> <span data-ttu-id="edfca-115">Rozważmy na przykład następujący wzorzec.</span><span class="sxs-lookup"><span data-stu-id="edfca-115">For example, consider the following pattern.</span></span>  
  
 `(dateTime1 – dateTime2).{Days, Hours, Milliseconds, Minutes, Months, Seconds, Years}`  
  
 <span data-ttu-id="edfca-116">Po rozpoznaniu są one tłumaczone na bezpośrednie wywołanie funkcji SQL Server w `DATEDIFF` następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="edfca-116">When it is recognized, it is translated into a direct call to the SQL Server `DATEDIFF` function, as follows:</span></span>  
  
 `DATEDIFF({DatePart}, @dateTime1, @dateTime2)`  
  
## <a name="sqlmethods-date-and-time-methods"></a><span data-ttu-id="edfca-117">Metody SqlMethods i Time</span><span class="sxs-lookup"><span data-stu-id="edfca-117">SQLMethods Date and Time Methods</span></span>  

 <span data-ttu-id="edfca-118">Oprócz metod oferowanych przez <xref:System.DateTime> strukturę LINQ to SQL oferują metody wymienione w poniższej tabeli z <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> klasy do pracy z datą i godziną.</span><span class="sxs-lookup"><span data-stu-id="edfca-118">In addition to the methods offered by the <xref:System.DateTime> structure, LINQ to SQL offers the methods listed in the following table from the <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> class for working with date and time.</span></span>  
  
||||  
|-|-|-|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffDay%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMillisecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffNanosecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffHour%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMinute%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffSecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMicrosecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMonth%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffYear%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="edfca-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="edfca-119">See also</span></span>

- [<span data-ttu-id="edfca-120">Pojęcia dotyczące zapytań</span><span class="sxs-lookup"><span data-stu-id="edfca-120">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="edfca-121">Tworzenie modelu obiektu</span><span class="sxs-lookup"><span data-stu-id="edfca-121">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="edfca-122">Mapowania typów środowiska SQL-CLR</span><span class="sxs-lookup"><span data-stu-id="edfca-122">SQL-CLR Type Mapping</span></span>](sql-clr-type-mapping.md)
- [<span data-ttu-id="edfca-123">Typy danych i funkcje</span><span class="sxs-lookup"><span data-stu-id="edfca-123">Data Types and Functions</span></span>](data-types-and-functions.md)
