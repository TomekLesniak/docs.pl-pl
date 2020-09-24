---
title: skojarzenie i liczebność
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: cf9e6b5af0dc6a33af364901c631b4ce66fe0480
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153511"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="f9c9c-102">skojarzenie i liczebność</span><span class="sxs-lookup"><span data-stu-id="f9c9c-102">association end multiplicity</span></span>

<span data-ttu-id="f9c9c-103">*Liczebność końcowa skojarzenia* definiuje liczbę wystąpień [typu jednostki](entity-type.md) , które mogą być na jednym końcu [skojarzenia](association-type.md).</span><span class="sxs-lookup"><span data-stu-id="f9c9c-103">*Association end multiplicity* defines the number of [entity type](entity-type.md) instances that can be at one end of an [association](association-type.md).</span></span>  
  
 <span data-ttu-id="f9c9c-104">Liczebność końcowa skojarzenia może mieć jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="f9c9c-104">An association end multiplicity can have one of the following values:</span></span>  
  
- <span data-ttu-id="f9c9c-105">jeden (1): wskazuje, że dokładnie jedno wystąpienie typu jednostki istnieje na końcu skojarzenia.</span><span class="sxs-lookup"><span data-stu-id="f9c9c-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
- <span data-ttu-id="f9c9c-106">zero lub jeden (0.. 1): wskazuje, że na końcu skojarzenia istnieją wystąpienia typu jednostki równe zero lub jeden.</span><span class="sxs-lookup"><span data-stu-id="f9c9c-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
- <span data-ttu-id="f9c9c-107">wiele ( \* ): wskazuje, że na końcu skojarzenia istnieje zero, jedno lub więcej wystąpień typu jednostki.</span><span class="sxs-lookup"><span data-stu-id="f9c9c-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="f9c9c-108">Skojarzenie jest często scharakteryzowane przez jego liczebność końcową skojarzenia.</span><span class="sxs-lookup"><span data-stu-id="f9c9c-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="f9c9c-109">Na przykład, jeśli koniec skojarzenia ma liczebność jeden (1) i wiele ( \* ), skojarzenie nazywa się skojarzeniem "jeden do wielu".</span><span class="sxs-lookup"><span data-stu-id="f9c9c-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="f9c9c-110">W poniższym przykładzie `PublishedBy` skojarzenie jest skojarzeniem jeden-do-wielu (Wydawca publikuje wiele książek, a książka jest publikowana przez jednego wydawcę).</span><span class="sxs-lookup"><span data-stu-id="f9c9c-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="f9c9c-111">`WrittenBy`Skojarzenie jest skojarzeniem wiele-do-wielu (książka może mieć wielu autorów i autor może zapisywać wiele książek).</span><span class="sxs-lookup"><span data-stu-id="f9c9c-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9c9c-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="f9c9c-112">Example</span></span>  

 <span data-ttu-id="f9c9c-113">Na poniższym diagramie przedstawiono model koncepcyjny z dwoma skojarzeniami: `PublishedBy` i `WrittenBy` .</span><span class="sxs-lookup"><span data-stu-id="f9c9c-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="f9c9c-114">Skojarzenie jest powiązane z `PublishedBy` `Book` `Publisher` typami jednostek i.</span><span class="sxs-lookup"><span data-stu-id="f9c9c-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="f9c9c-115">Liczebność `Publisher` końca jest jedną (1), a liczebność `Book` końca ma wiele ( \* ).</span><span class="sxs-lookup"><span data-stu-id="f9c9c-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 ![Przykładowy model z trzema typami jednostek](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="f9c9c-117">ADO.NET Entity Framework używa języka specyficznego dla domeny (DSL) zwanego językiem definicji schematu koncepcyjnego ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) do definiowania modeli koncepcyjnych.</span><span class="sxs-lookup"><span data-stu-id="f9c9c-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="f9c9c-118">Poniższy obiekt CSDL definiuje `PublishedBy` skojarzenie pokazane na powyższym diagramie:</span><span class="sxs-lookup"><span data-stu-id="f9c9c-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="f9c9c-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f9c9c-119">See also</span></span>

- [<span data-ttu-id="f9c9c-120">Kluczowe założenia modelu danych jednostki</span><span class="sxs-lookup"><span data-stu-id="f9c9c-120">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="f9c9c-121">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="f9c9c-121">Entity Data Model</span></span>](entity-data-model.md)
