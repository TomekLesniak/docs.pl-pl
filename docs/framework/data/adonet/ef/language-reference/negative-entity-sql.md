---
title: '- Poziomem (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 71749dab073fade854c2a494841e3f6b408ebd1d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204414"
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="05775-102">-(Wartość ujemna) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="05775-102">- (Negative) (Entity SQL)</span></span>

<span data-ttu-id="05775-103">Zwraca ujemną wartość wyrażenia liczbowego.</span><span class="sxs-lookup"><span data-stu-id="05775-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05775-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="05775-104">Syntax</span></span>  
  
```sql  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="05775-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="05775-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="05775-106">Dowolne prawidłowe wyrażenie jednego z typów danych liczbowych.</span><span class="sxs-lookup"><span data-stu-id="05775-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="05775-107">Typy wyników</span><span class="sxs-lookup"><span data-stu-id="05775-107">Result Types</span></span>  

 <span data-ttu-id="05775-108">Typ danych `expression` .</span><span class="sxs-lookup"><span data-stu-id="05775-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05775-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="05775-109">Remarks</span></span>  

 <span data-ttu-id="05775-110">Jeśli `expression` jest typem bez znaku, typ wyniku będzie typem ze znakiem, który najlepiej odnosi się do typu `expression` .</span><span class="sxs-lookup"><span data-stu-id="05775-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="05775-111">Na przykład jeśli `expression` jest typu Byte, zostanie zwrócona wartość typu Int16.</span><span class="sxs-lookup"><span data-stu-id="05775-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05775-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="05775-112">Example</span></span>  

 <span data-ttu-id="05775-113">Poniższe zapytanie Entity SQL używa operatora-arytmetycznego, aby zwrócić ujemną wartość wyrażenia liczbowego.</span><span class="sxs-lookup"><span data-stu-id="05775-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="05775-114">Zapytanie jest oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="05775-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="05775-115">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="05775-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="05775-116">Postępuj zgodnie z procedurą w temacie [How to: Execute a Query zwracającej wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="05775-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="05775-117">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="05775-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NEGATIVE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="05775-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="05775-118">See also</span></span>

- [<span data-ttu-id="05775-119">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="05775-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
