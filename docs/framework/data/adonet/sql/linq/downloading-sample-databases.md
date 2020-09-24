---
title: Pobierz przykładowe SQL Server bazy danych dla przykładów kodu ADO.NET
description: Pobierz przykładowe SQL Server bazy danych używane w przykładach kodu w dokumentacji programu ADO.NET, a także narzędzia do SQL Server i zarządzania
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: f7c0d1eb0089a6bfabc92e1deecf563c3e59cc6a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156059"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="a2e37-103">Pobierz przykładowe bazy danych dla przykładów kodu ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a2e37-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="a2e37-104">Kilka przykładów i instruktaży w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dokumentacji używają przykładowych baz danych SQL Server i SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="a2e37-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="a2e37-105">Te produkty można pobrać bezpłatnie od firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2e37-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="a2e37-106">Pobierz przykładową bazę danych Northwind dla SQL Server</span><span class="sxs-lookup"><span data-stu-id="a2e37-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="a2e37-107">Pobierz skrypt `instnwnd.sql` z następującego repozytorium GitHub, aby utworzyć i załadować przykładową bazę danych Northwind dla SQL Server:</span><span class="sxs-lookup"><span data-stu-id="a2e37-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="a2e37-108">Przykładowe bazy danych Northwind i pubs dla Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="a2e37-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="a2e37-109">Aby można było korzystać z bazy danych Northwind, należy uruchomić pobrany `instnwnd.sql` plik skryptu w celu odtworzenia bazy danych w wystąpieniu SQL Server przy użyciu [SQL Server Management Studio](#get_ssms) lub podobnego narzędzia.</span><span class="sxs-lookup"><span data-stu-id="a2e37-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="a2e37-110">Postępuj zgodnie z instrukcjami w pliku Readme w repozytorium.</span><span class="sxs-lookup"><span data-stu-id="a2e37-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="a2e37-111">Jeśli szukasz bazy danych Northwind dla programu Microsoft Access, zobacz [Instalowanie przykładowej bazy danych Northwind dla programu Microsoft Access](#northwind_access).</span><span class="sxs-lookup"><span data-stu-id="a2e37-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a> <span data-ttu-id="a2e37-112">Pobieranie przykładowej bazy danych Northwind dla programu Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="a2e37-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="a2e37-113">Przykładowa baza danych Northwind dla programu Microsoft Access nie jest dostępna w centrum pobierania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2e37-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="a2e37-114">Aby zainstalować Northwind bezpośrednio z poziomu programu Access, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="a2e37-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="a2e37-115">Otwórz program Access.</span><span class="sxs-lookup"><span data-stu-id="a2e37-115">Open Access.</span></span>

1. <span data-ttu-id="a2e37-116">Wprowadź ciąg **Northwind** w polu **Wyszukaj szablony online** , a następnie wybierz klawisz **Enter**.</span><span class="sxs-lookup"><span data-stu-id="a2e37-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="a2e37-117">Na ekranie Wyniki wybierz pozycję **Northwind**.</span><span class="sxs-lookup"><span data-stu-id="a2e37-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="a2e37-118">Zostanie otwarte nowe okno z opisem bazy danych Northwind.</span><span class="sxs-lookup"><span data-stu-id="a2e37-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="a2e37-119">W nowym oknie, w polu tekstowym **Nazwa pliku** Podaj nazwę pliku dla kopii bazy danych Northwind.</span><span class="sxs-lookup"><span data-stu-id="a2e37-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="a2e37-120">Wybierz przycisk **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="a2e37-120">Select **Create**.</span></span> <span data-ttu-id="a2e37-121">Program Access pobiera bazę danych Northwind i przygotowuje plik.</span><span class="sxs-lookup"><span data-stu-id="a2e37-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="a2e37-122">Po zakończeniu tego procesu zostanie otwarta baza danych z ekranem powitalnym.</span><span class="sxs-lookup"><span data-stu-id="a2e37-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="a2e37-123">Pobierz przykładową bazę danych AdventureWorks dla SQL Server</span><span class="sxs-lookup"><span data-stu-id="a2e37-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="a2e37-124">Pobierz przykładową bazę danych AdventureWorks dla SQL Server z następującego repozytorium GitHub:</span><span class="sxs-lookup"><span data-stu-id="a2e37-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="a2e37-125">Przykładowe bazy danych AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="a2e37-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="a2e37-126">Po pobraniu jednego z plików kopii zapasowej bazy danych ( \* . bak) Przywróć kopię zapasową do wystąpienia SQL Server przy użyciu SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="a2e37-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="a2e37-127">Zobacz [pobieranie SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="a2e37-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a> <span data-ttu-id="a2e37-128">Pobierz SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a2e37-128">Get SQL Server Management Studio</span></span>

<span data-ttu-id="a2e37-129">Jeśli chcesz wyświetlić lub zmodyfikować bazę danych, która została pobrana, możesz użyć SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="a2e37-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="a2e37-130">Pobierz narzędzie SSMS z następującej strony:</span><span class="sxs-lookup"><span data-stu-id="a2e37-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="a2e37-131">Pobieranie programu SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="a2e37-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms)

<span data-ttu-id="a2e37-132">Możesz również wyświetlać bazy danych i zarządzać nimi w zintegrowanym środowisku programistycznym (IDE) programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a2e37-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="a2e37-133">W programie [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)Połącz się z bazą danych z programu **Eksplorator obiektów SQL Server**lub Utwórz połączenie danych z bazą danych w programie **Eksplorator serwera**.</span><span class="sxs-lookup"><span data-stu-id="a2e37-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="a2e37-134">Otwórz te okienka Eksploratora z menu **Widok** .</span><span class="sxs-lookup"><span data-stu-id="a2e37-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get-sql-server-express"></a><a name="get_sql"></a> <span data-ttu-id="a2e37-135">Pobierz SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="a2e37-135">Get SQL Server Express</span></span>

<span data-ttu-id="a2e37-136">SQL Server Express to bezpłatna wersja SQL Server, którą można rozpowszechniać za pomocą aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a2e37-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="a2e37-137">Pobierz SQL Server Express z następującej strony:</span><span class="sxs-lookup"><span data-stu-id="a2e37-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="a2e37-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="a2e37-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="a2e37-139">Jeśli używasz [programu Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), SQL Server Express LocalDB jest zawarty w bezpłatnej wersji Community programu Visual Studio, a także w wersjach Professional i wyższych.</span><span class="sxs-lookup"><span data-stu-id="a2e37-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a2e37-140">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a2e37-140">See also</span></span>

- [<span data-ttu-id="a2e37-141">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="a2e37-141">Getting Started</span></span>](getting-started.md)
