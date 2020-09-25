---
title: Zwracanie średniej wartości z sekwencji numerycznej
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee3b8673-a2e7-4b2d-9b5c-4972ff9e665d
ms.openlocfilehash: 1f113a475bb350640aef7a6b4d7a70b32509d1e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200410"
---
# <a name="return-the-average-value-from-a-numeric-sequence"></a>Zwracanie średniej wartości z sekwencji numerycznej

<xref:System.Linq.Enumerable.Average%2A>Operator oblicza średnią sekwencji wartości liczbowych.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Tłumaczenie `Average` wartości całkowitych jest obliczane jako liczba całkowita, nie jako Double.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład zwraca średnią `Freight` wartości w `Orders` tabeli.  
  
 Wyniki z przykładowej bazy danych Northwind byłyby `78.2442` .  
  
 [!code-csharp[DLinqQueryExamples#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#1)]
 [!code-vb[DLinqQueryExamples#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#1)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład zwraca średnią cenę jednostkową wszystkich `Products` w `Products` tabeli.  
  
 Wyniki z przykładowej bazy danych Northwind byłyby `28.8663` .  
  
 [!code-csharp[DLinqQueryExamples#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#2)]
 [!code-vb[DLinqQueryExamples#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#2)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład używa operatora, `Average` Aby znaleźć te, `Products` których cena jednostkowa jest wyższa niż średnia cena jednostkowa kategorii, do której należy. Przykład następnie wyświetla wyniki w grupach.  
  
 Należy zauważyć, że ten przykład wymaga użycia `var` słowa kluczowego w języku C#, ponieważ zwracany typ jest anonimowy.  
  
 [!code-csharp[DLinqQueryExamples#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#3)]
 [!code-vb[DLinqQueryExamples#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#3)]  
  
 W przypadku uruchomienia tego zapytania względem przykładowej bazy danych Northwind wyniki powinny wyglądać następująco:  
  
 `1`  
  
 `Côte de Blaye`  
  
 `Ipoh Coffee`  
  
 `2`  
  
 `Grandma's Boysenberry Spread`  
  
 `Northwoods Cranberry Sauce`  
  
 `Sirop d'érable`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `Gumbär Gummibärchen`  
  
 `Schoggi Schokolade`  
  
 `Tarte au sucre`  
  
 `4`  
  
 `Queso Manchego La Pastora`  
  
 `Mascarpone Fabioli`  
  
 `Raclette Courdavault`  
  
 `Camembert Pierrot`  
  
 `Gudbrandsdalsost`  
  
 `Mozzarella di Giovanni`  
  
 `5`  
  
 `Gustaf's Knäckebröd`  
  
 `Gnocchi di nonna Alice`  
  
 `Wimmers gute Semmelknödel`  
  
 `6`  
  
 `Mishi Kobe Niku`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Rössle Sauerkraut`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Ikura`  
  
 `Carnarvon Tigers`  
  
 `Nord-Ost Matjeshering`  
  
 `Gravad lax`  
  
## <a name="see-also"></a>Zobacz też

- [Zapytania zagregowane](aggregate-queries.md)
