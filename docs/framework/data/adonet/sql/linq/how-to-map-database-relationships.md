---
title: 'Instrukcje: Mapowanie relacji w bazie danych'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 538def39-8399-46fb-b02d-60ede4e050af
ms.openlocfilehash: 2f612877f5e7da6442c242aa0d56d811c0aa7cf8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166459"
---
# <a name="how-to-map-database-relationships"></a>Instrukcje: Mapowanie relacji w bazie danych

Można kodować jako odwołania do właściwości w klasie Entity, wszelkie relacje danych, które zawsze będą takie same. W przykładowej bazie danych Northwind, ponieważ klienci zwykle umieszczają zamówienia, zawsze istnieje relacja między klientami a ich zamówieniami.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] definiuje <xref:System.Data.Linq.Mapping.AssociationAttribute> atrybut, który pomaga reprezentować takie relacje. Ten atrybut jest używany razem z <xref:System.Data.Linq.EntitySet%601> typami i, <xref:System.Data.Linq.EntityRef%601> aby reprezentować, co byłoby relacją klucza obcego w bazie danych. Aby uzyskać więcej informacji, zobacz sekcję atrybut skojarzenia w [mapowaniu opartym na atrybutach](attribute-based-mapping.md).  
  
> [!NOTE]
> W wartościach właściwości magazynu AssociationAttribute i ColumnAttribute jest uwzględniana wielkość liter. Na przykład upewnij się, że wartości używane w atrybucie właściwości AssociationAttribute. Storage pasują do wielkości liter dla odpowiednich nazw właściwości używanych w innym miejscu w kodzie. Dotyczy to wszystkich języków programowania .NET, nawet tych, które nie są zazwyczaj rozróżniane wielkości liter, w tym Visual Basic. Aby uzyskać więcej informacji na temat właściwości Storage, zobacz <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType> .  
  
 Większość relacji to jeden-do-wielu, jak w przykładzie w dalszej części tego tematu. Istnieje również możliwość reprezentowania relacji jeden-do-jednego i wiele-do-wielu w następujący sposób:  
  
- Jeden do jednego: reprezentuje ten rodzaj relacji przez uwzględnienie <xref:System.Data.Linq.EntitySet%601> obu stron.  
  
     Rozważmy na przykład `Customer` - `SecurityCode` relację utworzoną w taki sposób, że kod zabezpieczający klienta nie zostanie znaleziony w `Customer` tabeli i dostęp do niego mają tylko autoryzowani osoby.  
  
- Wiele do wielu: w relacjach wiele-do-wielu, klucz podstawowy tabeli łączy (nazywany również tabelą *skrzyżowania* ) jest często tworzony przez złożone klucze obce z pozostałych dwóch tabel.  
  
     Rozważmy na przykład `Employee` - `Project` relację wiele-do-wielu utworzoną za pomocą tabeli linków `EmployeeProject` . [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wymaga, aby taka relacja była modelowana przy użyciu trzech klas: `Employee` , `Project` , i `EmployeeProject` . W takim przypadku zmiana relacji między `Employee` i a `Project` może wydawać się, że wymaga aktualizacji klucza podstawowego `EmployeeProject` . Ta sytuacja jest jednak najlepszym modelem jako usunięcie istniejącej `EmployeeProject` i nowej `EmployeeProject` .  
  
    > [!NOTE]
    > Relacje w relacyjnych bazach danych są zwykle modelowane jako wartości klucza obcego, które odwołują się do kluczy podstawowych w innych tabelach. Aby poruszać się między nimi, można jawnie skojarzyć dwie tabele przy użyciu operacji *sprzężenia* relacyjnego.  
    >
    >  Obiekty w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , z drugiej strony, odnoszą się do siebie nawzajem przy użyciu odwołań do właściwości lub kolekcji odwołań, które przechodź przy użyciu notacji *kropkowej* .  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie jeden-do-wielu `Customer` Klasa ma właściwość, która deklaruje relację między klientami a ich zamówieniami.  `Orders`Właściwość jest typu <xref:System.Data.Linq.EntitySet%601> . Ten typ oznacza, że ta relacja jest "jeden do wielu" (jeden klient do wielu zamówień). <xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A>Właściwość służy do opisywania, w jaki sposób to skojarzenie jest realizowane, a mianowicie, poprzez określenie nazwy właściwości w powiązanej klasie, która ma zostać porównana z tym elementem. W tym przykładzie `CustomerID` Właściwość jest porównywana, podobnie jak *sprzężenie* bazy danych będzie porównywać tę wartość kolumny.  
  
> [!NOTE]
> Jeśli używasz programu Visual Studio, możesz użyć Object Relational Designer, aby utworzyć skojarzenie między klasami.  
  
 [!code-csharp[DlinqCustomize#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#3)]
 [!code-vb[DlinqCustomize#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#3)]  
  
## <a name="example"></a>Przykład  

 Możesz również odwrócić sytuację. Zamiast używać `Customer` klasy do opisywania skojarzenia między klientami i zamówieniami, można użyć `Order` klasy. `Order`Klasa używa <xref:System.Data.Linq.EntityRef%601> typu do opisywania relacji z powrotem do klienta, jak w poniższym przykładzie kodu.  
  
> [!NOTE]
> <xref:System.Data.Linq.EntityRef%601>Klasa obsługuje *ładowanie odroczone*. Aby uzyskać więcej informacji, *Zobacz* [odroczone względem natychmiastowego ładowania](deferred-versus-immediate-loading.md).  
  
 [!code-csharp[DLinqCustomize#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#5)]
 [!code-vb[DLinqCustomize#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Model obiektu LINQ to SQL](the-linq-to-sql-object-model.md)
