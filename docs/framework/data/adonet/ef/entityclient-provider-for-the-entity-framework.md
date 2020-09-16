---
title: Dostawca EntityClient dla programu Entity Framework
ms.date: 03/30/2017
ms.assetid: 8c5db787-78e6-4a34-8dc1-188bca0aca5e
ms.openlocfilehash: cd02f2ede37ef3518071b5d4c79cdffe2e2f1b5d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542597"
---
# <a name="entityclient-provider-for-the-entity-framework"></a>Dostawca EntityClient dla programu Entity Framework
Dostawca EntityClient jest dostawcą danych używanym przez aplikacje Entity Framework do uzyskiwania dostępu do danych opisanych w modelu koncepcyjnym. Aby uzyskać informacje o modelach koncepcyjnych, zobacz [modelowanie i mapowanie](modeling-and-mapping.md). EntityClient używa innych dostawców danych .NET Framework, aby uzyskać dostęp do źródła danych. Na przykład EntityClient używa Dostawca danych .NET Framework dla SQL Server (SqlClient) podczas uzyskiwania dostępu do bazy danych SQL Server. Aby uzyskać informacje na temat dostawcy SqlClient, zobacz temat [SqlClient dla Entity Framework](sqlclient-for-the-entity-framework.md). Dostawca EntityClient jest zaimplementowany w <xref:System.Data.EntityClient> przestrzeni nazw.  
  
## <a name="managing-connections"></a>Zarządzanie połączeniami  
 Entity Framework kompiluje się w oparciu o ADO.NET dostawców danych specyficznych dla magazynu, dostarczając <xref:System.Data.EntityClient.EntityConnection> do podstawowego dostawcy danych i relacyjnej. Aby skonstruować <xref:System.Data.EntityClient.EntityConnection> obiekt, należy odwołać się do zestawu metadanych zawierającego wymagane modele i mapowania, a także nazwę dostawcy danych specyficzną dla magazynu i parametry połączenia. Po zakończeniu <xref:System.Data.EntityClient.EntityConnection> będzie można uzyskać dostęp do jednostek za pośrednictwem klas generowanych na podstawie modelu koncepcyjnego.  
  
 Możesz określić parametry połączenia w pliku app.config.  
  
 <xref:System.Data.EntityClient>Zawiera również <xref:System.Data.EntityClient.EntityConnectionStringBuilder> klasę. Ta klasa umożliwia deweloperom Programistyczne tworzenie składni parametrów połączenia oraz analizowanie i ponowne kompilowanie istniejących parametrów połączenia przy użyciu właściwości i metod klasy. Aby uzyskać więcej informacji, zobacz [How to: build The EntityConnection Connection String](how-to-build-an-entityconnection-connection-string.md).  
  
## <a name="creating-queries"></a>Tworzenie zapytań  
 [!INCLUDE[esql](../../../../../includes/esql-md.md)]Język to niezależny od magazynu DIALEKT SQL, który działa bezpośrednio ze schematami jednostek koncepcyjnych i obsługuje Entity Data Model pojęć, takich jak dziedziczenie i relacje. <xref:System.Data.EntityClient.EntityCommand>Klasa jest używana do wykonywania [!INCLUDE[esql](../../../../../includes/esql-md.md)] polecenia względem modelu jednostki. Podczas konstruowania <xref:System.Data.EntityClient.EntityCommand> obiektów można określić nazwę procedury składowanej lub tekst zapytania. Entity Framework współpracuje z dostawcami danych specyficznymi dla magazynu w celu tłumaczenia ogólnego [!INCLUDE[esql](../../../../../includes/esql-md.md)] na zapytania specyficzne dla magazynu. Aby uzyskać więcej informacji na temat pisania [!INCLUDE[esql](../../../../../includes/esql-md.md)] zapytań, zobacz [Entity SQL Language](./language-reference/entity-sql-language.md).  
  
 Poniższy przykład tworzy <xref:System.Data.EntityClient.EntityCommand> obiekt i przypisuje [!INCLUDE[esql](../../../../../includes/esql-md.md)] tekst zapytania do jego <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> właściwości. To [!INCLUDE[esql](../../../../../includes/esql-md.md)] zapytanie żąda produktów uporządkowanych według ceny listy z modelu koncepcyjnego. Poniższy kod nie zawiera żadnych informacji o modelu magazynu.  
  
 ```csharp
EntityCommand cmd = conn.CreateCommand();
cmd.CommandText = @"SELECT VALUE p
  FROM AdventureWorksEntities.Product AS p
  ORDER BY p.ListPrice";
```
  
## <a name="executing-queries"></a>Wykonywanie zapytań  
 Gdy zapytanie jest wykonywane, jest analizowane i konwertowane do drzewa poleceń w postaci kanonicznej. Wszystkie kolejne operacje przetwarzania są wykonywane w drzewie poleceń. Drzewo poleceń jest sposobem komunikacji między programem <xref:System.Data.EntityClient> a podstawowym dostawcą danych .NET Framework, na przykład <xref:System.Data.SqlClient> .  
  
 <xref:System.Data.EntityClient.EntityDataReader>Prezentuje wyniki wykonywania <xref:System.Data.EntityClient.EntityCommand> względem modelu koncepcyjnego. Aby wykonać polecenie, które zwraca <xref:System.Data.EntityClient.EntityDataReader> wywołanie <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A> . <xref:System.Data.EntityClient.EntityDataReader>Implementuje, <xref:System.Data.IExtendedDataRecord> aby opisać bogate wyniki strukturalne.  
  
## <a name="managing-transactions"></a>Zarządzanie transakcjami  
 W Entity Framework istnieją dwa sposoby używania transakcji: automatyczne i jawne. Transakcje automatyczne używają <xref:System.Transactions> przestrzeni nazw, a transakcje jawne używają <xref:System.Data.EntityClient.EntityTransaction> klasy.  
  
 Aby zaktualizować dane, które są udostępniane za pomocą modelu koncepcyjnego, zobacz [How to: Manage Transactions in the Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738523(v=vs.100)).  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Instrukcje: Tworzenie parametrów połączenia EntityConnection](how-to-build-an-entityconnection-connection-string.md)  
  
 [Instrukcje: Wykonywanie zapytania, które zwraca wyniki PrimitiveType](how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Instrukcje: Wykonywanie zapytania, które zwraca wyniki StructuralType](how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Instrukcje: Wykonywanie zapytania, które zwraca wyniki RefType](how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Instrukcje: Wykonywanie zapytania, które zwraca typy złożone](how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Instrukcje: Wykonywanie zapytania, które zwraca kolekcje zagnieżdżone](how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Instrukcje: Wykonywanie zapytania SQL do sparametryzowanej jednostki przy użyciu EntityCommand](how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Instrukcje: Wykonywanie zapytania SQL do sparametryzowanej procedury składowanej przy użyciu EntityCommand](how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Instrukcje: Wykonywanie zapytania polimorficznego](how-to-execute-a-polymorphic-query.md)  
  
 [Instrukcje: Nawigowanie po relacjach za pomocą operatora nawigowania](how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="see-also"></a>Zobacz także

- [Zarządzanie połączeniami i transakcjami](/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100))
- [Program Entity Framework na platformie ADO.NET](index.md)
- [Dokumentacja języka](./language-reference/index.md)
