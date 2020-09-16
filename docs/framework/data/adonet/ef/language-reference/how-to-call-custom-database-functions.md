---
title: 'Instrukcje: Wywoływanie niestandardowych funkcji bazy danych'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: 9879803c970b7965bf152c216367b216e201af38
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540311"
---
# <a name="how-to-call-custom-database-functions"></a><span data-ttu-id="89670-102">Instrukcje: Wywoływanie niestandardowych funkcji bazy danych</span><span class="sxs-lookup"><span data-stu-id="89670-102">How to: Call Custom Database Functions</span></span>

<span data-ttu-id="89670-103">W tym temacie opisano sposób wywoływania funkcji niestandardowych, które są zdefiniowane w bazie danych z zapytań LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="89670-103">This topic describes how to call custom functions that are defined in the database from within LINQ to Entities queries.</span></span>

<span data-ttu-id="89670-104">Funkcje bazy danych, które są wywoływane z zapytań LINQ to Entities są wykonywane w bazie danych programu.</span><span class="sxs-lookup"><span data-stu-id="89670-104">Database functions that are called from LINQ to Entities queries are executed in the database.</span></span> <span data-ttu-id="89670-105">Wykonywanie funkcji w bazie danych może zwiększyć wydajność aplikacji.</span><span class="sxs-lookup"><span data-stu-id="89670-105">Executing functions in the database can improve application performance.</span></span>

<span data-ttu-id="89670-106">Poniższa procedura zawiera konspekt wysokiego poziomu służący do wywoływania niestandardowej funkcji bazy danych.</span><span class="sxs-lookup"><span data-stu-id="89670-106">The procedure below provides a high-level outline for calling a custom database function.</span></span> <span data-ttu-id="89670-107">Poniższy przykład zawiera bardziej szczegółowe informacje na temat kroków w procedurze.</span><span class="sxs-lookup"><span data-stu-id="89670-107">The example that follows provides more detail about the steps in the procedure.</span></span>

## <a name="to-call-custom-functions-that-are-defined-in-the-database"></a><span data-ttu-id="89670-108">Aby wywołać funkcje niestandardowe zdefiniowane w bazie danych</span><span class="sxs-lookup"><span data-stu-id="89670-108">To call custom functions that are defined in the database</span></span>

