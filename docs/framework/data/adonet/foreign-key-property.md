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
# <a name="foreign-key-property"></a>właściwość klucza obcego

*Właściwość klucza obcego* w Entity Data Model (EDM) jest [właściwością](property.md) typu pierwotnego (lub zestawem właściwości typu pierwotnego) dla [typu jednostki](entity-type.md) , który zawiera [klucz jednostki](entity-key.md) innego typu jednostki.  
  
 Właściwość klucza obcego jest analogiczna do kolumny klucza obcego w relacyjnej bazie danych. W taki sam sposób, w jaki kolumny klucza obcego są używane w relacyjnej bazie danych do tworzenia relacji między wierszami w tabelach, właściwości klucza obcego w modelu koncepcyjnym są używane do ustanawiania [skojarzeń](association-type.md) między typami jednostek. [Ograniczenie integralności referencyjnej](referential-integrity-constraint.md) służy do definiowania skojarzenia między dwoma typami jednostek, gdy jeden z typów ma właściwość klucza obcego.  
  
## <a name="example"></a>Przykład  

 Na poniższym diagramie przedstawiono model koncepcyjny z trzema typami jednostek: `Book` , `Publisher` i `Author` . `Book`Typ jednostki ma właściwość, `PublisherId` która odwołuje się do klucza jednostki `Publisher` typu jednostki podczas definiowania ograniczenia integralności referencyjnej w `PublishedBy` skojarzeniu.  
  
 ![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Przykład modelu ograniczeń referencyjnych")  
  
 [ADO.NET Entity Framework](./ef/index.md) używa języka specyficznego dla domeny (DSL) zwanego językiem definicji schematu koncepcyjnego ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) do definiowania modeli koncepcyjnych. Poniższy CSDL używa właściwości klucza obcego `PublisherId` do zdefiniowania ograniczenia integralności referencyjnej na skojarzeniu pokazanym `PublishedBy` powyżej.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>Zobacz też

- [Kluczowe założenia modelu danych jednostki](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
