---
title: System typów (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: d4c8ba7a9d9b58220455b50ff99960fa132c00c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200995"
---
# <a name="type-system-entity-sql"></a><span data-ttu-id="20549-102">System typów (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="20549-102">Type System (Entity SQL)</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="20549-103">obsługuje wiele typów:</span><span class="sxs-lookup"><span data-stu-id="20549-103">supports a number of types:</span></span>  
  
- <span data-ttu-id="20549-104">Typy pierwotne (proste), takie jak `Int32` i `String.`</span><span class="sxs-lookup"><span data-stu-id="20549-104">Primitive (simple) types such as `Int32` and `String.`</span></span>  
  
- <span data-ttu-id="20549-105">Typy nominalne, które są zdefiniowane w schemacie, takie jak <xref:System.Data.Metadata.Edm.EntityType> , <xref:System.Data.Metadata.Edm.ComplexType> , i <xref:System.Data.Metadata.Edm.RelationshipType> .</span><span class="sxs-lookup"><span data-stu-id="20549-105">Nominal types that are defined in the schema, such as <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType>, and <xref:System.Data.Metadata.Edm.RelationshipType>.</span></span>  
  
- <span data-ttu-id="20549-106">Typy anonimowe, które nie są zdefiniowane w schemacie jawnie: <xref:System.Data.Metadata.Edm.CollectionType> , <xref:System.Data.Metadata.Edm.RowType> , i <xref:System.Data.Metadata.Edm.RefType> .</span><span class="sxs-lookup"><span data-stu-id="20549-106">Anonymous types that are not defined in the schema explicitly: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType>, and <xref:System.Data.Metadata.Edm.RefType>.</span></span>  
  
 <span data-ttu-id="20549-107">W tej sekcji omówiono typy anonimowe, które nie są zdefiniowane w schemacie jawnie, ale są obsługiwane przez Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="20549-107">This section discusses the anonymous types that are not defined in the schema explicitly but are supported by Entity SQL.</span></span> <span data-ttu-id="20549-108">Aby uzyskać informacje na temat typów pierwotnych i nominalnych, zobacz [koncepcyjne typy modeli (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span><span class="sxs-lookup"><span data-stu-id="20549-108">For information on primitive and nominal types, see [Conceptual Model Types (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span></span>  
  
## <a name="rows"></a><span data-ttu-id="20549-109">Rows (Wiersze)</span><span class="sxs-lookup"><span data-stu-id="20549-109">Rows</span></span>  

 <span data-ttu-id="20549-110">Struktura wiersza zależy od sekwencji wpisanych i nazwanych elementów członkowskich, z których składa się wiersz.</span><span class="sxs-lookup"><span data-stu-id="20549-110">The structure of a row depends on the sequence of typed and named members that the row consists of.</span></span> <span data-ttu-id="20549-111">Typ wiersza nie ma tożsamości i nie można go dziedziczyć.</span><span class="sxs-lookup"><span data-stu-id="20549-111">A row type has no identity and cannot be inherited from.</span></span> <span data-ttu-id="20549-112">Wystąpienia tego samego typu wiersza są równoważne, jeśli elementy członkowskie są odpowiednio równoważne.</span><span class="sxs-lookup"><span data-stu-id="20549-112">Instances of the same row type are equivalent if the members are respectively equivalent.</span></span> <span data-ttu-id="20549-113">Wiersze nie mają zachowania wykraczające poza ich równoważność strukturalną i nie mają odpowiednika w środowisku uruchomieniowym języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="20549-113">Rows have no behavior beyond their structural equivalence and have no equivalent in the common language runtime.</span></span> <span data-ttu-id="20549-114">Zapytania mogą prowadzić do struktur, które zawierają wiersze lub kolekcje wierszy.</span><span class="sxs-lookup"><span data-stu-id="20549-114">Queries can result in structures that contain rows or collections of rows.</span></span> <span data-ttu-id="20549-115">Powiązanie interfejsu API między [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zapytaniami i językiem hosta definiuje sposób zrealizowania wierszy w zapytaniu, które wygenerowało wynik.</span><span class="sxs-lookup"><span data-stu-id="20549-115">The API binding between the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries and the host language defines how rows are realized in the query that produced the result.</span></span> <span data-ttu-id="20549-116">Aby uzyskać informacje na temat sposobu konstruowania wystąpienia wiersza, zobacz [konstruowanie typów](constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="20549-116">For information on how to construct a row instance, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="collections"></a><span data-ttu-id="20549-117">Kolekcje</span><span class="sxs-lookup"><span data-stu-id="20549-117">Collections</span></span>  

 <span data-ttu-id="20549-118">Typy kolekcji reprezentują zero lub więcej wystąpień innych obiektów.</span><span class="sxs-lookup"><span data-stu-id="20549-118">Collection types represent zero or more instances of other objects.</span></span> <span data-ttu-id="20549-119">Aby uzyskać informacje na temat tworzenia kolekcji, zobacz [konstruowanie typów](constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="20549-119">For information on how to construct collection, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="20549-120">Odwołania</span><span class="sxs-lookup"><span data-stu-id="20549-120">References</span></span>  

 <span data-ttu-id="20549-121">Odwołanie jest logicznym wskaźnikiem do określonej jednostki w określonym zestawie jednostek.</span><span class="sxs-lookup"><span data-stu-id="20549-121">A reference is a logical pointer to a specific entity in a specific entity set.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="20549-122">Program obsługuje następujące operatory do konstruowania, dekonstrukcji i nawigowania po odwołaniach:</span><span class="sxs-lookup"><span data-stu-id="20549-122">supports the following operators to construct, deconstruct, and navigate through references:</span></span>  
  
- [<span data-ttu-id="20549-123">UMIESZCZONE</span><span class="sxs-lookup"><span data-stu-id="20549-123">REF</span></span>](ref-entity-sql.md)  
  
- [<span data-ttu-id="20549-124">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="20549-124">CREATEREF</span></span>](createref-entity-sql.md)  
  
- [<span data-ttu-id="20549-125">GŁÓWNYCH</span><span class="sxs-lookup"><span data-stu-id="20549-125">KEY</span></span>](key-entity-sql.md)  
  
- [<span data-ttu-id="20549-126">DEREF</span><span class="sxs-lookup"><span data-stu-id="20549-126">DEREF</span></span>](deref-entity-sql.md)  
  
 <span data-ttu-id="20549-127">Możesz nawigować przez odwołanie za pomocą operatora dostępu do elementu członkowskiego ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="20549-127">You can navigate through a reference by using the member access (dot) operator(`.`).</span></span> <span data-ttu-id="20549-128">Poniższy fragment kodu wyodrębnia Właściwość identyfikatora (Order), przechodząc przez właściwość r (Reference).</span><span class="sxs-lookup"><span data-stu-id="20549-128">The following snippet extracts the Id property (of Order) by navigating through the r (reference) property.</span></span>  
  
```sql  
select o2.r.Id
from (select ref(o) as r from LOB.Orders as o) as o2
```  
  
 <span data-ttu-id="20549-129">Jeśli wartość odwołania jest równa null lub jeśli obiekt docelowy odwołania nie istnieje, wynik ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="20549-129">If the reference value is null, or if the target of the reference does not exist, the result is null.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20549-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="20549-130">See also</span></span>

- [<span data-ttu-id="20549-131">Omówienie jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="20549-131">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="20549-132">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="20549-132">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="20549-133">CAST</span><span class="sxs-lookup"><span data-stu-id="20549-133">CAST</span></span>](cast-entity-sql.md)
- [<span data-ttu-id="20549-134">Specyfikacje CSDL, SSDL i MSL</span><span class="sxs-lookup"><span data-stu-id="20549-134">CSDL, SSDL, and MSL Specifications</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
