---
title: Szybkie odwołanie do języka Entity SQL
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: 7ec3b6fc184b4f169d6f6489bda0ec8fa4abb4f5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148143"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="b5f9c-102">Szybkie odwołanie do języka Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b5f9c-102">Entity SQL Quick Reference</span></span>

<span data-ttu-id="b5f9c-103">Ten temat zawiera krótkie informacje o [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytaniach.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="b5f9c-104">Zapytania w tym temacie są oparte na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="b5f9c-105">Literały</span><span class="sxs-lookup"><span data-stu-id="b5f9c-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="b5f9c-106">String</span><span class="sxs-lookup"><span data-stu-id="b5f9c-106">String</span></span>  

 <span data-ttu-id="b5f9c-107">Istnieją literały ciągu Unicode i inne niż Unicode.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="b5f9c-108">Ciągi Unicode są poprzedzone znakiem N. Na przykład `N'hello'` .</span><span class="sxs-lookup"><span data-stu-id="b5f9c-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="b5f9c-109">Poniżej znajduje się przykład literału ciągu innego niż Unicode:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="b5f9c-110">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-110">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-111">Wartość</span><span class="sxs-lookup"><span data-stu-id="b5f9c-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="b5f9c-112">hello</span><span class="sxs-lookup"><span data-stu-id="b5f9c-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="b5f9c-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="b5f9c-113">DateTime</span></span>  

 <span data-ttu-id="b5f9c-114">W literałach DateTime oba części daty i godziny są obowiązkowe.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="b5f9c-115">Brak wartości domyślnych.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-115">There are no default values.</span></span>  
  
 <span data-ttu-id="b5f9c-116">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-116">Example:</span></span>  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="b5f9c-117">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-117">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-118">Wartość</span><span class="sxs-lookup"><span data-stu-id="b5f9c-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="b5f9c-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="b5f9c-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="b5f9c-120">Integer</span><span class="sxs-lookup"><span data-stu-id="b5f9c-120">Integer</span></span>  

 <span data-ttu-id="b5f9c-121">Literały całkowite mogą być typu Int32 (123), UInt32 (123U), Int64 (123L) i UInt64 (123UL).</span><span class="sxs-lookup"><span data-stu-id="b5f9c-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="b5f9c-122">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-122">Example:</span></span>  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="b5f9c-123">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-123">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-124">Wartość</span><span class="sxs-lookup"><span data-stu-id="b5f9c-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="b5f9c-125">1</span><span class="sxs-lookup"><span data-stu-id="b5f9c-125">1</span></span>|  
|<span data-ttu-id="b5f9c-126">2</span><span class="sxs-lookup"><span data-stu-id="b5f9c-126">2</span></span>|  
|<span data-ttu-id="b5f9c-127">3</span><span class="sxs-lookup"><span data-stu-id="b5f9c-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="b5f9c-128">Inne</span><span class="sxs-lookup"><span data-stu-id="b5f9c-128">Other</span></span>  

 <span data-ttu-id="b5f9c-129">Inne literały obsługiwane przez [!INCLUDE[esql](../../../../../../includes/esql-md.md)] program to GUID, Binary, float/Double, Decimal i `null` .</span><span class="sxs-lookup"><span data-stu-id="b5f9c-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="b5f9c-130">Literały o wartości null w [!INCLUDE[esql](../../../../../../includes/esql-md.md)] są uważane za zgodne z każdym innym typem w modelu koncepcyjnym.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="b5f9c-131">Konstruktory typów</span><span class="sxs-lookup"><span data-stu-id="b5f9c-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="b5f9c-132">ROW</span><span class="sxs-lookup"><span data-stu-id="b5f9c-132">ROW</span></span>  

 <span data-ttu-id="b5f9c-133">[Wiersz](row-entity-sql.md) konstruuje anonimową, strukturalnie wpisaną wartość w postaci: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="b5f9c-133">[ROW](row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="b5f9c-134">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-134">Example:</span></span>  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 <span data-ttu-id="b5f9c-135">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-135">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="b5f9c-136">ProductID</span></span>|<span data-ttu-id="b5f9c-137">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b5f9c-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="b5f9c-138">1</span><span class="sxs-lookup"><span data-stu-id="b5f9c-138">1</span></span>|<span data-ttu-id="b5f9c-139">Wyścigi regulowane</span><span class="sxs-lookup"><span data-stu-id="b5f9c-139">Adjustable Race</span></span>|  
|<span data-ttu-id="b5f9c-140">879</span><span class="sxs-lookup"><span data-stu-id="b5f9c-140">879</span></span>|<span data-ttu-id="b5f9c-141">Podstawa roweru ogólnego przeznaczenia</span><span class="sxs-lookup"><span data-stu-id="b5f9c-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="b5f9c-142">712</span><span class="sxs-lookup"><span data-stu-id="b5f9c-142">712</span></span>|<span data-ttu-id="b5f9c-143">AWC logo</span><span class="sxs-lookup"><span data-stu-id="b5f9c-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="b5f9c-144">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-144">...</span></span>|<span data-ttu-id="b5f9c-145">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="b5f9c-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="b5f9c-146">MULTISET</span></span>  

 <span data-ttu-id="b5f9c-147">Kolekcje [zestawów wielokrotnych](multiset-entity-sql.md) , takie jak:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-147">[MULTISET](multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="b5f9c-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="b5f9c-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="b5f9c-149">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-149">Example:</span></span>  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="b5f9c-150">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-150">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="b5f9c-151">ProductID</span></span>|<span data-ttu-id="b5f9c-152">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b5f9c-152">Name</span></span>|<span data-ttu-id="b5f9c-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="b5f9c-153">ProductNumber</span></span>|<span data-ttu-id="b5f9c-154">…</span><span class="sxs-lookup"><span data-stu-id="b5f9c-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="b5f9c-155">842</span><span class="sxs-lookup"><span data-stu-id="b5f9c-155">842</span></span>|<span data-ttu-id="b5f9c-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="b5f9c-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="b5f9c-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="b5f9c-157">PA-T100</span></span>|<span data-ttu-id="b5f9c-158">…</span><span class="sxs-lookup"><span data-stu-id="b5f9c-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="b5f9c-159">Obiekt</span><span class="sxs-lookup"><span data-stu-id="b5f9c-159">Object</span></span>  

 <span data-ttu-id="b5f9c-160">Konstrukcje [konstruktorów nazwanych](named-type-constructor-entity-sql.md) (o nazwach) obiekty zdefiniowane przez użytkownika, takie jak `person("abc", 12)` .</span><span class="sxs-lookup"><span data-stu-id="b5f9c-160">[Named Type Constructor](named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="b5f9c-161">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-161">Example:</span></span>  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail
AS o  
```  
  
 <span data-ttu-id="b5f9c-162">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-162">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="b5f9c-163">SalesOrderDetailID</span></span>|<span data-ttu-id="b5f9c-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="b5f9c-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="b5f9c-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="b5f9c-165">OrderQty</span></span>|<span data-ttu-id="b5f9c-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="b5f9c-166">ProductID</span></span>|<span data-ttu-id="b5f9c-167">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="b5f9c-168">1</span><span class="sxs-lookup"><span data-stu-id="b5f9c-168">1</span></span>|<span data-ttu-id="b5f9c-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="b5f9c-169">4911-403C-98</span></span>|<span data-ttu-id="b5f9c-170">1</span><span class="sxs-lookup"><span data-stu-id="b5f9c-170">1</span></span>|<span data-ttu-id="b5f9c-171">776</span><span class="sxs-lookup"><span data-stu-id="b5f9c-171">776</span></span>|<span data-ttu-id="b5f9c-172">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-172">...</span></span>|  
|<span data-ttu-id="b5f9c-173">2</span><span class="sxs-lookup"><span data-stu-id="b5f9c-173">2</span></span>|<span data-ttu-id="b5f9c-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="b5f9c-174">4911-403C-98</span></span>|<span data-ttu-id="b5f9c-175">3</span><span class="sxs-lookup"><span data-stu-id="b5f9c-175">3</span></span>|<span data-ttu-id="b5f9c-176">777</span><span class="sxs-lookup"><span data-stu-id="b5f9c-176">777</span></span>|<span data-ttu-id="b5f9c-177">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-177">...</span></span>|  
|<span data-ttu-id="b5f9c-178">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-178">...</span></span>|<span data-ttu-id="b5f9c-179">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-179">...</span></span>|<span data-ttu-id="b5f9c-180">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-180">...</span></span>|<span data-ttu-id="b5f9c-181">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-181">...</span></span>|<span data-ttu-id="b5f9c-182">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="b5f9c-183">Odwołania</span><span class="sxs-lookup"><span data-stu-id="b5f9c-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="b5f9c-184">REF</span><span class="sxs-lookup"><span data-stu-id="b5f9c-184">REF</span></span>  

 <span data-ttu-id="b5f9c-185">[Ref](ref-entity-sql.md) tworzy odwołanie do wystąpienia typu jednostki.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-185">[REF](ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="b5f9c-186">Na przykład następujące zapytanie zwraca odwołania do każdej jednostki zamówienia w zestawie jednostek Orders:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="b5f9c-187">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-187">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-188">Wartość</span><span class="sxs-lookup"><span data-stu-id="b5f9c-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="b5f9c-189">1</span><span class="sxs-lookup"><span data-stu-id="b5f9c-189">1</span></span>|  
|<span data-ttu-id="b5f9c-190">2</span><span class="sxs-lookup"><span data-stu-id="b5f9c-190">2</span></span>|  
|<span data-ttu-id="b5f9c-191">3</span><span class="sxs-lookup"><span data-stu-id="b5f9c-191">3</span></span>|  
|<span data-ttu-id="b5f9c-192">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-192">...</span></span>|  
  
 <span data-ttu-id="b5f9c-193">Poniższy przykład używa operatora wyodrębniania właściwości (.) w celu uzyskania dostępu do właściwości jednostki.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="b5f9c-194">Gdy jest używany operator wyodrębniania właściwości, odwołanie jest automatycznie wywoływać.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="b5f9c-195">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-195">Example:</span></span>  
  
```sql  
SELECT VALUE REF(p).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="b5f9c-196">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-196">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-197">Wartość</span><span class="sxs-lookup"><span data-stu-id="b5f9c-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="b5f9c-198">Wyścigi regulowane</span><span class="sxs-lookup"><span data-stu-id="b5f9c-198">Adjustable Race</span></span>|  
|<span data-ttu-id="b5f9c-199">Podstawa roweru ogólnego przeznaczenia</span><span class="sxs-lookup"><span data-stu-id="b5f9c-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="b5f9c-200">AWC logo</span><span class="sxs-lookup"><span data-stu-id="b5f9c-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="b5f9c-201">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="b5f9c-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="b5f9c-202">DEREF</span></span>  

 <span data-ttu-id="b5f9c-203">[DEREF](deref-entity-sql.md) odwołuje się do wartości odniesienia i tworzy wynik tego odwołania.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-203">[DEREF](deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="b5f9c-204">Na przykład następujące zapytanie tworzy jednostki Order dla każdego zamówienia w zestawie jednostek Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2` ..</span><span class="sxs-lookup"><span data-stu-id="b5f9c-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="b5f9c-205">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-205">Example:</span></span>  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="b5f9c-206">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-206">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-207">Wartość</span><span class="sxs-lookup"><span data-stu-id="b5f9c-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="b5f9c-208">Wyścigi regulowane</span><span class="sxs-lookup"><span data-stu-id="b5f9c-208">Adjustable Race</span></span>|  
|<span data-ttu-id="b5f9c-209">Podstawa roweru ogólnego przeznaczenia</span><span class="sxs-lookup"><span data-stu-id="b5f9c-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="b5f9c-210">AWC logo</span><span class="sxs-lookup"><span data-stu-id="b5f9c-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="b5f9c-211">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="b5f9c-212">CREATEREF I KLUCZ</span><span class="sxs-lookup"><span data-stu-id="b5f9c-212">CREATEREF AND KEY</span></span>  

 <span data-ttu-id="b5f9c-213">[CreateRef](createref-entity-sql.md) tworzy odwołanie z przekazywaniem klucza.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-213">[CREATEREF](createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="b5f9c-214">[Klucz](key-entity-sql.md) wyodrębnia część klucza wyrażenia z odwołaniem do typu.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-214">[KEY](key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="b5f9c-215">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-215">Example:</span></span>  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))
    FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="b5f9c-216">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-216">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="b5f9c-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="b5f9c-218">980</span><span class="sxs-lookup"><span data-stu-id="b5f9c-218">980</span></span>|  
|<span data-ttu-id="b5f9c-219">365</span><span class="sxs-lookup"><span data-stu-id="b5f9c-219">365</span></span>|  
|<span data-ttu-id="b5f9c-220">771</span><span class="sxs-lookup"><span data-stu-id="b5f9c-220">771</span></span>|  
|<span data-ttu-id="b5f9c-221">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="b5f9c-222">Funkcje</span><span class="sxs-lookup"><span data-stu-id="b5f9c-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="b5f9c-223">Canonical</span><span class="sxs-lookup"><span data-stu-id="b5f9c-223">Canonical</span></span>  

 <span data-ttu-id="b5f9c-224">Przestrzeń nazw dla [funkcji kanonicznych](canonical-functions.md) to EDM, jak w `Edm.Length("string")` .</span><span class="sxs-lookup"><span data-stu-id="b5f9c-224">The namespace for [canonical functions](canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="b5f9c-225">Nie trzeba określać przestrzeni nazw, chyba że zostanie zaimportowana inna przestrzeń nazw, która zawiera funkcję o takiej samej nazwie jak funkcja kanoniczna.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="b5f9c-226">Jeśli dwie przestrzenie nazw mają tę samą funkcję, użytkownik powinien mieć określoną pełną nazwę.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="b5f9c-227">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-227">Example:</span></span>  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="b5f9c-228">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-228">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="b5f9c-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="b5f9c-230">6</span><span class="sxs-lookup"><span data-stu-id="b5f9c-230">6</span></span>|  
|<span data-ttu-id="b5f9c-231">6</span><span class="sxs-lookup"><span data-stu-id="b5f9c-231">6</span></span>|  
|<span data-ttu-id="b5f9c-232">5</span><span class="sxs-lookup"><span data-stu-id="b5f9c-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="b5f9c-233">Specyficzne dla dostawcy firmy Microsoft</span><span class="sxs-lookup"><span data-stu-id="b5f9c-233">Microsoft Provider-Specific</span></span>  

 <span data-ttu-id="b5f9c-234">[Funkcje specyficzne dla dostawcy firmy Microsoft](../sqlclient-for-ef-functions.md) znajdują się w `SqlServer` przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-234">[Microsoft provider-specific functions](../sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="b5f9c-235">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-235">Example:</span></span>  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="b5f9c-236">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-236">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="b5f9c-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="b5f9c-238">27</span><span class="sxs-lookup"><span data-stu-id="b5f9c-238">27</span></span>|  
|<span data-ttu-id="b5f9c-239">27</span><span class="sxs-lookup"><span data-stu-id="b5f9c-239">27</span></span>|  
|<span data-ttu-id="b5f9c-240">26</span><span class="sxs-lookup"><span data-stu-id="b5f9c-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="b5f9c-241">Przestrzenie nazw</span><span class="sxs-lookup"><span data-stu-id="b5f9c-241">Namespaces</span></span>  

 <span data-ttu-id="b5f9c-242">[Użycie](using-entity-sql.md) określa przestrzenie nazw używane w wyrażeniu zapytania.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-242">[USING](using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="b5f9c-243">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-243">Example:</span></span>  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="b5f9c-244">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-244">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-245">Wartość</span><span class="sxs-lookup"><span data-stu-id="b5f9c-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="b5f9c-246">aa</span><span class="sxs-lookup"><span data-stu-id="b5f9c-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="b5f9c-247">Stronicowanie</span><span class="sxs-lookup"><span data-stu-id="b5f9c-247">Paging</span></span>  

 <span data-ttu-id="b5f9c-248">Stronicowanie może być wyrażone za pomocą deklaracji podrzędnych klauzul [Skip](skip-entity-sql.md) i [Limit](limit-entity-sql.md) do klauzuli [order by](order-by-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="b5f9c-248">Paging can be expressed by declaring a [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses to the [ORDER BY](order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="b5f9c-249">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-249">Example:</span></span>  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="b5f9c-250">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-250">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-251">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="b5f9c-251">ID</span></span>|<span data-ttu-id="b5f9c-252">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b5f9c-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="b5f9c-253">10</span><span class="sxs-lookup"><span data-stu-id="b5f9c-253">10</span></span>|<span data-ttu-id="b5f9c-254">Adina</span><span class="sxs-lookup"><span data-stu-id="b5f9c-254">Adina</span></span>|  
|<span data-ttu-id="b5f9c-255">11</span><span class="sxs-lookup"><span data-stu-id="b5f9c-255">11</span></span>|<span data-ttu-id="b5f9c-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="b5f9c-256">Agcaoili</span></span>|  
|<span data-ttu-id="b5f9c-257">12</span><span class="sxs-lookup"><span data-stu-id="b5f9c-257">12</span></span>|<span data-ttu-id="b5f9c-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="b5f9c-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="b5f9c-259">Grupowanie</span><span class="sxs-lookup"><span data-stu-id="b5f9c-259">Grouping</span></span>  

 <span data-ttu-id="b5f9c-260">[Grupowanie według](group-by-entity-sql.md) określa grupy, do których obiekty zwracane przez zapytanie ([SELECT](select-entity-sql.md)) mają zostać umieszczone.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-260">[GROUPING BY](group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="b5f9c-261">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-261">Example:</span></span>  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="b5f9c-262">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-262">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-263">name</span><span class="sxs-lookup"><span data-stu-id="b5f9c-263">name</span></span>|  
|----------|  
|<span data-ttu-id="b5f9c-264">WSZYSTKO — zestaw stanowisk górskich</span><span class="sxs-lookup"><span data-stu-id="b5f9c-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="b5f9c-265">Zestaw siedzeń górskich ML</span><span class="sxs-lookup"><span data-stu-id="b5f9c-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="b5f9c-266">Zestaw miejsc górskich HL</span><span class="sxs-lookup"><span data-stu-id="b5f9c-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="b5f9c-267">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="b5f9c-268">Nawigacja</span><span class="sxs-lookup"><span data-stu-id="b5f9c-268">Navigation</span></span>  

 <span data-ttu-id="b5f9c-269">Operator nawigacji relacji umożliwia nawigowanie po relacji od jednej jednostki (od końca) do innej (do końca).</span><span class="sxs-lookup"><span data-stu-id="b5f9c-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="b5f9c-270">[Nawigacja](navigate-entity-sql.md) przyjmuje typ relacji kwalifikowana jako \<namespace> . \<relationship type name> .</span><span class="sxs-lookup"><span data-stu-id="b5f9c-270">[NAVIGATE](navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="b5f9c-271">Funkcja nawigacji zwraca wartość Ref, \<T> Jeśli Kardynalność końcową jest równa 1.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="b5f9c-272">Jeśli Kardynalność do końca to n, \<T> zostanie zwrócona kolekcja<Ref>.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="b5f9c-273">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-273">Example:</span></span>  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="b5f9c-274">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-274">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="b5f9c-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="b5f9c-276">1</span><span class="sxs-lookup"><span data-stu-id="b5f9c-276">1</span></span>|  
|<span data-ttu-id="b5f9c-277">2</span><span class="sxs-lookup"><span data-stu-id="b5f9c-277">2</span></span>|  
|<span data-ttu-id="b5f9c-278">3</span><span class="sxs-lookup"><span data-stu-id="b5f9c-278">3</span></span>|  
|<span data-ttu-id="b5f9c-279">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="b5f9c-280">WYBIERZ POZYCJĘ WARTOŚĆ I WYBIERZ POZYCJĘ</span><span class="sxs-lookup"><span data-stu-id="b5f9c-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="b5f9c-281">WYBIERZ WARTOŚĆ</span><span class="sxs-lookup"><span data-stu-id="b5f9c-281">SELECT VALUE</span></span>  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="b5f9c-282">udostępnia klauzulę SELECT VALUE, aby pominąć konstruowanie niejawnego wiersza.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-282">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="b5f9c-283">W klauzuli SELECT VALUE można określić tylko jeden element.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="b5f9c-284">Gdy taka klauzula jest używana, żadna otoka wiersza nie jest zbudowana wokół elementów w klauzuli SELECT i można utworzyć kolekcję żądanego kształtu, na przykład: `SELECT VALUE a` .</span><span class="sxs-lookup"><span data-stu-id="b5f9c-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="b5f9c-285">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-285">Example:</span></span>  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="b5f9c-286">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-286">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-287">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b5f9c-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="b5f9c-288">Wyścigi regulowane</span><span class="sxs-lookup"><span data-stu-id="b5f9c-288">Adjustable Race</span></span>|  
|<span data-ttu-id="b5f9c-289">Podstawa roweru ogólnego przeznaczenia</span><span class="sxs-lookup"><span data-stu-id="b5f9c-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="b5f9c-290">AWC logo</span><span class="sxs-lookup"><span data-stu-id="b5f9c-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="b5f9c-291">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="b5f9c-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="b5f9c-292">SELECT</span></span>  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="b5f9c-293">udostępnia także konstruktora wierszy do konstruowania dowolnych wierszy.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-293">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="b5f9c-294">Zaznacz powoduje, że co najmniej jeden element w projekcji i wyniki w rekordzie danych z polami, na przykład: `SELECT a, b, c` .</span><span class="sxs-lookup"><span data-stu-id="b5f9c-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="b5f9c-295">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-295">Example:</span></span>  
  
 <span data-ttu-id="b5f9c-296">Wybierz pozycję p.Name, p. ProductID z AdventureWorksEntities. Product jako p Output:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="b5f9c-297">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b5f9c-297">Name</span></span>|<span data-ttu-id="b5f9c-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="b5f9c-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="b5f9c-299">Wyścigi regulowane</span><span class="sxs-lookup"><span data-stu-id="b5f9c-299">Adjustable Race</span></span>|<span data-ttu-id="b5f9c-300">1</span><span class="sxs-lookup"><span data-stu-id="b5f9c-300">1</span></span>|  
|<span data-ttu-id="b5f9c-301">Podstawa roweru ogólnego przeznaczenia</span><span class="sxs-lookup"><span data-stu-id="b5f9c-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="b5f9c-302">879</span><span class="sxs-lookup"><span data-stu-id="b5f9c-302">879</span></span>|  
|<span data-ttu-id="b5f9c-303">AWC logo</span><span class="sxs-lookup"><span data-stu-id="b5f9c-303">AWC Logo Cap</span></span>|<span data-ttu-id="b5f9c-304">712</span><span class="sxs-lookup"><span data-stu-id="b5f9c-304">712</span></span>|  
|<span data-ttu-id="b5f9c-305">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-305">...</span></span>|<span data-ttu-id="b5f9c-306">...</span><span class="sxs-lookup"><span data-stu-id="b5f9c-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="b5f9c-307">WYRAŻENIE CASE</span><span class="sxs-lookup"><span data-stu-id="b5f9c-307">CASE EXPRESSION</span></span>  

 <span data-ttu-id="b5f9c-308">[Wyrażenie CASE](case-entity-sql.md) oblicza zestaw wyrażeń logicznych, aby określić wynik.</span><span class="sxs-lookup"><span data-stu-id="b5f9c-308">The [case expression](case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="b5f9c-309">Przykład:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-309">Example:</span></span>  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="b5f9c-310">Dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b5f9c-310">Output:</span></span>  
  
|<span data-ttu-id="b5f9c-311">Wartość</span><span class="sxs-lookup"><span data-stu-id="b5f9c-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="b5f9c-312">TRUE</span><span class="sxs-lookup"><span data-stu-id="b5f9c-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5f9c-313">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b5f9c-313">See also</span></span>

- [<span data-ttu-id="b5f9c-314">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="b5f9c-314">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="b5f9c-315">Omówienie jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="b5f9c-315">Entity SQL Overview</span></span>](entity-sql-overview.md)
