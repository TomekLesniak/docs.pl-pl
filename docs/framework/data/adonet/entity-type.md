---
title: typ jednostki
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 3f99667a06d8aa439232802d4909290dfe9db97c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194781"
---
# <a name="entity-type"></a>typ jednostki

*Typ jednostki* jest podstawowym blokiem konstrukcyjnym opisującym strukturę danych z Entity Data Model (EDM). W modelu koncepcyjnym typ jednostki reprezentuje strukturę koncepcji najwyższego poziomu, takich jak klienci lub zamówienia. Typ jednostki to szablon wystąpień typu jednostki. Każdy szablon zawiera następujące informacje:  
  
- Unikatowa nazwa. (Wymagane).  
  
- [Klucz jednostki](entity-key.md) zdefiniowany przez jedną lub więcej właściwości. (Wymagane).  
  
- Dane w postaci [Właściwości](property.md). (opcjonalnie)  
  
- [Właściwości nawigacji](navigation-property.md) , które umożliwiają nawigację z jednego [końca](association-end.md) [skojarzenia](association-type.md) z drugim. (opcjonalnie)  
  
 W aplikacji wystąpienie typu jednostki reprezentuje określony obiekt (na przykład konkretny klient lub zamówienie). Każde wystąpienie typu jednostki musi mieć unikatowy [klucz jednostki](entity-key.md) w ramach [zestawu jednostek](entity-set.md).  
  
 Dwa wystąpienia typu jednostki są uważane za równe tylko wtedy, gdy są one tego samego typu, a wartości ich kluczy jednostek są takie same.  
  
## <a name="example"></a>Przykład  

 Na poniższym diagramie przedstawiono model koncepcyjny z trzema typami jednostek: `Book` , `Publisher` i `Author` :  
  
 ![Przykładowy model z trzema typami jednostek](./media/entity-type/example-model-three-entity-types.gif)  
  
 Należy zauważyć, że właściwości każdego typu jednostki, które tworzą swój klucz jednostki, są oznaczane "(kluczem)".  
  
 [ADO.NET Entity Framework](./ef/index.md) używa języka specyficznego dla domeny (DSL) zwanego językiem definicji schematu koncepcyjnego ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) do definiowania modeli koncepcyjnych. Poniższy obiekt CSDL definiuje `Book` Typ jednostki przedstawiony na poniższym diagramie:  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>Zobacz też

- [Kluczowe założenia modelu danych jednostki](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
- [facet](facet.md)
