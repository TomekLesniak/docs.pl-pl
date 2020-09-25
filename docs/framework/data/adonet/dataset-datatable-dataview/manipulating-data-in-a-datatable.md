---
title: Operowanie na danych w elemencie DataTable
ms.date: 03/30/2017
ms.assetid: 5cb86d48-a987-4af4-80e0-8cc2c8373d62
ms.openlocfilehash: 3f98832b4aa9361346d06830f2f004fa374222ee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201333"
---
# <a name="manipulating-data-in-a-datatable"></a><span data-ttu-id="d38cd-102">Operowanie na danych w elemencie DataTable</span><span class="sxs-lookup"><span data-stu-id="d38cd-102">Manipulating Data in a DataTable</span></span>

<span data-ttu-id="d38cd-103">Po utworzeniu elementu <xref:System.Data.DataTable> w programie <xref:System.Data.DataSet> można wykonać te same działania, które będą używane w przypadku korzystania z tabeli w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="d38cd-103">After creating a <xref:System.Data.DataTable> in a <xref:System.Data.DataSet>, you can perform the same activities that you would when using a table in a database.</span></span> <span data-ttu-id="d38cd-104">Można dodawać, wyświetlać, edytować i usuwać dane w tabeli; można monitorować błędy i zdarzenia; i można wykonywać zapytania dotyczące danych w tabeli.</span><span class="sxs-lookup"><span data-stu-id="d38cd-104">You can add, view, edit, and delete data in the table; you can monitor errors and events; and you can query the data in the table.</span></span> <span data-ttu-id="d38cd-105">Podczas modyfikowania danych w **elemencie DataTable**można także sprawdzić, czy zmiany są dokładne, oraz określić, czy zmiany mają być programowo akceptowane czy odrzucane.</span><span class="sxs-lookup"><span data-stu-id="d38cd-105">When modifying data in a **DataTable**, you can also verify whether the changes are accurate, and determine whether to programmatically accept or reject the changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d38cd-106">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="d38cd-106">In This Section</span></span>  

 [<span data-ttu-id="d38cd-107">Dodawanie danych do elementu DataTable</span><span class="sxs-lookup"><span data-stu-id="d38cd-107">Adding Data to a DataTable</span></span>](adding-data-to-a-datatable.md)  
 <span data-ttu-id="d38cd-108">Wyjaśnia, jak utworzyć nowe wiersze i dodać je do tabeli.</span><span class="sxs-lookup"><span data-stu-id="d38cd-108">Explains how to create new rows and add them to a table.</span></span>  
  
 [<span data-ttu-id="d38cd-109">Wyświetlanie danych w elemencie DataTable</span><span class="sxs-lookup"><span data-stu-id="d38cd-109">Viewing Data in a DataTable</span></span>](viewing-data-in-a-datatable.md)  
 <span data-ttu-id="d38cd-110">Opisuje, jak uzyskać dostęp do danych w wierszu, łącznie z oryginalnymi i bieżącymi wersjami danych.</span><span class="sxs-lookup"><span data-stu-id="d38cd-110">Describes how to access the data in a row, including original and current versions of the data.</span></span>  
  
 [<span data-ttu-id="d38cd-111">Metoda Load</span><span class="sxs-lookup"><span data-stu-id="d38cd-111">The Load Method</span></span>](the-load-method.md)  
 <span data-ttu-id="d38cd-112">Opisuje użycie metody **Load** do wypełniania tabeli **DataTable** z wierszami.</span><span class="sxs-lookup"><span data-stu-id="d38cd-112">Describes the use of the **Load** method to fill a **DataTable** with rows.</span></span>  
  
 [<span data-ttu-id="d38cd-113">Edycje elementu DataTable</span><span class="sxs-lookup"><span data-stu-id="d38cd-113">DataTable Edits</span></span>](datatable-edits.md)  
 <span data-ttu-id="d38cd-114">Wyjaśnia, jak modyfikować dane w wierszu, włącznie z zawieszeniem zmian w wierszu do momentu, gdy proponowane zmiany zostaną zweryfikowane i zaakceptowane.</span><span class="sxs-lookup"><span data-stu-id="d38cd-114">Explains how to modify the data in a row, including suspending the changes to a row until the proposed changes are verified and accepted.</span></span>  
  
 [<span data-ttu-id="d38cd-115">Stany wiersza i wersje wiersza</span><span class="sxs-lookup"><span data-stu-id="d38cd-115">Row States and Row Versions</span></span>](row-states-and-row-versions.md)  
 <span data-ttu-id="d38cd-116">Zawiera informacje o różnych stanach wiersza.</span><span class="sxs-lookup"><span data-stu-id="d38cd-116">Provides information about the different states of a row.</span></span>  
  
 [<span data-ttu-id="d38cd-117">Usuwanie elementu DataRow</span><span class="sxs-lookup"><span data-stu-id="d38cd-117">DataRow Deletion</span></span>](datarow-deletion.md)  
 <span data-ttu-id="d38cd-118">Opisuje sposób usuwania wiersza z tabeli.</span><span class="sxs-lookup"><span data-stu-id="d38cd-118">Describes how to remove a row from a table.</span></span>  
  
 [<span data-ttu-id="d38cd-119">Informacje o błędzie wiersza</span><span class="sxs-lookup"><span data-stu-id="d38cd-119">Row Error Information</span></span>](row-error-information.md)  
 <span data-ttu-id="d38cd-120">Wyjaśnia, jak wstawiać informacje o błędach w poszczególnych wierszach, aby pomóc w rozwiązywaniu problemów z danymi w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d38cd-120">Explains how to insert error information per row, to help resolve problems with the data within an application.</span></span>  
  
 [<span data-ttu-id="d38cd-121">Metody AcceptChanges i RejectChanges</span><span class="sxs-lookup"><span data-stu-id="d38cd-121">AcceptChanges and RejectChanges</span></span>](acceptchanges-and-rejectchanges.md)  
 <span data-ttu-id="d38cd-122">Wyjaśnia, jak zaakceptować lub odrzucić zmiany wprowadzone w wierszu.</span><span class="sxs-lookup"><span data-stu-id="d38cd-122">Explains how to accept or reject the changes made to a row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d38cd-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d38cd-123">See also</span></span>

- [<span data-ttu-id="d38cd-124">Elementy DataTable</span><span class="sxs-lookup"><span data-stu-id="d38cd-124">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="d38cd-125">Obsługa zdarzeń elementu DataTable</span><span class="sxs-lookup"><span data-stu-id="d38cd-125">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="d38cd-126">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d38cd-126">ADO.NET Overview</span></span>](../ado-net-overview.md)
