---
title: Dodawanie logiki biznesowej przy użyciu metod częściowych
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: 9ad3329c621b8bf8eaa0fd5f986ac7e8cff97d9e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156163"
---
# <a name="adding-business-logic-by-using-partial-methods"></a>Dodawanie logiki biznesowej przy użyciu metod częściowych

Możesz dostosować Visual Basic i wygenerowany kod C# w projektach przy [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] użyciu *metod częściowych*. Kod, który [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generuje definiuje podpisy jako jedną część metody częściowej. Jeśli chcesz zaimplementować metodę, możesz dodać własną metodę częściową. Jeśli nie dodasz własnej implementacji, kompilator odrzuca podpis metod częściowych i wywołuje metody domyślne w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .  
  
> [!NOTE]
> Jeśli używasz programu Visual Studio, możesz użyć Object Relational Designer, aby dodać walidację i inne dostosowania do klas jednostek.  
  
 Na przykład domyślne mapowanie `Customer` klasy w przykładowej bazie danych Northwind zawiera następującą metodę częściową:  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 Możesz zaimplementować własną metodę, dodając kod, taki jak poniżej, do własnej klasy częściowej `Customer` :  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 Takie podejście jest zwykle używane w programie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , aby przesłonić domyślne metody dla `Insert` ,, `Update` `Delete` i do walidacji właściwości podczas zdarzeń cyklu życia obiektu.  
  
 Aby uzyskać więcej informacji, zobacz [częściowe metody](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) lub [częściowe (Metoda) (odwołanie w c#)](../../../../../csharp/language-reference/keywords/partial-method.md) (c#).  
  
## <a name="example"></a>Przykład  
  
### <a name="description"></a>Opis  

 Poniższy przykład pokazuje `ExampleClass` pierwszy, ponieważ może być zdefiniowany przez narzędzie generujące kod, takie jak SQLMetal, a następnie jak można zaimplementować tylko jedną z dwóch metod.  
  
### <a name="code"></a>Kod  

 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a>Przykład  
  
### <a name="description"></a>Opis  

 Poniższy przykład używa relacji między `Shipper` i `Order` jednostką. Zwróć uwagę między metodami częściowymi `InsertShipper` i `DeleteShipper` . Te metody zastępują domyślne metody częściowe dostarczone przez [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Mapowanie.  
  
### <a name="code"></a>Kod  

 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Tworzenie i przesyłanie zmian danych](making-and-submitting-data-changes.md)
- [Dostosowywanie operacji wstawiania, aktualizowania i usuwania](customizing-insert-update-and-delete-operations.md)
