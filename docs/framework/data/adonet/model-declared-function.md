---
title: funkcja zadeklarowana modelu
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: fb30dd86c29d6a7fff6f2c71d5fd892326e1fda4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147856"
---
# <a name="model-declared-function"></a>funkcja zadeklarowana modelu

*Funkcja zadeklarowana przez model* to funkcja zadeklarowana w modelu koncepcyjnym, ale nie jest zdefiniowana w tym modelu koncepcyjnym. Funkcja może być zdefiniowana w środowisku hostingu lub magazynu. Na przykład funkcja zadeklarowana przez model może zostać zmapowana do funkcji, która jest zdefiniowana w bazie danych, dzięki czemu udostępnia funkcje po stronie serwera w modelu koncepcyjnym.  
  
 Deklaracja funkcji zadeklarowanej przez model zawiera następujące informacje:  
  
- Nazwa funkcji. Potrzeb  
  
- Typ wartości zwracanej. (opcjonalnie)  
  
    > [!NOTE]
    > Jeśli nie określono wartości zwracanej, zwracany typ to void.  
  
- Informacje o parametrach, w tym nazwa parametru i typ. (opcjonalnie)  
  
## <a name="example"></a>Przykład  

 [ADO.NET Entity Framework](./ef/index.md) używa języka specyficznego dla domeny (DSL) zwanego językiem definicji schematu koncepcyjnego ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) do definiowania modeli koncepcyjnych. W obszarze CSDL jedna implementacja funkcji zadeklarowanej przez model jest importem funkcji (przy użyciu [elementu FunctionImport](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)). Poniższy plik CSDL definiuje kontener jednostek z definicją importu funkcji. Zwróć uwagę, że zwracany typ dla funkcji to void, ponieważ nie określono typu zwracanego.  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a>Zobacz też

- [Kluczowe założenia modelu danych jednostki](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
