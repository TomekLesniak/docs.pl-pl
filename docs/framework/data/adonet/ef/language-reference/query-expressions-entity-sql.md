---
title: Wyrażenia zapytań (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: ca6b79b4b3d3326a74780345decf58367596adb0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175606"
---
# <a name="query-expressions-entity-sql"></a><span data-ttu-id="51775-102">Wyrażenia zapytań (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="51775-102">Query Expressions (Entity SQL)</span></span>

<span data-ttu-id="51775-103">Wyrażenie zapytania łączy wiele różnych operatorów zapytań w jedną składnię.</span><span class="sxs-lookup"><span data-stu-id="51775-103">A query expression combines many different query operators into a single syntax.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="51775-104">oferuje różne rodzaje wyrażeń, w tym następujące: [literały](literals-entity-sql.md), [Parametry](parameters-entity-sql.md), [zmienne](variables-entity-sql.md), operatory, [funkcje](functions-entity-sql.md), operatory ustawiające itd.</span><span class="sxs-lookup"><span data-stu-id="51775-104">provides various kinds of expressions, including the following: [literals](literals-entity-sql.md), [parameters](parameters-entity-sql.md), [variables](variables-entity-sql.md), operators, [functions](functions-entity-sql.md), set operators, and so on.</span></span> <span data-ttu-id="51775-105">Aby uzyskać więcej informacji, zobacz [Entity SQL Reference](entity-sql-reference.md).</span><span class="sxs-lookup"><span data-stu-id="51775-105">For more information, see [Entity SQL Reference](entity-sql-reference.md).</span></span>  
  
## <a name="clauses"></a><span data-ttu-id="51775-106">Klauzule</span><span class="sxs-lookup"><span data-stu-id="51775-106">Clauses</span></span>  

 <span data-ttu-id="51775-107">Wyrażenie zapytania składa się z serii klauzul, które stosują kolejne operacje do kolekcji obiektów.</span><span class="sxs-lookup"><span data-stu-id="51775-107">A query expression is composed of a series of clauses that apply successive operations to a collection of objects.</span></span> <span data-ttu-id="51775-108">Są one oparte na tych samych klauzulach, które znajdują się w standardowej instrukcji SELECT języka SQL: [SELECT](select-entity-sql.md), [from](from-entity-sql.md), [WHERE](where-entity-sql.md), [Group by](group-by-entity-sql.md), [HAVING](having-entity-sql.md)i [order by](order-by-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="51775-108">They are based on the same clauses found in standard a SQL select statement: [SELECT](select-entity-sql.md), [FROM](from-entity-sql.md), [WHERE](where-entity-sql.md), [GROUP BY](group-by-entity-sql.md), [HAVING](having-entity-sql.md), and [ORDER BY](order-by-entity-sql.md).</span></span>  
  
## <a name="scope"></a><span data-ttu-id="51775-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="51775-109">Scope</span></span>  

 <span data-ttu-id="51775-110">Nazwy zdefiniowane w klauzuli FROM są wprowadzane do zakresu od w kolejności wyglądu, od lewej do prawej.</span><span class="sxs-lookup"><span data-stu-id="51775-110">Names defined in the FROM clause are introduced into the FROM scope in order of appearance, left to right.</span></span> <span data-ttu-id="51775-111">Na liście SPRZĘŻENIa wyrażenia mogą odwoływać się do nazw zdefiniowanych wcześniej na liście.</span><span class="sxs-lookup"><span data-stu-id="51775-111">In the JOIN list, expressions can refer to names defined earlier in the list.</span></span> <span data-ttu-id="51775-112">Właściwości publiczne elementów zidentyfikowanych w klauzuli FROM nie są dodawane do zakresu od: muszą być zawsze przywoływane przez nazwę kwalifikowaną aliasem.</span><span class="sxs-lookup"><span data-stu-id="51775-112">Public properties of elements identified in the FROM clause are not added to the FROM scope: They must be always referenced through the alias-qualified name.</span></span> <span data-ttu-id="51775-113">Zwykle wszystkie części wyrażenia SELECT są uwzględniane w zakresie od.</span><span class="sxs-lookup"><span data-stu-id="51775-113">Normally, all parts of the select expression are considered within the FROM scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51775-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="51775-114">See also</span></span>

- [<span data-ttu-id="51775-115">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="51775-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
