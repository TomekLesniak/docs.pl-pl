---
title: Funkcje (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: bef959ae6a835b5d1d696162528a8f904c59e8e5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201073"
---
# <a name="functions-entity-sql"></a><span data-ttu-id="18c7f-102">Funkcje (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="18c7f-102">Functions (Entity SQL)</span></span>

<span data-ttu-id="18c7f-103">Entity SQL obsługuje funkcje zdefiniowane przez użytkownika, funkcje kanoniczne i funkcje specyficzne dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="18c7f-103">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="18c7f-104">Funkcje zdefiniowane przez użytkownika są określone w modelu koncepcyjnym lub wbudowane w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="18c7f-104">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="18c7f-105">Aby uzyskać więcej informacji, zobacz [funkcje zdefiniowane przez użytkownika](user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="18c7f-105">For more information, see [User-Defined Functions](user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="18c7f-106">Funkcje kanoniczne są wstępnie zdefiniowane w Entity Framework i powinny być obsługiwane przez dostawców danych.</span><span class="sxs-lookup"><span data-stu-id="18c7f-106">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="18c7f-107">Entity SQL polecenia zakończą się niepowodzeniem, jeśli użytkownik wywoła funkcję, która nie jest obsługiwana przez dostawcę.</span><span class="sxs-lookup"><span data-stu-id="18c7f-107">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="18c7f-108">W związku z tym funkcje kanoniczne są zwykle zalecane w stosunku do funkcji specyficznych dla magazynu, które znajdują się w przestrzeni nazw specyficznej dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="18c7f-108">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="18c7f-109">Aby uzyskać więcej informacji, zobacz [funkcje kanoniczne](canonical-functions.md).</span><span class="sxs-lookup"><span data-stu-id="18c7f-109">For more information, see [Canonical Functions](canonical-functions.md).</span></span>  
  
 <span data-ttu-id="18c7f-110">Dostawca zarządzany przez klienta programu Microsoft SQL Server udostępnia zestaw funkcji specyficznych dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="18c7f-110">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="18c7f-111">Aby uzyskać więcej informacji, zobacz temat [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="18c7f-111">For more information, see [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18c7f-112">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="18c7f-112">In This Section</span></span>  

 [<span data-ttu-id="18c7f-113">Funkcje zdefiniowane przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="18c7f-113">User-Defined Functions</span></span>](user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="18c7f-114">Rozpoznanie przeciążenia funkcji</span><span class="sxs-lookup"><span data-stu-id="18c7f-114">Function Overload Resolution</span></span>](function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="18c7f-115">Funkcje agregujące</span><span class="sxs-lookup"><span data-stu-id="18c7f-115">Aggregate Functions</span></span>](../aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="18c7f-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="18c7f-116">See also</span></span>

- [<span data-ttu-id="18c7f-117">Omówienie jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="18c7f-117">Entity SQL Overview</span></span>](entity-sql-overview.md)
