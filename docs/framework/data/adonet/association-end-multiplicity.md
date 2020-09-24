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
# <a name="association-end-multiplicity"></a>skojarzenie i liczebność

*Liczebność końcowa skojarzenia* definiuje liczbę wystąpień [typu jednostki](entity-type.md) , które mogą być na jednym końcu [skojarzenia](association-type.md).  
  
 Liczebność końcowa skojarzenia może mieć jedną z następujących wartości:  
  
- jeden (1): wskazuje, że dokładnie jedno wystąpienie typu jednostki istnieje na końcu skojarzenia.  
  
- zero lub jeden (0.. 1): wskazuje, że na końcu skojarzenia istnieją wystąpienia typu jednostki równe zero lub jeden.  
  
- wiele ( \* ): wskazuje, że na końcu skojarzenia istnieje zero, jedno lub więcej wystąpień typu jednostki.  
  
 Skojarzenie jest często scharakteryzowane przez jego liczebność końcową skojarzenia. Na przykład, jeśli koniec skojarzenia ma liczebność jeden (1) i wiele ( \* ), skojarzenie nazywa się skojarzeniem "jeden do wielu". W poniższym przykładzie `PublishedBy` skojarzenie jest skojarzeniem jeden-do-wielu (Wydawca publikuje wiele książek, a książka jest publikowana przez jednego wydawcę). `WrittenBy`Skojarzenie jest skojarzeniem wiele-do-wielu (książka może mieć wielu autorów i autor może zapisywać wiele książek).  
  
## <a name="example"></a>Przykład  

 Na poniższym diagramie przedstawiono model koncepcyjny z dwoma skojarzeniami: `PublishedBy` i `WrittenBy` . Skojarzenie jest powiązane z `PublishedBy` `Book` `Publisher` typami jednostek i. Liczebność `Publisher` końca jest jedną (1), a liczebność `Book` końca ma wiele ( \* ).  
  
 ![Przykładowy model z trzema typami jednostek](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 ADO.NET Entity Framework używa języka specyficznego dla domeny (DSL) zwanego językiem definicji schematu koncepcyjnego ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) do definiowania modeli koncepcyjnych. Poniższy obiekt CSDL definiuje `PublishedBy` skojarzenie pokazane na powyższym diagramie:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Zobacz też

- [Kluczowe założenia modelu danych jednostki](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
