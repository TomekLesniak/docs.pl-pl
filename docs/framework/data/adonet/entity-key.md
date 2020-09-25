---
title: klucz jednostki
ms.date: 03/30/2017
ms.assetid: 0d447a6d-fa7a-4db0-8e7a-fd45e385fca0
ms.openlocfilehash: b2692faf2f8bea27c8a5d6cdc52689ca186d3194
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200787"
---
# <a name="entity-key"></a>klucz jednostki

*Klucz jednostki* jest [właściwością](property.md) lub zestawem właściwości [typu jednostki](entity-type.md) , które są używane do określania tożsamości. Właściwości tworzące klucz jednostki są wybierane w czasie projektowania. Wartości właściwości klucza jednostki muszą jednoznacznie identyfikować wystąpienie typu jednostki w ramach [zestawu jednostek](entity-set.md) w czasie wykonywania. Właściwości tworzące klucz jednostki powinny być wybierane w celu zagwarantowania unikatowej wartości wystąpień w zestawie jednostek.  
  
 Poniżej przedstawiono wymagania dotyczące zestawu właściwości jako klucza jednostki:  
  
- Nie mogą być identyczne dwa klucze jednostek w ramach zestawu jednostek. Oznacza to, że dla wszystkich dwóch jednostek w ramach zestawu jednostek wartości dla wszystkich właściwości, które stanowią klucz, nie mogą być takie same. Jednak niektóre (ale nie wszystkie) wartości, które składają się na klucz jednostki, mogą być takie same.  
  
- Klucz jednostki musi składać się z zestawu właściwości niedopuszczających wartości null, niezmiennego [typu podstawowego](entity-data-model-primitive-data-types.md).  
  
- Nie można zmienić właściwości, które składają się na klucz jednostki dla danego typu jednostki. Nie można zezwolić na więcej niż jeden możliwy klucz jednostki dla danego typu jednostki; klucze zastępcze nie są obsługiwane.  
  
- Gdy jednostka jest uwzględniona w hierarchii dziedziczenia, jednostka główna musi zawierać wszystkie właściwości tworzące klucz jednostki, a klucz jednostki musi być zdefiniowany w typie jednostki głównej. Aby uzyskać więcej informacji, zobacz [Entity Data Model: dziedziczenie](entity-data-model-inheritance.md).  
  
## <a name="example"></a>Przykład  

 Na poniższym diagramie przedstawiono model koncepcyjny z trzema typami jednostek: `Book` , `Publisher` i `Author` . Właściwości każdego typu jednostki, który tworzą swój klucz jednostki, są oznaczane "(kluczem)". Należy zauważyć, że `Author` Typ jednostki ma klucz jednostki składający się z dwóch właściwości, `Name` i `Address` .  
  
 ![Przykładowy model z trzema typami jednostek](./media/entity-key/example-model-three-entity-types.gif)  
  
 [ADO.NET Entity Framework](./ef/index.md) używa języka specyficznego dla domeny (DSL) zwanego językiem definicji schematu koncepcyjnego ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) do definiowania modeli koncepcyjnych. W obszarze CSDL poniżej zdefiniowano `Book` Typ jednostki przedstawiony na powyższym diagramie. Należy pamiętać, że klucz jednostki jest definiowany przez odwołanie się do `ISBN` właściwości typu jednostki.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 `ISBN`Właściwość jest dobrym wyborem dla klucza jednostki, ponieważ międzynarodowy numer książki standardowej (ISBN) jednoznacznie identyfikuje książkę.  
  
 W obszarze CSDL poniżej zdefiniowano `Author` Typ jednostki przedstawiony na powyższym diagramie. Należy zauważyć, że klucz jednostki składa się z dwóch właściwości, `Name` i `Address` .  
  
 [!code-xml[EDM_Example_Model#CompositeKeyExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#compositekeyexample)]  
  
 Korzystanie z `Name` i `Address` dla klucza jednostki jest rozsądnie możliwe, ponieważ dwa autorów o tej samej nazwie jest mało prawdopodobne, aby na tym samym adresie były wyświetlane. Jednak wybór dla klucza jednostki nie gwarantuje jednowzględnie unikatowych kluczy jednostki w zestawie jednostek. `AuthorId`W takim przypadku zaleca się dodanie właściwości, takiej jak, która może zostać użyta do unikatowej identyfikacji autora.  
  
## <a name="see-also"></a>Zobacz też

- [Kluczowe założenia modelu danych jednostki](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
