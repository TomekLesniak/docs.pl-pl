---
title: Kwerendy pojedynczej tabeli (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b74bcf8-3f87-449f-bff7-6bcb0d69d212
ms.openlocfilehash: 17a2fcf54cae64d9443b0cc0e8a37e1002bbd394
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175359"
---
# <a name="single-table-queries-linq-to-dataset"></a>Kwerendy pojedynczej tabeli (LINQ to DataSet)

Zapytania dotyczące języka (LINQ) są używane w źródłach danych, które implementują <xref:System.Collections.Generic.IEnumerable%601> interfejs lub <xref:System.Linq.IQueryable%601> interfejs. <xref:System.Data.DataTable>Klasa nie implementuje żadnego interfejsu, dlatego należy wywołać <xref:System.Data.DataTableExtensions.AsEnumerable%2A> metodę, jeśli chcesz użyć <xref:System.Data.DataTable> jako źródła w `From` klauzuli zapytania LINQ.  
  
 Poniższy przykład pobiera wszystkie zamówienia online z tabeli SalesOrderHeader i wyświetla identyfikator zamówienia, datę zamówienia i numer zamówienia w konsoli programu.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)]
  
 Zapytanie zmiennej lokalnej jest inicjowane z wyrażeniem zapytania, które działa na co najmniej jednym źródle informacji przez zastosowanie co najmniej jednego operatora zapytań z standardowych operatorów zapytań lub, w przypadku LINQ to DataSet, operatorów specyficznych dla <xref:System.Data.DataSet> klasy. W wyrażeniu zapytania w poprzednim przykładzie użyto dwóch standardowych operatorów zapytań: `Where` i `Select` .  
  
 `Where`Klauzula filtruje sekwencję w oparciu o warunek, w tym przypadku `OnlineOrderFlag` jest ustawiona na `true` . `Select`Operator przydziela i zwraca wyliczalny obiekt, który przechwytuje argumenty przekazane do operatora. W tym przykładzie typ anonimowy jest tworzony z trzema właściwościami: `SalesOrderID` , `OrderDate` , i `SalesOrderNumber` . Wartości tych trzech właściwości są ustawiane na wartości `SalesOrderID` , `OrderDate` , i `SalesOrderNumber` kolumn z `SalesOrderHeader` tabeli.  
  
 `foreach`Pętla następnie wylicza wyliczalny obiekt zwracany przez `Select` i daje wyniki zapytania. Ponieważ zapytanie jest <xref:System.Linq.Enumerable> typu, który implementuje <xref:System.Collections.Generic.IEnumerable%601> , obliczanie zapytania jest odroczone do momentu, gdy zmienna zapytania zostanie powtórzona przy użyciu `foreach` pętli. Wywnioskowana Ocena zapytania umożliwia przechowywanie zapytań jako wartości, które mogą być oceniane wiele razy, za każdym razem, gdy dają one inne wyniki.  
  
 <xref:System.Data.DataRowExtensions.Field%2A>Metoda zapewnia dostęp do wartości kolumn a <xref:System.Data.DataRow> i <xref:System.Data.DataRowExtensions.SetField%2A> (nie pokazano w poprzednim przykładzie) ustawia wartości kolumn w <xref:System.Data.DataRow> . <xref:System.Data.DataRowExtensions.Field%2A>Metody i <xref:System.Data.DataRowExtensions.SetField%2A> metody obsługują typy wartości null, więc nie trzeba jawnie sprawdzać wartości null. Obie metody są metodami ogólnymi, co oznacza, że nie trzeba rzutować zwracanego typu. Można użyć metody dostępu do istniejącej kolumny <xref:System.Data.DataRow> (na przykład `o["OrderDate"]` ), ale wykonanie tej operacji wymagałoby rzutowania obiektu powrotnego na odpowiedni typ.  Jeśli kolumna jest typem wartości null, należy sprawdzić, czy wartość jest równa null przy użyciu <xref:System.Data.DataRow.IsNull%2A> metody. Aby uzyskać więcej informacji, zobacz [pola ogólne i metody SetField](generic-field-and-setfield-methods-linq-to-dataset.md).  
  
 Należy zauważyć, że typ danych określony w parametrze ogólnym `T` <xref:System.Data.DataRowExtensions.Field%2A> metody i <xref:System.Data.DataRowExtensions.SetField%2A> metody musi być zgodny z typem podstawowej wartości lub <xref:System.InvalidCastException> zostanie wygenerowany. Określona nazwa kolumny musi być również zgodna z nazwą kolumny w <xref:System.Data.DataSet> lub <xref:System.ArgumentException> zostanie wygenerowane. W obu przypadkach wyjątek jest generowany podczas wyliczania danych w czasie wykonywania, gdy zapytanie jest wykonywane.  
  
## <a name="see-also"></a>Zobacz też

- [Zapytania wielotabelowe](cross-table-queries-linq-to-dataset.md)
- [Wykonywanie zapytania do typizowanych zestawów danych](querying-typed-datasets.md)
- [Field i SetField, metody ogólne](generic-field-and-setfield-methods-linq-to-dataset.md)
