---
title: punkt końcowy skojarzenia
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: 00e3a7d855957ae539ea652dc8cde3ed8841dda5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153446"
---
# <a name="association-end"></a><span data-ttu-id="6b8d6-102">punkt końcowy skojarzenia</span><span class="sxs-lookup"><span data-stu-id="6b8d6-102">association end</span></span>

<span data-ttu-id="6b8d6-103">*Punkt końcowy skojarzenia* identyfikuje [Typ jednostki](entity-type.md) na jednym końcu [skojarzenia](association-type.md) i liczbę wystąpień typu jednostki, które mogą istnieć na tym końcu skojarzenia.</span><span class="sxs-lookup"><span data-stu-id="6b8d6-103">An *association end* identifies the [entity type](entity-type.md) on one end of an [association](association-type.md) and the number of entity type instances that can exist at that end of an association.</span></span> <span data-ttu-id="6b8d6-104">Punkty końcowe skojarzenia są zdefiniowane jako część skojarzenia; skojarzenie musi mieć dokładnie dwa punkty końcowe skojarzenia.</span><span class="sxs-lookup"><span data-stu-id="6b8d6-104">Association ends are defined as part of an association; an association must have exactly two association ends.</span></span> <span data-ttu-id="6b8d6-105">[Właściwości nawigacji](navigation-property.md) umożliwiają nawigowanie z jednego skojarzenia do drugiego.</span><span class="sxs-lookup"><span data-stu-id="6b8d6-105">[Navigation properties](navigation-property.md) allow for navigation from one association end to the other.</span></span>  
  
 <span data-ttu-id="6b8d6-106">Definicja końca skojarzenia zawiera następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="6b8d6-106">An association end definition contains the following information:</span></span>  
  
- <span data-ttu-id="6b8d6-107">Jeden z typów jednostek uwzględnionych w skojarzeniu.</span><span class="sxs-lookup"><span data-stu-id="6b8d6-107">One of the entity types involved in the association.</span></span> <span data-ttu-id="6b8d6-108">Potrzeb</span><span class="sxs-lookup"><span data-stu-id="6b8d6-108">(Required)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6b8d6-109">Dla danego skojarzenia typ jednostki określony dla każdego końca skojarzenia może być taki sam.</span><span class="sxs-lookup"><span data-stu-id="6b8d6-109">For a given association, the entity type specified for each association end can be the same.</span></span> <span data-ttu-id="6b8d6-110">Spowoduje to utworzenie własnego skojarzenia.</span><span class="sxs-lookup"><span data-stu-id="6b8d6-110">This creates a self-association.</span></span>  
  
- <span data-ttu-id="6b8d6-111">[Liczebność końcowa skojarzenia](association-end-multiplicity.md) , która wskazuje liczbę wystąpień typu jednostki, które mogą znajdować się na jednym końcu skojarzenia.</span><span class="sxs-lookup"><span data-stu-id="6b8d6-111">An [association end multiplicity](association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="6b8d6-112">Liczebność końcowa skojarzenia może mieć wartość jednego (1), zero lub jeden (0.. 1) lub wiele ( \* ).</span><span class="sxs-lookup"><span data-stu-id="6b8d6-112">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (\*).</span></span>  
  
- <span data-ttu-id="6b8d6-113">Nazwa punktu końcowego skojarzenia.</span><span class="sxs-lookup"><span data-stu-id="6b8d6-113">A name for the association end.</span></span> <span data-ttu-id="6b8d6-114">(opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="6b8d6-114">(Optional)</span></span>  
  
- <span data-ttu-id="6b8d6-115">Informacje o operacjach wykonywanych na końcu skojarzenia, takich jak kaskadowo przy usuwaniu.</span><span class="sxs-lookup"><span data-stu-id="6b8d6-115">Information about operations that are performed on the association end, such as cascade on delete.</span></span> <span data-ttu-id="6b8d6-116">(opcjonalnie)</span><span class="sxs-lookup"><span data-stu-id="6b8d6-116">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b8d6-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="6b8d6-117">Example</span></span>  

 <span data-ttu-id="6b8d6-118">Na poniższym diagramie przedstawiono model koncepcyjny z dwoma skojarzeniami: `PublishedBy` i `WrittenBy` .</span><span class="sxs-lookup"><span data-stu-id="6b8d6-118">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="6b8d6-119">Skojarzenie jest powiązane z `PublishedBy` `Book` `Publisher` typami jednostek i.</span><span class="sxs-lookup"><span data-stu-id="6b8d6-119">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="6b8d6-120">Liczebność `Publisher` końca jest jedną (1), a liczebność `Book` końca ma wiele ( \* ), co oznacza, że Wydawca publikuje wiele książek, a książka jest publikowana przez jednego wydawcę.</span><span class="sxs-lookup"><span data-stu-id="6b8d6-120">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 ![Przykładowy model z trzema typami jednostek](./media/association-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="6b8d6-122">ADO.NET Entity Framework używa języka specyficznego dla domeny (DSL) zwanego językiem definicji schematu koncepcyjnego ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) do definiowania modeli koncepcyjnych.</span><span class="sxs-lookup"><span data-stu-id="6b8d6-122">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="6b8d6-123">Poniżej definiujemy `PublishedBy` skojarzenie pokazane na powyższym diagramie.</span><span class="sxs-lookup"><span data-stu-id="6b8d6-123">The CSDL below defines the `PublishedBy` association shown in the diagram above.</span></span> <span data-ttu-id="6b8d6-124">Należy zauważyć, że typ, nazwa i liczebność każdego końca skojarzenia są określone przez atrybuty XML ( `Type` `Role` `Multiplicity` odpowiednio atrybuty, i).</span><span class="sxs-lookup"><span data-stu-id="6b8d6-124">Note that the type, name, and multiplicity of each association end are specified by XML attributes (the `Type`, `Role`, and `Multiplicity` attributes, respectively).</span></span> <span data-ttu-id="6b8d6-125">Opcjonalne informacje o operacjach wykonywanych na końcu są określone w elemencie XML ( `OnDelete` elementu).</span><span class="sxs-lookup"><span data-stu-id="6b8d6-125">Optional information about operations performed on an end is specified in an XML element (the `OnDelete` element).</span></span> <span data-ttu-id="6b8d6-126">W takim przypadku, jeśli zostanie usunięty Wydawca, wszystkie skojarzone książki.</span><span class="sxs-lookup"><span data-stu-id="6b8d6-126">In this case, if a publisher is deleted, so are all associated books.</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a><span data-ttu-id="6b8d6-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6b8d6-127">See also</span></span>

- [<span data-ttu-id="6b8d6-128">Kluczowe założenia modelu danych jednostki</span><span class="sxs-lookup"><span data-stu-id="6b8d6-128">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="6b8d6-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="6b8d6-129">Entity Data Model</span></span>](entity-data-model.md)
