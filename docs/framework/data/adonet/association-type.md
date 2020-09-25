---
title: typ skojarzenia
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: 6f6eb91d4f292c7e98b8c9a1d814ed6bf71b7370
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198759"
---
# <a name="association-type"></a>typ skojarzenia

*Typ skojarzenia* (nazywany także skojarzeniem) to podstawowy blok konstrukcyjny do opisywania relacji w Entity Data Model (EDM). W modelu koncepcyjnym skojarzenie reprezentuje relację między dwoma [typami jednostek](entity-type.md) (takimi jak `Customer` i `Order` ). W aplikacji wystąpienie skojarzenia reprezentuje określone skojarzenie (takie jak skojarzenie między wystąpieniem `Customer` i wystąpieniem `Order` ). Wystąpienia skojarzeń są logicznie pogrupowane w [zestawie skojarzenia](association-set.md).  
  
 Definicja skojarzenia zawiera następujące informacje:  
  
- Unikatowa nazwa. Potrzeb  
  
- Dwa [punkty końcowe skojarzenia](association-end.md), jeden dla każdego typu jednostki w relacji. Potrzeb  
  
    > [!NOTE]
    > Skojarzenie nie może reprezentować relacji między więcej niż dwoma typami jednostek. Skojarzenie może jednak definiować samodzielny przez określenie tego samego typu jednostki dla każdego z jego punktów końcowych skojarzenia.  
  
- [Ograniczenie integralności referencyjnej](referential-integrity-constraint.md). (opcjonalnie)  
  
 Każdy punkt końcowy skojarzenia musi określać [liczebność końcową skojarzenia](association-end-multiplicity.md) , która wskazuje liczbę wystąpień typu jednostki, które mogą znajdować się na jednym końcu skojarzenia. Liczebność końcowa skojarzenia może mieć wartość jednego (1), zero lub jeden (0.. 1) lub wiele ( \* ). Do wystąpienia typu jednostki na jednym końcu skojarzenia można uzyskać dostęp za poorednictwem [właściwości nawigacji](navigation-property.md) lub kluczy obcych, jeśli są one uwidocznione w typie jednostki. Aby uzyskać więcej informacji, zobacz [Entity Data Model: klucze obce](foreign-key-property.md).  
  
## <a name="example"></a>Przykład  

 Na poniższym diagramie przedstawiono model koncepcyjny z dwoma skojarzeniami: `PublishedBy` i `WrittenBy` . Skojarzenie jest powiązane z `PublishedBy` `Book` `Publisher` typami jednostek i. Liczebność `Publisher` końca jest jedną (1), a liczebność `Book` końca ma wiele ( \* ), co oznacza, że Wydawca publikuje wiele książek, a książka jest publikowana przez jednego wydawcę.  
  
 ![Przykładowy model z trzema typami jednostek](./media/association-type/example-model-three-entity-types.gif)  
  
 [ADO.NET Entity Framework](./ef/index.md) używa języka specyficznego dla domeny (DSL) zwanego językiem definicji schematu koncepcyjnego ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) do definiowania modeli koncepcyjnych. Poniższy obiekt CSDL definiuje `PublishedBy` skojarzenie pokazane na powyższym diagramie:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Zobacz też

- [Kluczowe założenia modelu danych jednostki](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
