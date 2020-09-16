---
title: Traktuj (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
ms.openlocfilehash: 566ac875aec17e4d0aa22ec1962053aeb6ae2a2e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558852"
---
# <a name="treat-entity-sql"></a><span data-ttu-id="7fc51-102">Traktuj (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7fc51-102">TREAT (Entity SQL)</span></span>
<span data-ttu-id="7fc51-103">Traktuje obiekt określonego typu podstawowego jako obiekt określonego typu pochodnego.</span><span class="sxs-lookup"><span data-stu-id="7fc51-103">Treats an object of a particular base type as an object of the specified derived type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fc51-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7fc51-104">Syntax</span></span>  
  
```sql  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a><span data-ttu-id="7fc51-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="7fc51-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="7fc51-106">Każde prawidłowe wyrażenie zapytania, które zwraca jednostkę.</span><span class="sxs-lookup"><span data-stu-id="7fc51-106">Any valid query expression that returns an entity.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7fc51-107">Typ określonego wyrażenia musi być podtypem określonego typu danych lub typ danych musi być podtypem typu wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="7fc51-107">The type of the specified expression must be a subtype of the specified data type, or the data type must be a subtype of the type of expression.</span></span>  
  
 `type`  
 <span data-ttu-id="7fc51-108">Typ jednostki.</span><span class="sxs-lookup"><span data-stu-id="7fc51-108">An entity type.</span></span> <span data-ttu-id="7fc51-109">Typ musi być kwalifikowany za pomocą przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="7fc51-109">The type must be qualified by a namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7fc51-110">Określone wyrażenie musi być podtypem określonego typu danych lub typem danych musi być podtyp wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="7fc51-110">The specified expression must be a subtype of the specified data type, or the data type must be a subtype of the expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7fc51-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="7fc51-111">Return Value</span></span>  
 <span data-ttu-id="7fc51-112">Wartość określonego typu danych.</span><span class="sxs-lookup"><span data-stu-id="7fc51-112">A value of the specified data type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fc51-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7fc51-113">Remarks</span></span>  
 <span data-ttu-id="7fc51-114">Funkcja Traktuj służy do przeprowadzenia rzutowania między powiązanymi klasami.</span><span class="sxs-lookup"><span data-stu-id="7fc51-114">TREAT is used to perform upcasting between related classes.</span></span> <span data-ttu-id="7fc51-115">Na przykład, jeśli `Employee` pochodzi od `Person` i p jest typu `Person` , `TREAT(p AS NamespaceName.Employee)` rzutuje `Person` wystąpienie ogólne na `Employee` ; oznacza to, że umożliwia traktowanie p jako `Employee` .</span><span class="sxs-lookup"><span data-stu-id="7fc51-115">For example, if `Employee` derives from `Person` and p is of type `Person`, `TREAT(p AS NamespaceName.Employee)` upcasts a generic `Person` instance to `Employee`; that is, it allows you to treat p as `Employee`.</span></span>  
  
 <span data-ttu-id="7fc51-116">TRAKTOWANIe jest używane w scenariuszach dziedziczenia, w których można wykonywać zapytania podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="7fc51-116">TREAT is used in inheritance scenarios where you can do a query like the following:</span></span>  
  
```sql  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)
```  
  
 <span data-ttu-id="7fc51-117">To zapytanie przerzutuje `Person` jednostki na `Employee` Typ.</span><span class="sxs-lookup"><span data-stu-id="7fc51-117">This query upcasts `Person` entities to the `Employee` type.</span></span> <span data-ttu-id="7fc51-118">Jeśli wartość p nie jest faktycznie typu `Employee` , wyrażenie zwraca wartość `null` .</span><span class="sxs-lookup"><span data-stu-id="7fc51-118">If the value of p is not actually of type `Employee`, the expression yields the value `null`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7fc51-119">Określone wyrażenie `Employee` musi być podtypem określonego typu danych `Person` lub typem danych musi być podtyp wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="7fc51-119">The specified expression `Employee` must be a subtype of the specified data type `Person`, or the data type must be a subtype of the expression.</span></span> <span data-ttu-id="7fc51-120">W przeciwnym razie wyrażenie spowoduje błąd czasu kompilacji.</span><span class="sxs-lookup"><span data-stu-id="7fc51-120">Otherwise, the expression will result in a compile-time error.</span></span>  
  
 <span data-ttu-id="7fc51-121">W poniższej tabeli przedstawiono zachowanie traktowania niektórych typowych wzorców i mniej popularnych wzorców.</span><span class="sxs-lookup"><span data-stu-id="7fc51-121">The following table shows the behavior of treat over some typical patterns and some less common patterns.</span></span> <span data-ttu-id="7fc51-122">Wszystkie wyjątki są zgłaszane po stronie klienta przed wywołaniem dostawcy:</span><span class="sxs-lookup"><span data-stu-id="7fc51-122">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="7fc51-123">Wzorce</span><span class="sxs-lookup"><span data-stu-id="7fc51-123">Pattern</span></span>|<span data-ttu-id="7fc51-124">Zachowanie</span><span class="sxs-lookup"><span data-stu-id="7fc51-124">Behavior</span></span>|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|<span data-ttu-id="7fc51-125">Zwraca wartość `DbNull`.</span><span class="sxs-lookup"><span data-stu-id="7fc51-125">Returns `DbNull`.</span></span>|  
|`TREAT (null AS ComplexType)`|<span data-ttu-id="7fc51-126">Zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="7fc51-126">Throws an exception.</span></span>|  
|`TREAT (null AS RowType)`|<span data-ttu-id="7fc51-127">Zgłasza wyjątek/</span><span class="sxs-lookup"><span data-stu-id="7fc51-127">Throws an exception/</span></span>|  
|`TREAT (EntityType AS EntityType)`|<span data-ttu-id="7fc51-128">Zwraca `EntityType` lub `null` .</span><span class="sxs-lookup"><span data-stu-id="7fc51-128">Returns `EntityType` or `null`.</span></span>|  
|`TREAT (ComplexType AS ComplexType)`|<span data-ttu-id="7fc51-129">Zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="7fc51-129">Throws an exception.</span></span>|  
|`TREAT (RowType AS RowType)`|<span data-ttu-id="7fc51-130">Zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="7fc51-130">Throws an exception.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7fc51-131">Przykład</span><span class="sxs-lookup"><span data-stu-id="7fc51-131">Example</span></span>  
 <span data-ttu-id="7fc51-132">Następujące [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytanie używa operatora Traktuj do konwersji obiektu typu kursu do kolekcji obiektów typu OnsiteCourse.</span><span class="sxs-lookup"><span data-stu-id="7fc51-132">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="7fc51-133">Zapytanie jest oparte na [modelu szkoły](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="7fc51-133">The query is based on the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 [!code-sql[DP EntityServices Concepts#TREAT_ISOF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="7fc51-134">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7fc51-134">See also</span></span>

- [<span data-ttu-id="7fc51-135">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="7fc51-135">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="7fc51-136">Typy strukturalne dopuszczające wartości Null</span><span class="sxs-lookup"><span data-stu-id="7fc51-136">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
