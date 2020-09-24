---
title: KLUCZ (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: 07160467dcee60377e3ef448fdc66092da4e06e7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161974"
---
# <a name="key-entity-sql"></a><span data-ttu-id="06305-102">KLUCZ (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="06305-102">KEY (Entity SQL)</span></span>

<span data-ttu-id="06305-103">Wyodrębnia klucz odwołania lub wyrażenia jednostki.</span><span class="sxs-lookup"><span data-stu-id="06305-103">Extracts the key of a reference or of an entity expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06305-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="06305-104">Syntax</span></span>  
  
```sql  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a><span data-ttu-id="06305-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="06305-105">Remarks</span></span>  

 <span data-ttu-id="06305-106">Klucz jednostki zawiera wartości klucza w prawidłowej kolejności określonej jednostki lub odwołania do jednostki.</span><span class="sxs-lookup"><span data-stu-id="06305-106">An entity key contains the key values in the correct order of the specified entity or entity reference.</span></span> <span data-ttu-id="06305-107">Ponieważ wiele zestawów jednostek może opierać się na tym samym typie, ten sam klucz może pojawić się w każdym zestawie jednostek.</span><span class="sxs-lookup"><span data-stu-id="06305-107">Because multiple entity sets can be based on the same type, the same key might appear in each entity set.</span></span> <span data-ttu-id="06305-108">Aby uzyskać unikatowe odwołanie, użyj `REF` .</span><span class="sxs-lookup"><span data-stu-id="06305-108">To get a unique reference, use `REF`.</span></span> <span data-ttu-id="06305-109">Zwracany typ operatora klucza jest typem wiersza, który zawiera jedno pole dla każdego klucza jednostki, w tej samej kolejności.</span><span class="sxs-lookup"><span data-stu-id="06305-109">The return type of the KEY operator is a row type that includes one field for each key of the entity, in the same order.</span></span>  
  
 <span data-ttu-id="06305-110">W poniższym przykładzie operator klucza jest przekazywać odwołanie do jednostki BadOrder i zwraca część klucza tego odwołania.</span><span class="sxs-lookup"><span data-stu-id="06305-110">In the following example, the key operator is passed a reference to the BadOrder entity, and returns the key portion of that reference.</span></span> <span data-ttu-id="06305-111">W tym przypadku typ rekordu z dokładnie jednym polem odpowiadającym `Id` właściwości.</span><span class="sxs-lookup"><span data-stu-id="06305-111">In this case, a record type with exactly one field corresponding to the `Id` property.</span></span>  
  
```sql  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )
from LOB.Orders as o  
```  
  
## <a name="example"></a><span data-ttu-id="06305-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="06305-112">Example</span></span>  

 <span data-ttu-id="06305-113">Poniższe zapytanie Entity SQL używa operatora KEY do wyodrębnienia części klucza wyrażenia z odwołaniem do typu.</span><span class="sxs-lookup"><span data-stu-id="06305-113">The following Entity SQL query uses the KEY operator to extract the key portion of an expression with type reference.</span></span> <span data-ttu-id="06305-114">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="06305-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="06305-115">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="06305-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="06305-116">Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="06305-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="06305-117">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="06305-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#KEY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#key)]  
  
## <a name="see-also"></a><span data-ttu-id="06305-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="06305-118">See also</span></span>

- [<span data-ttu-id="06305-119">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="06305-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="06305-120">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="06305-120">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="06305-121">UMIESZCZONE</span><span class="sxs-lookup"><span data-stu-id="06305-121">REF</span></span>](ref-entity-sql.md)
- [<span data-ttu-id="06305-122">DEREF</span><span class="sxs-lookup"><span data-stu-id="06305-122">DEREF</span></span>](deref-entity-sql.md)
