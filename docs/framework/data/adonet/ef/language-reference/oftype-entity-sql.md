---
title: OFTYPE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 6d259ca7-bbf0-40f8-a154-181d25c0d67e
ms.openlocfilehash: b5600b4cee23945fe60142b370feb35ac1a2efa1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175684"
---
# <a name="oftype-entity-sql"></a><span data-ttu-id="b2d59-102">OFTYPE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b2d59-102">OFTYPE (Entity SQL)</span></span>

<span data-ttu-id="b2d59-103">Zwraca kolekcję obiektów z wyrażenia zapytania, które jest określonego typu.</span><span class="sxs-lookup"><span data-stu-id="b2d59-103">Returns a collection of objects from a query expression that is of a specific type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2d59-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b2d59-104">Syntax</span></span>  
  
```sql  
OFTYPE ( expression, [ONLY] test_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="b2d59-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="b2d59-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="b2d59-106">Każde prawidłowe wyrażenie zapytania, które zwraca kolekcję obiektów.</span><span class="sxs-lookup"><span data-stu-id="b2d59-106">Any valid query expression that returns a collection of objects.</span></span>  
  
 `test_type`  
 <span data-ttu-id="b2d59-107">Typ do testowania każdego obiektu zwróconego przez `expression` .</span><span class="sxs-lookup"><span data-stu-id="b2d59-107">The type to test each object returned by `expression` against.</span></span> <span data-ttu-id="b2d59-108">Typ musi być kwalifikowany za pomocą przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="b2d59-108">The type must be qualified by a namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2d59-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="b2d59-109">Return Value</span></span>  

 <span data-ttu-id="b2d59-110">Kolekcja obiektów typu `test_type` , lub typ podstawowy lub typ pochodny `test_type` .</span><span class="sxs-lookup"><span data-stu-id="b2d59-110">A collection of objects that are of type `test_type`, or a base type or derived type of `test_type`.</span></span> <span data-ttu-id="b2d59-111">Jeśli jest określony tylko, zostaną zwrócone tylko wystąpienia `test_type` lub pustą kolekcję.</span><span class="sxs-lookup"><span data-stu-id="b2d59-111">If ONLY is specified, only instances of the `test_type` or an empty collection will be returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2d59-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b2d59-112">Remarks</span></span>  

 <span data-ttu-id="b2d59-113">`OFTYPE`Wyrażenie określa wyrażenie typu, które zostało wystawione w celu przeprowadzenia testu typu dla każdego elementu kolekcji.</span><span class="sxs-lookup"><span data-stu-id="b2d59-113">An `OFTYPE` expression specifies a type expression that is issued to perform a type test against each element of a collection.</span></span>  <span data-ttu-id="b2d59-114">`OFTYPE`Wyrażenie tworzy nową kolekcję określonego typu zawierającego tylko te elementy, które były równoważne temu typowi lub podtyp.</span><span class="sxs-lookup"><span data-stu-id="b2d59-114">The `OFTYPE` expression produces a new collection of the specified type containing only those elements that were either equivalent to that type or a sub-type of it.</span></span>  
  
 <span data-ttu-id="b2d59-115">`OFTYPE`Wyrażenie jest skrótem następującego wyrażenia zapytania:</span><span class="sxs-lookup"><span data-stu-id="b2d59-115">An `OFTYPE` expression is an abbreviation of the following query expression:</span></span>  
  
```sql  
select value treat(t as T) from ts as t where t is of (T)  
```  
  
 <span data-ttu-id="b2d59-116">Mając na względzie, że Menedżer jest podtypem pracownika, następujące wyrażenie tworzy kolekcję tylko menedżerów z kolekcji Employees:</span><span class="sxs-lookup"><span data-stu-id="b2d59-116">Given that a Manager is a subtype of Employee, the following expression produces a collection of only managers from a collection of employees:</span></span>  
  
```sql  
OfType(employees, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="b2d59-117">Istnieje również możliwość rzutowania kolekcji przy użyciu filtru typu:</span><span class="sxs-lookup"><span data-stu-id="b2d59-117">It is also possible to up cast a collection using the type filter:</span></span>  
  
```sql
OfType(executives, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="b2d59-118">Ze względu na to, że wszyscy kierownicy są menedżerami, powstająca kolekcja nadal zawiera wszystkie pierwotnych kierownictwa, chociaż kolekcja została teraz wpisana jako kolekcja menedżerów.</span><span class="sxs-lookup"><span data-stu-id="b2d59-118">Since all executives are managers, the resulting collection still contains all the original executives, though the collection is now typed as a collection of managers.</span></span>  
  
 <span data-ttu-id="b2d59-119">W poniższej tabeli przedstawiono zachowanie `OFTYPE` operatora względem niektórych wzorców.</span><span class="sxs-lookup"><span data-stu-id="b2d59-119">The following table shows the behavior of the `OFTYPE` operator over some patterns.</span></span> <span data-ttu-id="b2d59-120">Wszystkie wyjątki są zgłaszane po stronie klienta przed wywołaniem dostawcy:</span><span class="sxs-lookup"><span data-stu-id="b2d59-120">All exceptions are thrown from the client side before the provider is invoked:</span></span>  
  
|<span data-ttu-id="b2d59-121">Wzorce</span><span class="sxs-lookup"><span data-stu-id="b2d59-121">Pattern</span></span>|<span data-ttu-id="b2d59-122">Zachowanie</span><span class="sxs-lookup"><span data-stu-id="b2d59-122">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="b2d59-123">OFTYPE (kolekcja (EntityType), EntityType)</span><span class="sxs-lookup"><span data-stu-id="b2d59-123">OFTYPE(Collection(EntityType), EntityType)</span></span>|<span data-ttu-id="b2d59-124">Kolekcja (EntityType)</span><span class="sxs-lookup"><span data-stu-id="b2d59-124">Collection(EntityType)</span></span>|  
|<span data-ttu-id="b2d59-125">OFTYPE (kolekcja (ComplexType), ComplexType)</span><span class="sxs-lookup"><span data-stu-id="b2d59-125">OFTYPE(Collection(ComplexType), ComplexType)</span></span>|<span data-ttu-id="b2d59-126">Generuje</span><span class="sxs-lookup"><span data-stu-id="b2d59-126">Throws</span></span>|  
|<span data-ttu-id="b2d59-127">OFTYPE (Collection (RowType), RowType)</span><span class="sxs-lookup"><span data-stu-id="b2d59-127">OFTYPE(Collection(RowType), RowType)</span></span>|<span data-ttu-id="b2d59-128">Generuje</span><span class="sxs-lookup"><span data-stu-id="b2d59-128">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b2d59-129">Przykład</span><span class="sxs-lookup"><span data-stu-id="b2d59-129">Example</span></span>  

 <span data-ttu-id="b2d59-130">Następujące [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytanie używa operatora OFTYPE do zwrócenia kolekcji obiektów OnsiteCourse z kolekcji obiektów kursów.</span><span class="sxs-lookup"><span data-stu-id="b2d59-130">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the OFTYPE operator to return a collection of OnsiteCourse objects from a collection of Course objects.</span></span> <span data-ttu-id="b2d59-131">Zapytanie jest oparte na [modelu szkoły](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b2d59-131">The query is based on the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 [!code-sql[DP EntityServices Concepts#OFTYPE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#oftype)]  
  
## <a name="see-also"></a><span data-ttu-id="b2d59-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b2d59-132">See also</span></span>

- [<span data-ttu-id="b2d59-133">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="b2d59-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
