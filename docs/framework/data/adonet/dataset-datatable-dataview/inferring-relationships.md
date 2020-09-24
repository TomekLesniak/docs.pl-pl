---
title: Wnioskowanie relacji
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: ee691eee95c34afdb6374cdd7448d4b44ece3055
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177569"
---
# <a name="inferring-relationships"></a><span data-ttu-id="10add-102">Wnioskowanie relacji</span><span class="sxs-lookup"><span data-stu-id="10add-102">Inferring Relationships</span></span>

<span data-ttu-id="10add-103">Jeśli element, który jest wywnioskowany jako tabela, ma element podrzędny, który jest również wywnioskowany jako tabela, <xref:System.Data.DataRelation> zostanie utworzony między dwiema tabelami.</span><span class="sxs-lookup"><span data-stu-id="10add-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="10add-104">Nowa kolumna o nazwie **ParentTableName_Id** zostanie dodana do tabeli utworzonej dla elementu nadrzędnego, a tabela utworzona dla elementu podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="10add-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="10add-105">Właściwość **ColumnMapping** tej kolumny tożsamości zostanie ustawiona na wartość **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="10add-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="10add-106">Kolumna będzie przerastać klucz podstawowy dla tabeli nadrzędnej i będzie używana dla **relacji** między tymi dwiema tabelami.</span><span class="sxs-lookup"><span data-stu-id="10add-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="10add-107">Typem danych kolumny dodanej tożsamości będzie **System. Int32**, w przeciwieństwie do typu danych wszystkich innych wywnioskowanych kolumn, które jest **System. String**.</span><span class="sxs-lookup"><span data-stu-id="10add-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="10add-108">Element <xref:System.Data.ForeignKeyConstraint> with **DeleteRule**  =  **Cascade** również zostanie utworzony przy użyciu nowej kolumny w tabeli nadrzędnej i podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="10add-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="10add-109">Rozważmy na przykład następujący kod XML:</span><span class="sxs-lookup"><span data-stu-id="10add-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="10add-110">Proces wnioskowania spowoduje utworzenie dwóch tabel: **element1** i **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="10add-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="10add-111">Tabela **element1** będzie miała dwie kolumny: **Element1_Id** i **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="10add-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="10add-112">Właściwość **ColumnMapping** kolumny **Element1_Id** zostanie ustawiona na wartość **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="10add-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="10add-113">Właściwość **ColumnMapping** kolumny **ChildElement2** zostanie ustawiona na wartość **MappingType. element**.</span><span class="sxs-lookup"><span data-stu-id="10add-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="10add-114">Kolumna **Element1_Id** zostanie ustawiona jako klucz podstawowy tabeli **element1** .</span><span class="sxs-lookup"><span data-stu-id="10add-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="10add-115">Tabela **ChildElement1** będzie miała trzy kolumny: **attr1**, **attr2** i **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="10add-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="10add-116">Właściwość **ColumnMapping** dla kolumn **attr1** i **Attr2** zostanie ustawiona na wartość **MappingType. Attribute**.</span><span class="sxs-lookup"><span data-stu-id="10add-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="10add-117">Właściwość **ColumnMapping** kolumny **Element1_Id** zostanie ustawiona na wartość **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="10add-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="10add-118">**Relacja** i **element ForeignKeyConstraint** zostanie utworzona przy użyciu kolumn **Element1_Id** z obu tabel.</span><span class="sxs-lookup"><span data-stu-id="10add-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="10add-119">**Zestaw danych:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="10add-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="10add-120">**Tabela:** Element1</span><span class="sxs-lookup"><span data-stu-id="10add-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="10add-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="10add-121">Element1_Id</span></span>|<span data-ttu-id="10add-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="10add-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="10add-123">0</span><span class="sxs-lookup"><span data-stu-id="10add-123">0</span></span>|<span data-ttu-id="10add-124">Text2</span><span class="sxs-lookup"><span data-stu-id="10add-124">Text2</span></span>|  
  
 <span data-ttu-id="10add-125">**Tabela:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="10add-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="10add-126">attr1</span><span class="sxs-lookup"><span data-stu-id="10add-126">attr1</span></span>|<span data-ttu-id="10add-127">attr2</span><span class="sxs-lookup"><span data-stu-id="10add-127">attr2</span></span>|<span data-ttu-id="10add-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="10add-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="10add-129">sekwencj</span><span class="sxs-lookup"><span data-stu-id="10add-129">value1</span></span>|<span data-ttu-id="10add-130">wartość2</span><span class="sxs-lookup"><span data-stu-id="10add-130">value2</span></span>|<span data-ttu-id="10add-131">0</span><span class="sxs-lookup"><span data-stu-id="10add-131">0</span></span>|  
  
 <span data-ttu-id="10add-132">**Relacja** : Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="10add-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="10add-133">**Element nadrzędny:** Element1</span><span class="sxs-lookup"><span data-stu-id="10add-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="10add-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="10add-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="10add-135">**Elementy podrzędne:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="10add-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="10add-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="10add-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="10add-137">**Zagnieżdżone:** Oznacza</span><span class="sxs-lookup"><span data-stu-id="10add-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="10add-138">**Element ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="10add-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="10add-139">**Kolumna:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="10add-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="10add-140">**Element nadrzędny:** Element1</span><span class="sxs-lookup"><span data-stu-id="10add-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="10add-141">**Elementy podrzędne:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="10add-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="10add-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="10add-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="10add-143">**AcceptRejectRule:** Dawaj</span><span class="sxs-lookup"><span data-stu-id="10add-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10add-144">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="10add-144">See also</span></span>

- [<span data-ttu-id="10add-145">Wnioskowanie relacyjnej struktury elementu DataSet z pliku XML</span><span class="sxs-lookup"><span data-stu-id="10add-145">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="10add-146">Ładowanie elementu DataSet z pliku XML</span><span class="sxs-lookup"><span data-stu-id="10add-146">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="10add-147">Ładowanie informacji o schemacie elementu DataSet z pliku XML</span><span class="sxs-lookup"><span data-stu-id="10add-147">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="10add-148">Zagnieżdżanie elementów DataRelation</span><span class="sxs-lookup"><span data-stu-id="10add-148">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="10add-149">Używanie języka XML w elemencie DataSet</span><span class="sxs-lookup"><span data-stu-id="10add-149">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="10add-150">Elementy DataSet, DataTable i DataView</span><span class="sxs-lookup"><span data-stu-id="10add-150">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="10add-151">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="10add-151">ADO.NET Overview</span></span>](../ado-net-overview.md)
