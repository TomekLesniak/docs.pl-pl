---
title: Używanie (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: bdab81ed8acae5e757de0a669922dc79d0303ee4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203595"
---
# <a name="using-entity-sql"></a><span data-ttu-id="cb0ee-102">Używanie (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cb0ee-102">USING (Entity SQL)</span></span>

<span data-ttu-id="cb0ee-103">Określa przestrzenie nazw używane w wyrażeniu zapytania.</span><span class="sxs-lookup"><span data-stu-id="cb0ee-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb0ee-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cb0ee-104">Syntax</span></span>  
  
```sql  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="cb0ee-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="cb0ee-105">Arguments</span></span>  

 `alias`  
 <span data-ttu-id="cb0ee-106">Określa krótszy alias do kwalifikowania przestrzeni nazw za pomocą.</span><span class="sxs-lookup"><span data-stu-id="cb0ee-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="cb0ee-107">Dowolna prawidłowa przestrzeń nazw.</span><span class="sxs-lookup"><span data-stu-id="cb0ee-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb0ee-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="cb0ee-108">Example</span></span>  

 <span data-ttu-id="cb0ee-109">Poniższe zapytanie Entity SQL używa operatora USING, aby określić przestrzenie nazw używane w wyrażeniu zapytania.</span><span class="sxs-lookup"><span data-stu-id="cb0ee-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="cb0ee-110">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="cb0ee-110">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="cb0ee-111">Postępuj zgodnie z procedurą w [instrukcje: wykonywanie zapytania, które zwraca wyniki typu pierwotnego](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="cb0ee-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="cb0ee-112">Przekaż następujące zapytanie jako argument do `ExecutePrimitiveTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="cb0ee-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```csharp
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb0ee-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cb0ee-113">See also</span></span>

- [<span data-ttu-id="cb0ee-114">Przestrzenie nazw</span><span class="sxs-lookup"><span data-stu-id="cb0ee-114">Namespaces</span></span>](namespaces-entity-sql.md)
- [<span data-ttu-id="cb0ee-115">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="cb0ee-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
