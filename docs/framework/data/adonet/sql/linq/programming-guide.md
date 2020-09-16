---
title: Przewodnik programowania
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: 0746d14d7be0b67bc9966ae0c5a4af0a3226c1e9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546565"
---
# <a name="programming-guide"></a><span data-ttu-id="2e9e2-102">Przewodnik programowania</span><span class="sxs-lookup"><span data-stu-id="2e9e2-102">Programming Guide</span></span>
<span data-ttu-id="2e9e2-103">Ta sekcja zawiera informacje o sposobie tworzenia i używania [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modelu obiektów.</span><span class="sxs-lookup"><span data-stu-id="2e9e2-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="2e9e2-104">Jeśli używasz programu Visual Studio, możesz również użyć Object Relational Designer, aby wykonać wiele z tych samych zadań.</span><span class="sxs-lookup"><span data-stu-id="2e9e2-104">If you are using Visual Studio, you can also use the Object Relational Designer to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="2e9e2-105">Możesz również wyszukać Microsoft Docs pod kątem określonych problemów i można wziąć udział na [forum LINQ](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), gdzie można omówić bardziej złożone tematy szczegółowo z ekspertami.</span><span class="sxs-lookup"><span data-stu-id="2e9e2-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="2e9e2-106">Na koniec [LINQ to SQL: zapytanie zintegrowane z językiem .NET na potrzeby](/previous-versions/dotnet/articles/bb425822(v=msdn.10)) Detailed Data Paper — [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technologia, kompletna z Visual Basic i kodu C# przykłady.</span><span class="sxs-lookup"><span data-stu-id="2e9e2-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](/previous-versions/dotnet/articles/bb425822(v=msdn.10)) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2e9e2-107">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="2e9e2-107">In This Section</span></span>  
 [<span data-ttu-id="2e9e2-108">Tworzenie modelu obiektu</span><span class="sxs-lookup"><span data-stu-id="2e9e2-108">Creating the Object Model</span></span>](creating-the-object-model.md)  
 <span data-ttu-id="2e9e2-109">Opisuje sposób generowania modelu obiektów.</span><span class="sxs-lookup"><span data-stu-id="2e9e2-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="2e9e2-110">Komunikacja z bazą danych</span><span class="sxs-lookup"><span data-stu-id="2e9e2-110">Communicating with the Database</span></span>](communicating-with-the-database.md)  
 <span data-ttu-id="2e9e2-111">Opisuje, jak używać <xref:System.Data.Linq.DataContext> obiektu jako przewód do bazy danych.</span><span class="sxs-lookup"><span data-stu-id="2e9e2-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="2e9e2-112">wykonywanie zapytania w bazie danych</span><span class="sxs-lookup"><span data-stu-id="2e9e2-112">Querying the Database</span></span>](querying-the-database.md)  
 <span data-ttu-id="2e9e2-113">Opisuje sposób wykonywania zapytań w programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] i zawiera wiele przykładów.</span><span class="sxs-lookup"><span data-stu-id="2e9e2-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="2e9e2-114">Tworzenie i przesyłanie zmian danych</span><span class="sxs-lookup"><span data-stu-id="2e9e2-114">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)  
 <span data-ttu-id="2e9e2-115">Opisuje sposób zmiany danych w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="2e9e2-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="2e9e2-116">Obsługa debugowania</span><span class="sxs-lookup"><span data-stu-id="2e9e2-116">Debugging Support</span></span>](debugging-support.md)  
 <span data-ttu-id="2e9e2-117">Opisuje pomoc techniczną dla debugowania [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projektów.</span><span class="sxs-lookup"><span data-stu-id="2e9e2-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="2e9e2-118">Informacje uzupełniające</span><span class="sxs-lookup"><span data-stu-id="2e9e2-118">Background Information</span></span>](background-information.md)  
 <span data-ttu-id="2e9e2-119">Obejmuje dodatkowe elementy, takie jak rozwiązywanie konfliktów współbieżności, tworzenie nowych baz danych i inne, dla bardziej zaawansowanych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="2e9e2-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2e9e2-120">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="2e9e2-120">Related Sections</span></span>  
 [<span data-ttu-id="2e9e2-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2e9e2-121">LINQ to SQL</span></span>](index.md)  
 <span data-ttu-id="2e9e2-122">Zawiera łącza do tematów, które opisują [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technologię i demonstrację funkcji.</span><span class="sxs-lookup"><span data-stu-id="2e9e2-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="2e9e2-123">Procedury składowane</span><span class="sxs-lookup"><span data-stu-id="2e9e2-123">Stored Procedures</span></span>](stored-procedures.md)  
 <span data-ttu-id="2e9e2-124">Zawiera linki do tematów, które ilustrują sposób korzystania z procedur składowanych.</span><span class="sxs-lookup"><span data-stu-id="2e9e2-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="2e9e2-125">Wprowadzenie do LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="2e9e2-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="2e9e2-126">Zawiera zasoby ułatwiające rozpoczęcie uczenia się LINQ to SQL przy użyciu języka C#.</span><span class="sxs-lookup"><span data-stu-id="2e9e2-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="2e9e2-127">Wprowadzenie do LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e9e2-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="2e9e2-128">Zawiera zasoby ułatwiające rozpoczęcie uczenia się LINQ to SQL przy użyciu Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2e9e2-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
