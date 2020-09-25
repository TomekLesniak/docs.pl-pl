---
title: Zapytania LINQ to SQL
ms.date: 03/30/2017
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
ms.openlocfilehash: c49644a866a6e245c6be1f9a8e8f95d003fd0191
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175229"
---
# <a name="linq-to-sql-queries"></a>Zapytania LINQ to SQL

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Zapytania są definiowane przy użyciu takiej samej składni jak w LINQ. Jedyną różnicą jest to, że obiekty, do których odwołują się zapytania, są mapowane na elementy w bazie danych. Aby uzyskać więcej informacji, zobacz [wprowadzenie do zapytań LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tłumaczy zapytania zapisane w równoważne zapytania SQL i wysyła je do serwera w celu przetworzenia. Dokładniej mówiąc, aplikacja używa [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] interfejsu API do żądania wykonania zapytania. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Następnie dostawca przekształca zapytanie w tekst SQL i deleguje wykonywanie do dostawcy ADO. Dostawca ADO zwraca wyniki zapytania jako `DataReader` . [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Dostawca tłumaczy wyniki ADO na <xref:System.Linq.IQueryable> kolekcję obiektów użytkownika.  
  
> [!NOTE]
> Większość metod i operatorów na .NET Framework typów wbudowanych ma bezpośrednie tłumaczenia na SQL. Te, które nie mogą przetłumaczyć generowania wyjątków czasu wykonywania. Aby uzyskać więcej informacji, zobacz [Mapowanie typu SQL-CLR](sql-clr-type-mapping.md).  
  
 W poniższej tabeli przedstawiono podobieństwa i różnice między elementami LINQ i [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Query.  
  
|Element|Zapytanie LINQ|[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Dotyczących|  
|----------|----------------|----------------------------------------------------------------------|  
|Zwracany typ zmiennej lokalnej, która przechowuje zapytanie (dla zapytań, które zwracają sekwencje)|Ogólnego `IEnumerable`|Ogólnego `IQueryable`|  
|Określanie źródła danych|Używa `From` klauzuli (Visual Basic) lub `from` (C#)|Ta sama|  
|Filtrowanie|Używa `Where` / `where` klauzuli|Ta sama|  
|Grupowanie|Używa `Group…By` / `groupby` klauzuli|Ta sama|  
|Zaznaczanie (Projekcja)|Używa `Select` / `select` klauzuli|Ta sama|  
|Odroczone względem natychmiastowego wykonania|Zobacz [wprowadzenie do zapytań LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)|Ta sama|  
|Implementowanie sprzężeń|Używa `Join` / `join` klauzuli|Może używać `Join` / `join` klauzuli, ale bardziej efektywnie korzysta z <xref:System.Data.Linq.Mapping.AssociationAttribute> atrybutu. Aby uzyskać więcej informacji, zobacz [wykonywanie zapytań w relacjach](querying-across-relationships.md).|  
|Zdalne a wykonywanie lokalne||Aby uzyskać więcej informacji, zobacz [zdalne a wykonywanie lokalne](remote-vs-local-execution.md).|  
|Przesyłanie strumieniowe i wykonywanie zapytań w pamięci podręcznej|Nie dotyczy w przypadku lokalnego scenariusza pamięci||  
  
## <a name="see-also"></a>Zobacz też

- [Wprowadzenie do kwerend LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [Podstawowe operacje zapytań LINQ](../../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)
- [Relacje typów w operacjach zapytań LINQ](../../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
- [Pojęcia dotyczące zapytań](query-concepts.md)