1. <span data-ttu-id="89670-109">Utwórz funkcję niestandardową w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="89670-109">Create a custom function in your database.</span></span>

     <span data-ttu-id="89670-110">Aby uzyskać więcej informacji na temat tworzenia funkcji niestandardowych w SQL Server, zobacz [CREATE FUNCTION (Transact-SQL)](/sql/t-sql/statements/create-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="89670-110">For more information about creating custom functions in SQL Server, see [CREATE FUNCTION (Transact-SQL)](/sql/t-sql/statements/create-function-transact-sql).</span></span>

2. <span data-ttu-id="89670-111">Zadeklaruj funkcję w języku definicji schematu magazynu (SSDL) pliku. edmx.</span><span class="sxs-lookup"><span data-stu-id="89670-111">Declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="89670-112">Nazwa funkcji musi być taka sama jak nazwa funkcji zadeklarowanej w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="89670-112">The name of the function must be the same as the name of the function declared in the database.</span></span>

     <span data-ttu-id="89670-113">Aby uzyskać więcej informacji, zobacz [Funkcja element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).</span><span class="sxs-lookup"><span data-stu-id="89670-113">For more information, see [Function Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).</span></span>

3. <span data-ttu-id="89670-114">Dodaj odpowiadającą metodę do klasy w kodzie aplikacji i Zastosuj <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> do metody należy zauważyć, że <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> Parametry i atrybutu są nazwą przestrzeni nazw modelu koncepcyjnego i nazwą funkcji w modelu koncepcyjnym odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="89670-114">Add a corresponding method to a class in your application code and apply a <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="89670-115">Rozpoznawanie nazw funkcji dla LINQ jest rozróżniana wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="89670-115">Function name resolution for LINQ is case sensitive.</span></span>

4. <span data-ttu-id="89670-116">Wywołaj metodę w kwerendzie LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="89670-116">Call the method in a LINQ to Entities query.</span></span>  

## <a name="example"></a><span data-ttu-id="89670-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="89670-117">Example</span></span>

<span data-ttu-id="89670-118">W poniższym przykładzie pokazano, jak wywołać funkcję niestandardowej bazy danych z poziomu zapytania LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="89670-118">The following example demonstrates how to call a custom database function from within a LINQ to Entities query.</span></span> <span data-ttu-id="89670-119">W przykładzie zastosowano model szkoły.</span><span class="sxs-lookup"><span data-stu-id="89670-119">The example uses the School model.</span></span> <span data-ttu-id="89670-120">Aby uzyskać informacje o modelu szkoły, zobacz [Tworzenie przykładowej bazy danych szkoły](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) i [generowanie pliku szkoły. edmx](/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="89670-120">For information about the School model, see [Creating the School Sample Database](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) and [Generating the School .edmx File](/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span></span>

<span data-ttu-id="89670-121">Poniższy kod dodaje `AvgStudentGrade` funkcję do przykładowej bazy danych szkoły.</span><span class="sxs-lookup"><span data-stu-id="89670-121">The following code adds the `AvgStudentGrade` function to the School sample database.</span></span>

> [!NOTE]
> <span data-ttu-id="89670-122">Kroki wywołania niestandardowej bazy danych są takie same, niezależnie od serwera bazy danych.</span><span class="sxs-lookup"><span data-stu-id="89670-122">The steps for calling a custom database function are the same regardless of the database server.</span></span> <span data-ttu-id="89670-123">Jednak poniższy kod jest specyficzny dla tworzenia funkcji w bazie danych SQL Server.</span><span class="sxs-lookup"><span data-stu-id="89670-123">However, the code below is specific to creating a function in a SQL Server database.</span></span> <span data-ttu-id="89670-124">Kod służący do tworzenia funkcji niestandardowej na innych serwerach bazy danych może się różnić.</span><span class="sxs-lookup"><span data-stu-id="89670-124">The code for creating a custom function in other database servers might differ.</span></span>

[!code-sql[DP L2E MapToDBFunction#1](~/samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]

## <a name="example"></a><span data-ttu-id="89670-125">Przykład</span><span class="sxs-lookup"><span data-stu-id="89670-125">Example</span></span>

<span data-ttu-id="89670-126">Następnie zadeklaruj funkcję w języku definicji schematu magazynu (SSDL) pliku *. edmx* .</span><span class="sxs-lookup"><span data-stu-id="89670-126">Next, declare a function in the store schema definition language (SSDL) of your *.edmx* file.</span></span> <span data-ttu-id="89670-127">Poniższy kod deklaruje `AvgStudentGrade` funkcję w SSDL:</span><span class="sxs-lookup"><span data-stu-id="89670-127">The following code declares the `AvgStudentGrade` function in SSDL:</span></span>

[!code-xml[DP L2E MapToDBFunction#2](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]

## <a name="example"></a><span data-ttu-id="89670-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="89670-128">Example</span></span>

<span data-ttu-id="89670-129">Teraz Utwórz metodę i zamapuj ją na funkcję zadeklarowaną w SSDL.</span><span class="sxs-lookup"><span data-stu-id="89670-129">Now, create a method and map it to the function declared in the SSDL.</span></span> <span data-ttu-id="89670-130">Metoda w poniższej klasie jest zamapowana na funkcję zdefiniowaną w SSDL (powyżej) przy użyciu <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> .</span><span class="sxs-lookup"><span data-stu-id="89670-130">The method in the following class is mapped to the function defined in the SSDL (above) by using an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="89670-131">Gdy ta metoda jest wywoływana, odpowiednia funkcja w bazie danych jest wykonywana.</span><span class="sxs-lookup"><span data-stu-id="89670-131">When this method is called, the corresponding function in the database is executed.</span></span>

[!code-csharp[DP L2E MapToDBFunction#3](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
[!code-vb[DP L2E MapToDBFunction#3](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]

## <a name="example"></a><span data-ttu-id="89670-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="89670-132">Example</span></span>

<span data-ttu-id="89670-133">Na koniec Wywołaj metodę w kwerendzie LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="89670-133">Finally, call the method in a LINQ to Entities query.</span></span> <span data-ttu-id="89670-134">Poniższy kod wyświetla nazwisko uczniów i średnią ocenę w konsoli:</span><span class="sxs-lookup"><span data-stu-id="89670-134">The following code displays students' last names and average grades to the console:</span></span>

[!code-csharp[DP L2E MapToDBFunction#4](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
[!code-vb[DP L2E MapToDBFunction#4](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="89670-135">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="89670-135">See also</span></span>

- <span data-ttu-id="89670-136">[Plik. edmx — Omówienie](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="89670-136">[.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="89670-137">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="89670-137">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
