---
title: 'Model danych jednostki: Dziedziczenie'
ms.date: 03/30/2017
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
ms.openlocfilehash: 057040eee411988c46adc9c4cabcfe5f5a185e1b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175463"
---
# <a name="entity-data-model-inheritance"></a>Model danych jednostki: Dziedziczenie

Entity Data Model (EDM) obsługuje dziedziczenie dla [typów jednostek](entity-type.md). Dziedziczenie w modelu EDM jest podobne do dziedziczenia klas w językach programowania zorientowanego obiektowo. Podobnie jak w przypadku klas w językach zorientowanych obiektowo, w modelu koncepcyjnym można zdefiniować typ jednostki ( *Typ pochodny*), który dziedziczy z innego typu jednostki ( *Typ podstawowy*). Jednak w przeciwieństwie do klas w programowaniu zorientowanym na obiektach, w modelu koncepcyjnym typ pochodny zawsze dziedziczy wszystkie [Właściwości](property.md) i [właściwości nawigacji](navigation-property.md) typu podstawowego. Nie można przesłonić dziedziczonych właściwości w typie pochodnym.  
  
 W modelu koncepcyjnym można tworzyć hierarchie dziedziczenia, w których typ pochodny dziedziczy z innego typu pochodnego. Typ w górnej części hierarchii (jeden typ w hierarchii, która nie jest typem pochodnym) jest nazywany *typem głównym*. W hierarchii dziedziczenia [klucz jednostki](entity-key.md) musi być zdefiniowany w typie głównym.  
  
 Nie można skompilować hierarchii dziedziczenia, w których typ pochodny dziedziczy z więcej niż jednego typu. Na przykład w modelu koncepcyjnym z `Book` typem jednostki można zdefiniować typy pochodne `FictionBook` i `NonFictionBook` każdy z nich dziedziczy `Book` . Nie można jednak zdefiniować typu, który dziedziczy z obu `FictionBook` `NonFictionBook` typów i.  
  
## <a name="example"></a>Przykład  

Na poniższym diagramie przedstawiono model koncepcyjny z czterema typami jednostek: `Book` , `FictionBook` , `Publisher` , i `Author` . `FictionBook`Typ jednostki jest typem pochodnym, który dziedziczy z `Book` typu jednostki. `FictionBook`Typ dziedziczy `ISBN (Key)` `Title` właściwości,, i `Revision` i definiuje dodatkową właściwość o nazwie `Genre` .  
  
 ![Diagram przedstawiający model koncepcyjny z czterema typami jednostek.](./media/entity-data-model-inheritance/entity-type-inheritance.gif)  
  
 [ADO.NET Entity Framework](./ef/index.md) używa języka specyficznego dla domeny (DSL) zwanego językiem definicji schematu koncepcyjnego ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) do definiowania modeli koncepcyjnych. Poniższy identyfikator CSDL definiuje typ jednostki, `FictionBook` który dziedziczy z `Book` typu (jak na diagramie powyżej):  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## <a name="see-also"></a>Zobacz też

- [Kluczowe założenia modelu danych jednostki](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
