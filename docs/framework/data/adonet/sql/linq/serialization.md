---
title: Serialization2
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a15ae411-8dc2-4ca3-84d2-01c9d5f1972a
ms.openlocfilehash: 778cc73575ffc7421854fd89592f1c4eaa284678
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203556"
---
# <a name="serialization"></a>Serializacja

W tym temacie opisano [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] możliwości serializacji. Poniższe akapity zawierają informacje dotyczące sposobu dodawania serializacji podczas generowania kodu w czasie projektowania oraz zachowania serializacji w czasie wykonywania dla [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] klas.  
  
 Kod serializacji można dodać w czasie projektowania przy użyciu jednej z następujących metod:  
  
- W Object Relational Designer Zmień właściwość **tryb serializacji** na **jednokierunkowy**.  
  
- W wierszu polecenia SQLMetal Dodaj opcję **/Serialization** . Aby uzyskać więcej informacji, zobacz [SqlMetal.exe (Narzędzie generowania kodu)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Omówienie  

 Kod wygenerowany przez [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zapewnia domyślnie odroczone funkcje ładowania. Ładowanie odroczone jest bardzo wygodne w średniej warstwie na potrzeby przezroczystego ładowania danych na żądanie. Jednak jest to problematyczne dla serializacji, ponieważ serializator wyzwala opóźnione ładowanie, niezależnie od tego, czy odroczone ładowanie jest zamierzone, czy nie. W efekcie, gdy obiekt jest serializowany, jego zamknięcie przechodnie we wszystkich odwołaniach załadowanych wychodzących jest serializowane.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Funkcja serializacji rozwiązuje ten problem, głównie przez dwa mechanizmy:  
  
- Tryb wyłączania <xref:System.Data.Linq.DataContext> odroczonego ładowania ( <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> ). Aby uzyskać więcej informacji, zobacz <xref:System.Data.Linq.DataContext>.  
  
- Przełącznik generowania kodu do generowania <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType> i <xref:System.Runtime.Serialization.DataMemberAttribute?displayProperty=nameWithType> atrybutów dla wygenerowanych jednostek. Ten aspekt, łącznie z zachowaniem klas ładowania opóźnienia w ramach serializacji, jest głównym tematem tego tematu.  
  
### <a name="definitions"></a>Definicje  
  
- *Serializator schematu DataContract*: domyślny serializator używany przez składnik Windows Communication Framework (WCF) w .NET Framework 3,0 lub nowszych wersjach.  
  
- Jednokierunkowa *Serializacja*: szeregowana wersja klasy, która zawiera tylko jednostopniową Właściwość skojarzenia (aby uniknąć cyklu). Zgodnie z Konwencją właściwość po stronie nadrzędnej relacji klucza podstawowego jest oznaczona do serializacji. Druga strona w skojarzeniu dwukierunkowym nie jest serializowana.  
  
     Jednokierunkowa Serializacja jest jedynym typem serializacji obsługiwanym przez [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .  
  
## <a name="code-example"></a>Przykład kodu  

 Poniższy kod używa tradycyjnych `Customer` i `Order` klas z przykładowej bazy danych Northwind i pokazuje, jak te klasy są uzupełnione atrybutami serializacji.  
  
 [!code-csharp[DLinqSerialization#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#1)]
 [!code-vb[DLinqSerialization#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#1)]  
  
 [!code-csharp[DLinqSerialization#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#2)]
 [!code-vb[DLinqSerialization#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#2)]  
  
 [!code-csharp[DLinqSerialization#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#3)]
 [!code-vb[DLinqSerialization#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#3)]  
  
 Dla `Order` klasy w poniższym przykładzie tylko Właściwość odwrotnego skojarzenia odpowiadająca `Customer` klasie jest pokazywana dla zwięzłości. Nie ma <xref:System.Runtime.Serialization.DataMemberAttribute> atrybutu, aby uniknąć cyklu.  
  
 [!code-csharp[DLinqSerialization#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#4)]
 [!code-vb[DLinqSerialization#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#4)]  
  
 [!code-csharp[DLinqSerialization#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#5)]
 [!code-vb[DLinqSerialization#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#5)]  
  
### <a name="how-to-serialize-the-entities"></a>Jak serializować jednostki  

 Można serializować jednostki w kodach przedstawionych w poprzedniej sekcji w następujący sposób:  
  
 [!code-csharp[DLinqSerialization#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/Program.cs#6)]
 [!code-vb[DLinqSerialization#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/Module1.vb#6)]  
  
### <a name="self-recursive-relationships"></a>Relacje samocykliczne  

 Relacje samocykliczne są zgodne z tym samym wzorcem. Właściwość skojarzenia odpowiadająca kluczowi obcemu nie ma <xref:System.Runtime.Serialization.DataMemberAttribute> atrybutu, natomiast Właściwość Parent ma wartość.  
  
 Rozważmy następującą klasę, która ma dwie relacje samocykliczne: Employee. Manager/Reports i Employee. opiekun/Mentees.  
  
 [!code-csharp[DLinqSerialization#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#7)]
 [!code-vb[DLinqSerialization#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#7)]  
  
## <a name="see-also"></a>Zobacz też

- [Informacje uzupełniające](background-information.md)
- [SqlMetal.exe (Narzędzie generowania kodu)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [Instrukcje: Umożliwianie serializacji jednostek](how-to-make-entities-serializable.md)
