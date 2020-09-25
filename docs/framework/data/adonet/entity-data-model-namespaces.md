---
title: 'Model danych jednostki: Namespaces'
ms.date: 03/30/2017
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
ms.openlocfilehash: 1e5f9527ec208c5650c68fe35bb758e0850b7700
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194833"
---
# <a name="entity-data-model-namespaces"></a>Model danych jednostki: Namespaces

Przestrzeń nazw w Entity Data Model (EDM) jest kontenerem abstrakcyjnym dla [typów jednostek](entity-type.md), [typów złożonych](complex-type.md)i [skojarzeń](association-type.md). Przestrzenie nazw w modelu EDM są podobne do przestrzeni nazw w języku programowania: zawierają kontekst dla obiektów, które zawierają i umożliwiają rozróżnianie obiektów, które mają taką samą nazwę (ale znajdują się w różnych obszarach nazw).  
  
## <a name="example"></a>Przykład  

 [ADO.NET Entity Framework](./ef/index.md) używa języka specyficznego dla domeny (DSL) zwanego językiem definicji schematu koncepcyjnego ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) do definiowania modeli koncepcyjnych. Poniższy kod CSDL używa przestrzeni nazw do identyfikowania typu, który jest zdefiniowany w innym modelu koncepcyjnym. W przykładzie zdefiniowano typ jednostki ( `Publisher` ), który ma właściwość typu złożonego ( `Address` ), która jest importowana z `ExtendedBooksModel` przestrzeni nazw. Należy zauważyć, że `Using` element wskazuje, że przestrzeń nazw została zaimportowana. Należy również zauważyć, że typ `Address` właściwości jest zdefiniowany przy użyciu jego w pełni kwalifikowanej nazwy ( `ExtendedBooksModel.Address` ), co oznacza, że ten typ jest zdefiniowany w `ExtendedBooksModel` przestrzeni nazw.  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a>Zobacz też

- [Kluczowe założenia modelu danych jednostki](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
