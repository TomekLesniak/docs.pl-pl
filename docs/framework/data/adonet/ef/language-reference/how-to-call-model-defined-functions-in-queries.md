---
title: 'Instrukcje: Wywoływanie funkcji definiowanych przez model w zapytaniach'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
ms.openlocfilehash: b142ef820e964eaf5f1afed53a6b12a9344c7dda
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189334"
---
# <a name="how-to-call-model-defined-functions-in-queries"></a>Instrukcje: Wywoływanie funkcji definiowanych przez model w zapytaniach

W tym temacie opisano, jak wywoływać funkcje, które są zdefiniowane w modelu koncepcyjnym z zapytań LINQ to Entities.  
  
 Poniższa procedura zawiera konspekt wysokiego poziomu służący do wywoływania funkcji zdefiniowanej przez model z poziomu zapytania LINQ to Entities. Poniższy przykład zawiera bardziej szczegółowe informacje na temat kroków w procedurze. W procedurze przyjęto założenie, że zdefiniowano funkcję w modelu koncepcyjnym. Aby uzyskać więcej informacji, zobacz [How to: define Custom Functions w modelu koncepcyjnym](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a>Aby wywołać funkcję zdefiniowaną w modelu koncepcyjnym  
  
1. Dodaj do aplikacji metodę środowiska uruchomieniowego języka wspólnego (CLR), która jest mapowana na funkcję zdefiniowaną w modelu koncepcyjnym. Aby zmapować metodę, należy zastosować <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> do metody. Należy zauważyć, <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> że <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> Parametry i atrybutu są nazwą przestrzeni nazw modelu koncepcyjnego i nazwą funkcji w modelu koncepcyjnym odpowiednio. Rozpoznawanie nazw funkcji dla LINQ jest rozróżniana wielkość liter.  
  
2. Wywołaj funkcję w kwerendzie LINQ to Entities.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład ilustruje sposób wywołania funkcji zdefiniowanej w modelu koncepcyjnym z poziomu zapytania LINQ to Entities. W przykładzie zastosowano model szkoły. Aby uzyskać informacje o modelu szkoły, zobacz [Tworzenie przykładowej bazy danych szkoły](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) i [generowanie pliku szkoły. edmx](/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).  
  
 Poniższa funkcja modelu koncepcyjnego zwraca liczbę lat od momentu zatrudnienia instruktora. Informacje o dodawaniu funkcji do modelu koncepcyjnego znajdują się [w temacie How to: define Custom Functions w modelu koncepcyjnym](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a>Przykład  

 Następnie Dodaj następującą metodę do aplikacji i użyj metody, <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> Aby zamapować ją na funkcję modelu koncepcyjnego:  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a>Przykład  

 Teraz można wywołać funkcję modelu koncepcyjnego z poziomu zapytania LINQ to Entities. Poniższy kod wywołuje metodę w celu wyświetlenia wszystkich instruktorów, którzy zostali zatrudnieni ponad dziesięć lat temu:  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a>Zobacz też

- [Plik. edmx — Omówienie](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Zapytania w składniku LINQ to Entities](queries-in-linq-to-entities.md)
- [Wywoływanie funkcji w zapytaniach składnika LINQ to Entities](calling-functions-in-linq-to-entities-queries.md)
- [Instrukcje: Wywoływanie funkcji definiowanych przez model jako metod obiektu](how-to-call-model-defined-functions-as-object-methods.md)
