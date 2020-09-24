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
# <a name="association-end"></a>punkt końcowy skojarzenia

*Punkt końcowy skojarzenia* identyfikuje [Typ jednostki](entity-type.md) na jednym końcu [skojarzenia](association-type.md) i liczbę wystąpień typu jednostki, które mogą istnieć na tym końcu skojarzenia. Punkty końcowe skojarzenia są zdefiniowane jako część skojarzenia; skojarzenie musi mieć dokładnie dwa punkty końcowe skojarzenia. [Właściwości nawigacji](navigation-property.md) umożliwiają nawigowanie z jednego skojarzenia do drugiego.  
  
 Definicja końca skojarzenia zawiera następujące informacje:  
  
- Jeden z typów jednostek uwzględnionych w skojarzeniu. Potrzeb  
  
    > [!NOTE]
    > Dla danego skojarzenia typ jednostki określony dla każdego końca skojarzenia może być taki sam. Spowoduje to utworzenie własnego skojarzenia.  
  
- [Liczebność końcowa skojarzenia](association-end-multiplicity.md) , która wskazuje liczbę wystąpień typu jednostki, które mogą znajdować się na jednym końcu skojarzenia. Liczebność końcowa skojarzenia może mieć wartość jednego (1), zero lub jeden (0.. 1) lub wiele ( \* ).  
  
- Nazwa punktu końcowego skojarzenia. (opcjonalnie)  
  
- Informacje o operacjach wykonywanych na końcu skojarzenia, takich jak kaskadowo przy usuwaniu. (opcjonalnie)  
  
## <a name="example"></a>Przykład  

 Na poniższym diagramie przedstawiono model koncepcyjny z dwoma skojarzeniami: `PublishedBy` i `WrittenBy` . Skojarzenie jest powiązane z `PublishedBy` `Book` `Publisher` typami jednostek i. Liczebność `Publisher` końca jest jedną (1), a liczebność `Book` końca ma wiele ( \* ), co oznacza, że Wydawca publikuje wiele książek, a książka jest publikowana przez jednego wydawcę.  
  
 ![Przykładowy model z trzema typami jednostek](./media/association-end/example-model-three-entity-types.gif)  
  
 ADO.NET Entity Framework używa języka specyficznego dla domeny (DSL) zwanego językiem definicji schematu koncepcyjnego ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) do definiowania modeli koncepcyjnych. Poniżej definiujemy `PublishedBy` skojarzenie pokazane na powyższym diagramie. Należy zauważyć, że typ, nazwa i liczebność każdego końca skojarzenia są określone przez atrybuty XML ( `Type` `Role` `Multiplicity` odpowiednio atrybuty, i). Opcjonalne informacje o operacjach wykonywanych na końcu są określone w elemencie XML ( `OnDelete` elementu). W takim przypadku, jeśli zostanie usunięty Wydawca, wszystkie skojarzone książki.  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a>Zobacz też

- [Kluczowe założenia modelu danych jednostki](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
