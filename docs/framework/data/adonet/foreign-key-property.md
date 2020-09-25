---
title: właściwość klucza obcego
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: be0fcb94b0b457a33c17e7125cd22db50f298cc6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189321"
---
# <a name="foreign-key-property"></a><span data-ttu-id="54414-102">właściwość klucza obcego</span><span class="sxs-lookup"><span data-stu-id="54414-102">foreign key property</span></span>

<span data-ttu-id="54414-103">*Właściwość klucza obcego* w Entity Data Model (EDM) jest [właściwością](property.md) typu pierwotnego (lub zestawem właściwości typu pierwotnego) dla [typu jednostki](entity-type.md) , który zawiera [klucz jednostki](entity-key.md) innego typu jednostki.</span><span class="sxs-lookup"><span data-stu-id="54414-103">A *foreign key property* in the Entity Data Model (EDM) is a primitive type [property](property.md) (or a set of primitive type properties) on an [entity type](entity-type.md) that contains the [entity key](entity-key.md) of another entity type.</span></span>  
  
 <span data-ttu-id="54414-104">Właściwość klucza obcego jest analogiczna do kolumny klucza obcego w relacyjnej bazie danych.</span><span class="sxs-lookup"><span data-stu-id="54414-104">A foreign key property is analogous to a foreign key column in a relational database.</span></span> <span data-ttu-id="54414-105">W taki sam sposób, w jaki kolumny klucza obcego są używane w relacyjnej bazie danych do tworzenia relacji między wierszami w tabelach, właściwości klucza obcego w modelu koncepcyjnym są używane do ustanawiania [skojarzeń](association-type.md) między typami jednostek.</span><span class="sxs-lookup"><span data-stu-id="54414-105">In the same way that foreign key columns are used in a relational database to create relationships between rows in tables, foreign key properties in a conceptual model are used to establish [associations](association-type.md) between entity types.</span></span> <span data-ttu-id="54414-106">[Ograniczenie integralności referencyjnej](referential-integrity-constraint.md) służy do definiowania skojarzenia między dwoma typami jednostek, gdy jeden z typów ma właściwość klucza obcego.</span><span class="sxs-lookup"><span data-stu-id="54414-106">A [referential integrity constraint](referential-integrity-constraint.md) is used to define an association between two entity types when one of the types has a foreign key property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54414-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="54414-107">Example</span></span>  

 <span data-ttu-id="54414-108">Na poniższym diagramie przedstawiono model koncepcyjny z trzema typami jednostek: `Book` , `Publisher` i `Author` .</span><span class="sxs-lookup"><span data-stu-id="54414-108">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="54414-109">`Book`Typ jednostki ma właściwość, `PublisherId` która odwołuje się do klucza jednostki `Publisher` typu jednostki podczas definiowania ograniczenia integralności referencyjnej w `PublishedBy` skojarzeniu.</span><span class="sxs-lookup"><span data-stu-id="54414-109">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="54414-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Przykład modelu ograniczeń referencyjnych")</span><span class="sxs-lookup"><span data-stu-id="54414-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="54414-111">[ADO.NET Entity Framework](./ef/index.md) używa języka specyficznego dla domeny (DSL) zwanego językiem definicji schematu koncepcyjnego ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) do definiowania modeli koncepcyjnych.</span><span class="sxs-lookup"><span data-stu-id="54414-111">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="54414-112">Poniższy CSDL używa właściwości klucza obcego `PublisherId` do zdefiniowania ograniczenia integralności referencyjnej na skojarzeniu pokazanym `PublishedBy` powyżej.</span><span class="sxs-lookup"><span data-stu-id="54414-112">The following CSDL uses the foreign key property `PublisherId` to define a referential integrity constraint on the `PublishedBy` association shown in the conceptual model shown above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="54414-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="54414-113">See also</span></span>

- [<span data-ttu-id="54414-114">Kluczowe założenia modelu danych jednostki</span><span class="sxs-lookup"><span data-stu-id="54414-114">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="54414-115">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="54414-115">Entity Data Model</span></span>](entity-data-model.md)
