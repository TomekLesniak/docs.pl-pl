---
title: 'Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu'
ms.date: 03/30/2017
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
ms.openlocfilehash: 5e61acc9de1ef2f00d5e81a3c3080a9dc46f074d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147700"
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="52f16-102">Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu</span><span class="sxs-lookup"><span data-stu-id="52f16-102">How to: Customize Entity Classes by Using the Code Editor</span></span>

<span data-ttu-id="52f16-103">Deweloperzy korzystający z programu Visual Studio mogą używać Object Relational Designer do tworzenia lub dostosowywania ich klas jednostek.</span><span class="sxs-lookup"><span data-stu-id="52f16-103">Developers using Visual Studio can use the Object Relational Designer to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="52f16-104">Możesz również użyć edytora kodu programu Visual Studio, aby napisać własny kod mapowania lub dostosować kod, który został już wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="52f16-104">You can also use the Visual Studio code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="52f16-105">Aby uzyskać więcej informacji, zobacz [Mapowanie oparte na atrybutach](attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="52f16-105">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="52f16-106">W tematach w tej sekcji opisano sposób dostosowywania modelu obiektów.</span><span class="sxs-lookup"><span data-stu-id="52f16-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="52f16-107">Instrukcje: Określanie nazw bazy danych</span><span class="sxs-lookup"><span data-stu-id="52f16-107">How to: Specify Database Names</span></span>](how-to-specify-database-names.md)  
 <span data-ttu-id="52f16-108">Opisuje sposób użycia programu <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> .</span><span class="sxs-lookup"><span data-stu-id="52f16-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="52f16-109">Instrukcje: Reprezentacja tabel jako klas</span><span class="sxs-lookup"><span data-stu-id="52f16-109">How to: Represent Tables as Classes</span></span>](how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="52f16-110">Opisuje sposób użycia programu <xref:System.Data.Linq.Mapping.TableAttribute> .</span><span class="sxs-lookup"><span data-stu-id="52f16-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="52f16-111">Instrukcje: Reprezentacja kolumn jako elementów członkowskich klas</span><span class="sxs-lookup"><span data-stu-id="52f16-111">How to: Represent Columns as Class Members</span></span>](how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="52f16-112">Opisuje sposób użycia programu <xref:System.Data.Linq.Mapping.ColumnAttribute> .</span><span class="sxs-lookup"><span data-stu-id="52f16-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="52f16-113">Instrukcje: Reprezentacja kluczy podstawowych</span><span class="sxs-lookup"><span data-stu-id="52f16-113">How to: Represent Primary Keys</span></span>](how-to-represent-primary-keys.md)  
 <span data-ttu-id="52f16-114">Opisuje sposób użycia programu <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> .</span><span class="sxs-lookup"><span data-stu-id="52f16-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="52f16-115">Instrukcje: Mapowanie relacji w bazie danych</span><span class="sxs-lookup"><span data-stu-id="52f16-115">How to: Map Database Relationships</span></span>](how-to-map-database-relationships.md)  
 <span data-ttu-id="52f16-116">Zawiera przykłady użycia <xref:System.Data.Linq.Mapping.AssociationAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="52f16-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="52f16-117">Instrukcje: Reprezentacja kolumn jako wygenerowanych w bazie danych</span><span class="sxs-lookup"><span data-stu-id="52f16-117">How to: Represent Columns as Database-Generated</span></span>](how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="52f16-118">Opisuje sposób użycia programu <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> .</span><span class="sxs-lookup"><span data-stu-id="52f16-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="52f16-119">Instrukcje: Reprezentacja kolumn jako kolumn znacznika czasu lub wersji</span><span class="sxs-lookup"><span data-stu-id="52f16-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="52f16-120">Opisuje sposób użycia programu <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> .</span><span class="sxs-lookup"><span data-stu-id="52f16-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="52f16-121">Instrukcje: Określanie typów danych bazy danych</span><span class="sxs-lookup"><span data-stu-id="52f16-121">How to: Specify Database Data Types</span></span>](how-to-specify-database-data-types.md)  
 <span data-ttu-id="52f16-122">Opisuje sposób użycia programu <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> .</span><span class="sxs-lookup"><span data-stu-id="52f16-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="52f16-123">Instrukcje: Reprezentacja kolumn obliczanych</span><span class="sxs-lookup"><span data-stu-id="52f16-123">How to: Represent Computed Columns</span></span>](how-to-represent-computed-columns.md)  
 <span data-ttu-id="52f16-124">Opisuje sposób użycia programu <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> .</span><span class="sxs-lookup"><span data-stu-id="52f16-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="52f16-125">Instrukcje: Określanie pól magazynu prywatnego</span><span class="sxs-lookup"><span data-stu-id="52f16-125">How to: Specify Private Storage Fields</span></span>](how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="52f16-126">Opisuje sposób użycia programu <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> .</span><span class="sxs-lookup"><span data-stu-id="52f16-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="52f16-127">Instrukcje: Reprezentacja kolumn jako dopuszczających wartości Null</span><span class="sxs-lookup"><span data-stu-id="52f16-127">How to: Represent Columns as Allowing Null Values</span></span>](how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="52f16-128">Opisuje sposób użycia programu <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> .</span><span class="sxs-lookup"><span data-stu-id="52f16-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="52f16-129">Instrukcje: Mapowanie hierarchii dziedziczenia</span><span class="sxs-lookup"><span data-stu-id="52f16-129">How to: Map Inheritance Hierarchies</span></span>](how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="52f16-130">Opisuje mapowania wymagane do określenia hierarchii dziedziczenia.</span><span class="sxs-lookup"><span data-stu-id="52f16-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="52f16-131">Instrukcje: Określanie sprawdzania konfliktów współbieżności</span><span class="sxs-lookup"><span data-stu-id="52f16-131">How to: Specify Concurrency-Conflict Checking</span></span>](how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="52f16-132">Opisuje sposób użycia programu <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> .</span><span class="sxs-lookup"><span data-stu-id="52f16-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52f16-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="52f16-133">See also</span></span>

- [<span data-ttu-id="52f16-134">SqlMetal.exe (Narzędzie generowania kodu)</span><span class="sxs-lookup"><span data-stu-id="52f16-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
