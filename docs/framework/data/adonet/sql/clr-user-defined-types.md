---
title: Zdefiniowane przez użytkownika typy CLR
ms.date: 03/30/2017
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
ms.openlocfilehash: 84d588e0c415daa7de19ea695c817f3eb24f732f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173591"
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="ccfb2-102">Zdefiniowane przez użytkownika typy CLR</span><span class="sxs-lookup"><span data-stu-id="ccfb2-102">CLR User-Defined Types</span></span>

<span data-ttu-id="ccfb2-103">Microsoft SQL Server zapewnia obsługę typów zdefiniowanych przez użytkownika (UDTs) implementowanych przy użyciu środowiska uruchomieniowego języka wspólnego (CLR) Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ccfb2-103">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="ccfb2-104">Środowisko CLR jest zintegrowane z SQL Server, a mechanizm ten umożliwia rozbudowanie systemu typu bazy danych.</span><span class="sxs-lookup"><span data-stu-id="ccfb2-104">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="ccfb2-105">UDTs zapewniają rozszerzalność użytkowników systemu SQL Server typu danych, a także możliwość definiowania złożonych typów strukturalnych.</span><span class="sxs-lookup"><span data-stu-id="ccfb2-105">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="ccfb2-106">UDTs mogą zapewnić dwie kluczowe korzyści z perspektywy architektury aplikacji:</span><span class="sxs-lookup"><span data-stu-id="ccfb2-106">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
- <span data-ttu-id="ccfb2-107">Silne hermetyzacja (zarówno w kliencie, jak i na serwerze) między stanem wewnętrznym i zachowaniami zewnętrznymi.</span><span class="sxs-lookup"><span data-stu-id="ccfb2-107">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
- <span data-ttu-id="ccfb2-108">Ścisła integracja z innymi powiązanymi funkcjami serwera.</span><span class="sxs-lookup"><span data-stu-id="ccfb2-108">Deep integration with other related server features.</span></span> <span data-ttu-id="ccfb2-109">Po zdefiniowaniu własnego UDT można użyć go we wszystkich kontekstach, w których można używać typu systemu w SQL Server, w tym definicji kolumn, oraz jako zmienne, parametry, wyniki funkcji, kursory, wyzwalacze i replikacja.</span><span class="sxs-lookup"><span data-stu-id="ccfb2-109">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="ccfb2-110">Aby uzyskać szczegółowe informacje, zapoznaj się z [dokumentacją SQL Server](/sql) dla używanej wersji SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ccfb2-110">For more detailed information, see the [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="ccfb2-111">**Dokumentacja SQL Server**</span><span class="sxs-lookup"><span data-stu-id="ccfb2-111">**SQL Server documentation**</span></span>
  
1. [<span data-ttu-id="ccfb2-112">Zdefiniowane przez użytkownika typy CLR</span><span class="sxs-lookup"><span data-stu-id="ccfb2-112">CLR User-Defined Types</span></span>](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="see-also"></a><span data-ttu-id="ccfb2-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ccfb2-113">See also</span></span>

- [<span data-ttu-id="ccfb2-114">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ccfb2-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
