---
title: Mapowania typów środowiska SQL-CLR
ms.date: 07/23/2018
ms.assetid: 4ed76327-54a7-414b-82a9-7579bfcec04b
ms.openlocfilehash: 313fd81bd84a99e4a2d32925a7d3bb4776f8472b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203543"
---
# <a name="sql-clr-type-mapping"></a>Mapowania typów środowiska SQL-CLR

W LINQ to SQL model danych relacyjnej bazy danych jest mapowany na model obiektów, który jest wyrażony w wybranym języku programowania. Gdy aplikacja zostanie uruchomiona, LINQ to SQL przetłumaczy zapytania zintegrowane z językiem w modelu obiektów na SQL i wyśle je do bazy danych w celu wykonania. Gdy baza danych zwróci wyniki, LINQ to SQL przekształca wyniki z powrotem do obiektów, z których można korzystać w własnym języku programowania.  
  
 Aby można było przetłumaczyć dane między modelem obiektów i bazą danych, należy zdefiniować *Mapowanie typu* . LINQ to SQL używa mapowania typu, aby dopasować każdy typ środowiska uruchomieniowego języka wspólnego (CLR) do określonego typu SQL Server. W modelu obiektów z mapowaniem opartym na atrybutach można definiować mapowania typów i inne informacje o mapowaniu, takie jak struktura bazy danych i relacje między tabelami. Alternatywnie możesz określić informacje o mapowaniu poza modelem obiektów z zewnętrznym plikiem mapowania. Aby uzyskać więcej informacji, zobacz [Mapowanie oparte na atrybutach](attribute-based-mapping.md) i [Mapowanie zewnętrzne](external-mapping.md).  
  
 W tym temacie omówiono następujące kwestie:  
  
- [Domyślne mapowanie typów](#DefaultTypeMapping)  
  
- [Macierz zachowań czasu wykonywania mapowania typów](#BehaviorMatrix)  
  
- [Różnice w zachowaniu między środowiskiem CLR a wykonywaniem kodu SQL](#BehaviorDiffs)  
  
- [Wyliczenie wyliczenia](#EnumMapping)  
  
- [Mapowanie numeryczne](#NumericMapping)  
  
- [Mapowanie tekstu i XML](#TextMapping)  
  
- [Mapowanie daty i godziny](#DateMapping)  
  
- [Mapowanie binarne](#BinaryMapping)  
  
- [Mapowanie różne](#MiscMapping)  
  
<a name="DefaultTypeMapping"></a>

## <a name="default-type-mapping"></a>Domyślne mapowanie typów  

 Można automatycznie utworzyć model obiektów lub zewnętrzny plik mapowania przy użyciu Object Relational Designer (Projektant O/R) lub narzędzia wiersza polecenia SQLMetal. Domyślne mapowania typów dla tych narzędzi definiują, które typy CLR są wybrane do mapowania na kolumny w bazie danych SQL Server. Aby uzyskać więcej informacji o korzystaniu z tych narzędzi, zobacz [Tworzenie modelu obiektów](creating-the-object-model.md).  
  
 Można również użyć metody, <xref:System.Data.Linq.DataContext.CreateDatabase%2A> Aby utworzyć bazę danych SQL Server na podstawie informacji o mapowaniu w modelu obiektów lub zewnętrznym pliku mapowania. Domyślne mapowania typu dla <xref:System.Data.Linq.DataContext.CreateDatabase%2A> metody definiują, który typ SQL Server kolumn jest tworzony w celu mapowania na typy CLR w modelu obiektów. Aby uzyskać więcej informacji, zobacz [jak: dynamiczne tworzenie bazy danych](how-to-dynamically-create-a-database.md).  
  
<a name="BehaviorMatrix"></a>

## <a name="type-mapping-run-time-behavior-matrix"></a>Macierz zachowań czasu wykonywania mapowania typów  

 Na poniższym diagramie przedstawiono oczekiwane zachowanie w czasie wykonywania mapowania określonego typu, gdy dane są pobierane lub zapisywane w bazie danych. Z wyjątkiem serializacji, LINQ to SQL nie obsługuje mapowania między dowolnymi typami danych CLR lub SQL Server, które nie są określone w tej macierzy. Aby uzyskać więcej informacji o obsłudze serializacji, zobacz [Serializacja binarna](#BinarySerialization).  

![Tabela mapowania typu danych SQL CLR SQL Server](./media/sql-clr-type-mapping.png)

> [!NOTE]
> Niektóre mapowania typów mogą spowodować przepełnienie lub wyjątki utraty danych podczas tłumaczenia do bazy danych lub z niej.  
  
### <a name="custom-type-mapping"></a>Niestandardowe Mapowanie typów  

 W przypadku LINQ to SQL nie są ograniczone do domyślnych mapowań typów używanych przez projektanta O/R, SQLMetal i <xref:System.Data.Linq.DataContext.CreateDatabase%2A> metodę. Można utworzyć niestandardowe mapowania typów, jawnie określając je w pliku DBML. Następnie można użyć tego pliku DBML do utworzenia kodu modelu obiektu i pliku mapowania. Aby uzyskać więcej informacji, zobacz [niestandardowe mapowania typów SQL-CLR](sql-clr-custom-type-mappings.md).  
  
<a name="BehaviorDiffs"></a>

## <a name="behavior-differences-between-clr-and-sql-execution"></a>Różnice w zachowaniu między środowiskiem CLR a wykonywaniem kodu SQL  

 Ze względu na różnice między dokładnością i wykonywaniem między środowiskiem CLR a SQL Server, możesz otrzymać różne wyniki lub inne zachowanie w zależności od tego, gdzie wykonujesz obliczenia. Obliczenia wykonywane w zapytaniach LINQ to SQL są w rzeczywistości tłumaczone na Transact-SQL, a następnie wykonywane w bazie danych SQL Server. Obliczenia wykonywane poza zapytaniami LINQ to SQL są wykonywane w kontekście środowiska CLR.  
  
 Na przykład poniżej przedstawiono niektóre różnice w zachowaniu między środowiskiem CLR i SQL Server:  
  
- SQL Server porządkuje niektóre typy danych inaczej niż dane typu równoważnego w środowisku CLR. Na przykład SQL Server dane typu `UNIQUEIDENTIFIER` są uporządkowane inaczej niż dane CLR typu <xref:System.Guid?displayProperty=nameWithType> .  
  
- SQL Server obsługuje niektóre operacje porównywania ciągów inaczej niż środowisko CLR. W SQL Server zachowanie porównania ciągów zależy od ustawień sortowania na serwerze. Aby uzyskać więcej informacji, zobacz [Praca z sortowaniem](/previous-versions/sql/sql-server-2008-r2/ms187582(v=sql.105)) w Microsoft SQL Server Books Online.  
  
- SQL Server mogą zwracać różne wartości dla niektórych funkcji mapowanych niż środowisko CLR. Na przykład funkcje równości będą się różnić, ponieważ SQL Server traktuje dwa ciągi, aby były równe, jeśli różnią się tylko znakami końcowymi. środowisko CLR uznaje, że nie jest równe.  
  
<a name="EnumMapping"></a>

## <a name="enum-mapping"></a>Wyliczenie wyliczenia  

 LINQ to SQL obsługuje mapowanie typu CLR <xref:System.Enum?displayProperty=nameWithType> na typy SQL Server na dwa sposoby:  
  
- Mapowanie na typy liczbowe SQL ( `TINYINT` , `SMALLINT` , `INT` , `BIGINT` )  
  
     Podczas mapowania <xref:System.Enum?displayProperty=nameWithType> typu CLR na typ liczbowy SQL, można mapować podstawową wartość całkowitą środowiska CLR <xref:System.Enum?displayProperty=nameWithType> na wartość kolumny SQL Server bazy danych. Na przykład, jeśli <xref:System.Enum?displayProperty=nameWithType> nazwa `DaysOfWeek` zawiera element członkowski o nazwie `Tue` z podstawową wartością całkowitą wynoszącą 3, ten element członkowski jest mapowany na wartość bazy danych 3.  
  
- Mapowanie na typy tekstu SQL ( `CHAR` , `NCHAR` , `VARCHAR` , `NVARCHAR` )  
  
     Podczas mapowania <xref:System.Enum?displayProperty=nameWithType> typu CLR na typ tekstu SQL wartość bazy danych SQL jest mapowana na nazwy <xref:System.Enum?displayProperty=nameWithType> elementów członkowskich środowiska CLR. Na przykład, jeśli <xref:System.Enum?displayProperty=nameWithType> nazwa `DaysOfWeek` zawiera element członkowski o nazwie `Tue` z podstawową wartością całkowitą wynoszącą 3, ten element członkowski jest mapowany na wartość bazy danych `Tue` .  
  
> [!NOTE]
> Podczas mapowania typów tekstu SQL na środowisko CLR <xref:System.Enum?displayProperty=nameWithType> należy uwzględnić tylko nazwy <xref:System.Enum> elementów członkowskich w mapowanej kolumnie SQL. Inne wartości nie są obsługiwane w <xref:System.Enum> zamapowanej kolumnie SQL.  
  
 Narzędzie wiersza polecenia Projektant O/R i SQLMetal nie może automatycznie zmapować typu SQL na <xref:System.Enum> klasę CLR. Należy jawnie skonfigurować to mapowanie, dostosowując plik DBML do użycia przez projektanta O/R i SQLMetal. Aby uzyskać więcej informacji na temat niestandardowego mapowania typów, zobacz [niestandardowe mapowania typów SQL-CLR](sql-clr-custom-type-mappings.md).  
  
 Ponieważ kolumna SQL przeznaczona do wyliczenia będzie mieć taki sam typ jak inne kolumny liczbowe i tekstowe; Narzędzia te nie rozpoznają zamiaru i domyślnego mapowania zgodnie z opisem w poniższych sekcjach [Mapowanie liczbowe](#NumericMapping) i [tekst i XML](#TextMapping) . Aby uzyskać więcej informacji na temat generowania kodu przy użyciu pliku DBML, zobacz [generowanie kodu w LINQ to SQL](code-generation-in-linq-to-sql.md).  
  
 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>Metoda tworzy kolumnę SQL typu liczbowego w celu mapowania <xref:System.Enum?displayProperty=nameWithType> typu CLR.  
  
<a name="NumericMapping"></a>

## <a name="numeric-mapping"></a>Mapowanie numeryczne  

 LINQ to SQL umożliwia mapowanie wielu typów CLR i SQL Server. W poniższej tabeli przedstawiono typy CLR, które Projektant O/R i SQLMetal wybiera podczas kompilowania modelu obiektów lub zewnętrznego pliku mapowania na podstawie bazy danych.  
  
|Typ SQL Server|Domyślne mapowanie typu CLR używane przez projektanta O/R i SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`BIT`|<xref:System.Boolean?displayProperty=nameWithType>|  
|`TINYINT`|<xref:System.Int16?displayProperty=nameWithType>|  
|`INT`|<xref:System.Int32?displayProperty=nameWithType>|  
|`BIGINT`|<xref:System.Int64?displayProperty=nameWithType>|  
|`SMALLMONEY`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`MONEY`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`DECIMAL`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`NUMERIC`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`REAL/FLOAT(24)`|<xref:System.Single?displayProperty=nameWithType>|  
|`FLOAT/FLOAT(53)`|<xref:System.Double?displayProperty=nameWithType>|  
  
 W następnej tabeli przedstawiono domyślne mapowania typów używane przez <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> metodę w celu zdefiniowania typu kolumn SQL do zamapowania na typy CLR zdefiniowane w modelu obiektów lub zewnętrznym pliku mapowania.  
  
|Typ CLR|Domyślny typ SQL Server używany przez <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Boolean?displayProperty=nameWithType>|`BIT`|  
|<xref:System.Byte?displayProperty=nameWithType>|`TINYINT`|  
|<xref:System.Int16?displayProperty=nameWithType>|`SMALLINT`|  
|<xref:System.Int32?displayProperty=nameWithType>|`INT`|  
|<xref:System.Int64?displayProperty=nameWithType>|`BIGINT`|  
|<xref:System.SByte?displayProperty=nameWithType>|`SMALLINT`|  
|<xref:System.UInt16?displayProperty=nameWithType>|`INT`|  
|<xref:System.UInt32?displayProperty=nameWithType>|`BIGINT`|  
|<xref:System.UInt64?displayProperty=nameWithType>|`DECIMAL(20)`|  
|<xref:System.Decimal?displayProperty=nameWithType>|`DECIMAL(29,4)`|  
|<xref:System.Single?displayProperty=nameWithType>|`REAL`|  
|<xref:System.Double?displayProperty=nameWithType>|`FLOAT`|  
  
 Istnieje wiele innych mapowań numerycznych, które można wybrać, ale niektóre mogą spowodować przepełnienie lub wyjątki utraty danych podczas tłumaczenia do bazy danych lub z niej. Aby uzyskać więcej informacji, zobacz [macierze zachowania w czasie wykonywania mapowania typu](#BehaviorMatrix).  
  
### <a name="decimal-and-money-types"></a>Typy dziesiętne i pieniężne  

 Domyślna precyzja typu SQL Server `DECIMAL` (18 cyfr dziesiętnych po lewej i prawej stronie przecinka dziesiętnego) jest znacznie mniejsza niż precyzja <xref:System.Decimal?displayProperty=nameWithType> typu CLR, z którym jest domyślnie sparowana. Może to spowodować utratę dokładności podczas zapisywania danych w bazie danych. Jednak w przypadku, gdy `DECIMAL` typ SQL Server jest skonfigurowany z większą niż 29 cyfr. Jeśli typ SQL Server został `DECIMAL` skonfigurowany z większą dokładnością niż środowisko CLR <xref:System.Decimal?displayProperty=nameWithType> , podczas pobierania danych z bazy danych może wystąpić utrata dokładności.  
  
 SQL Server `MONEY` i `SMALLMONEY` typy, które są również sparowane z <xref:System.Decimal?displayProperty=nameWithType> typem CLR, mają znacznie mniejszą precyzję, co może spowodować przepełnienie lub wyjątki utraty danych podczas zapisywania danych w bazie danych.  
  
<a name="TextMapping"></a>

## <a name="text-and-xml-mapping"></a>Mapowanie tekstu i XML  

 Istnieje również wiele typów tekstowych i XML, które można mapować przy użyciu LINQ to SQL. W poniższej tabeli przedstawiono typy CLR, które Projektant O/R i SQLMetal wybiera podczas kompilowania modelu obiektów lub zewnętrznego pliku mapowania na podstawie bazy danych.  
  
|Typ SQL Server|Domyślne mapowanie typu CLR używane przez projektanta O/R i SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`CHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`NCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`VARCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`NVARCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`TEXT`|<xref:System.String?displayProperty=nameWithType>|  
|`NTEXT`|<xref:System.String?displayProperty=nameWithType>|  
|`XML`|<xref:System.Xml.Linq.XElement?displayProperty=nameWithType>|  
  
 W następnej tabeli przedstawiono domyślne mapowania typów używane przez <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> metodę w celu zdefiniowania typu kolumn SQL do zamapowania na typy CLR zdefiniowane w modelu obiektów lub zewnętrznym pliku mapowania.  
  
|Typ CLR|Domyślny typ SQL Server używany przez <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Char?displayProperty=nameWithType>|`NCHAR(1)`|  
|<xref:System.String?displayProperty=nameWithType>|`NVARCHAR(4000)`|  
|<xref:System.Char?displayProperty=nameWithType>[]|`NVARCHAR(4000)`|  
|Implementacja typu niestandardowego `Parse()` i `ToString()`|`NVARCHAR(MAX)`|  
  
 Istnieje wiele innych mapowań tekstowych i XML, które można wybrać, ale niektóre mogą spowodować przepełnienie lub wyjątki utraty danych podczas tłumaczenia do bazy danych lub z niej. Aby uzyskać więcej informacji, zobacz [macierze zachowania w czasie wykonywania mapowania typu](#BehaviorMatrix).  
  
### <a name="xml-types"></a>Typy XML  

 SQL Server `XML` Typ danych jest dostępny od Microsoft SQL Server 2005. Możesz zmapować SQL Server `XML` Typ danych na <xref:System.Xml.Linq.XElement> , <xref:System.Xml.Linq.XDocument> , lub <xref:System.String> . Jeśli w kolumnie są przechowywane fragmenty XML, których nie można odczytać <xref:System.Xml.Linq.XElement> , należy zamapować kolumnę, aby <xref:System.String> uniknąć błędów w czasie wykonywania. Fragmenty XML, które muszą być mapowane, aby <xref:System.String> uwzględnić następujące elementy:  
  
- Sekwencja elementów XML  
  
- Atrybuty  
  
- Identyfikatory publiczne (PI)  
  
- Komentarze  
  
 Chociaż można mapować <xref:System.Xml.Linq.XElement> i <xref:System.Xml.Linq.XDocument> do SQL Server, jak pokazano w [macierzy zachowania czasu wykonywania mapowania typów](#BehaviorMatrix), metoda nie <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> ma domyślnego mapowania typu SQL Server dla tych typów.  
  
### <a name="custom-types"></a>Typy niestandardowe  

 Jeśli klasa implementuje `Parse()` i `ToString()` , można mapować obiekt na dowolny typ tekstu SQL (,,,,,, `CHAR` `NCHAR` `VARCHAR` `NVARCHAR` `TEXT` `NTEXT` `XML` ). Obiekt jest przechowywany w bazie danych przez wysłanie wartości zwróconej przez `ToString()` do kolumny zamapowanej bazy danych. Obiekt jest tworzony przez wywołanie `Parse()` na ciągu zwracanego przez bazę danych.  
  
> [!NOTE]
> LINQ to SQL nie obsługuje serializacji przy użyciu <xref:System.Xml.Serialization.IXmlSerializable?displayProperty=nameWithType> .  
  
<a name="DateMapping"></a>

## <a name="date-and-time-mapping"></a>Mapowanie daty i godziny  

 Za pomocą LINQ to SQL można mapować wiele SQL Server typów daty i godziny. W poniższej tabeli przedstawiono typy CLR, które Projektant O/R i SQLMetal wybiera podczas kompilowania modelu obiektów lub zewnętrznego pliku mapowania na podstawie bazy danych.  
  
|Typ SQL Server|Domyślne mapowanie typu CLR używane przez projektanta O/R i SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`SMALLDATETIME`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIME`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIME2`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIMEOFFSET`|<xref:System.DateTimeOffset?displayProperty=nameWithType>|  
|`DATE`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`TIME`|<xref:System.TimeSpan?displayProperty=nameWithType>|  
  
 W następnej tabeli przedstawiono domyślne mapowania typów używane przez <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> metodę w celu zdefiniowania typu kolumn SQL do zamapowania na typy CLR zdefiniowane w modelu obiektów lub zewnętrznym pliku mapowania.  
  
|Typ CLR|Domyślny typ SQL Server używany przez <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.DateTime?displayProperty=nameWithType>|`DATETIME`|  
|<xref:System.DateTimeOffset?displayProperty=nameWithType>|`DATETIMEOFFSET`|  
|<xref:System.TimeSpan?displayProperty=nameWithType>|`TIME`|  
  
 Istnieje wiele innych mapowań daty i godziny, które można wybrać, ale niektóre mogą spowodować przepełnienie lub wyjątki utraty danych podczas tłumaczenia do bazy danych lub z niej. Aby uzyskać więcej informacji, zobacz [macierze zachowania w czasie wykonywania mapowania typu](#BehaviorMatrix).  
  
> [!NOTE]
> Typy SQL Server `DATETIME2` ,, `DATETIMEOFFSET` `DATE` i `TIME` są dostępne począwszy od Microsoft SQL Server 2008. LINQ to SQL obsługuje mapowanie na te nowe typy, zaczynając od .NET Framework wersji 3,5 SP1.  
  
### <a name="systemdatetime"></a>System. DateTime  

 Zakres i precyzja <xref:System.DateTime?displayProperty=nameWithType> typu CLR są większe niż zakres i precyzja `DATETIME` typu SQL Server, który jest domyślnym mapowaniem typu dla <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> metody. Aby zapobiec wyjątkom związanym z datami poza zakresem `DATETIME` , użyj `DATETIME2` , który jest dostępny od Microsoft SQL Server 2008. `DATETIME2` może pasować do zakresu i dokładności środowiska CLR <xref:System.DateTime?displayProperty=nameWithType> .  
  
 SQL Server daty nie mają koncepcji <xref:System.TimeZone> , funkcja, która jest w sposób bogaty obsługiwana w środowisku CLR. <xref:System.TimeZone> wartości są zapisywane jako do bazy danych bez <xref:System.TimeZone> konwersji, niezależnie od oryginalnych <xref:System.DateTimeKind> informacji. Gdy <xref:System.DateTime> wartości są pobierane z bazy danych, ich wartości są ładowane w postaci do <xref:System.DateTime> i z <xref:System.DateTimeKind> <xref:System.DateTimeKind.Unspecified> . Aby uzyskać więcej informacji na temat obsługiwanych <xref:System.DateTime?displayProperty=nameWithType> metod, zobacz [metody System. DateTime](system-datetime-methods.md).  
  
### <a name="systemtimespan"></a>System. TimeSpan  

 Microsoft SQL Server 2008 i .NET Framework 3,5 SP1 umożliwiają mapowanie <xref:System.TimeSpan?displayProperty=nameWithType> typu CLR na `TIME` Typ SQL Server. Istnieje jednak duża różnica między zakresem obsługiwanym przez środowisko CLR <xref:System.TimeSpan?displayProperty=nameWithType> a elementem `TIME` obsługiwanym przez typ SQL Server. Mapowanie wartości mniejszej niż 0 lub większej niż 23:59:59.9999999 godziny do bazy danych SQL `TIME` spowoduje przepełnienie wyjątków. Aby uzyskać więcej informacji, zobacz [metody System. TimeSpan](system-timespan-methods.md).  
  
 W Microsoft SQL Server 2000 i SQL Server 2005 nie można mapować pól bazy danych na <xref:System.TimeSpan> . Jednak operacje na <xref:System.TimeSpan> są obsługiwane, ponieważ <xref:System.TimeSpan> wartości mogą być zwracane z <xref:System.DateTime> odejmowania lub wprowadzane do wyrażenia jako literału lub zmiennej powiązanej.  
  
<a name="BinaryMapping"></a>

## <a name="binary-mapping"></a>Mapowanie binarne  

 Istnieje wiele typów SQL Server, które można zamapować na typ CLR <xref:System.Data.Linq.Binary?displayProperty=nameWithType> . W poniższej tabeli przedstawiono typy SQL Server, które powodują, że Projektant O/R i SQLMetal definiują <xref:System.Data.Linq.Binary?displayProperty=nameWithType> typ CLR podczas kompilowania modelu obiektów lub zewnętrznego pliku mapowania na podstawie bazy danych.  
  
|Typ SQL Server|Domyślne mapowanie typu CLR używane przez projektanta O/R i SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`BINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(MAX)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(MAX)` z `FILESTREAM` atrybutem|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`IMAGE`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`TIMESTAMP`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
  
 W następnej tabeli przedstawiono domyślne mapowania typów używane przez <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> metodę w celu zdefiniowania typu kolumn SQL do zamapowania na typy CLR zdefiniowane w modelu obiektów lub zewnętrznym pliku mapowania.  
  
|Typ CLR|Domyślny typ SQL Server używany przez <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
|<xref:System.Byte?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
|<xref:System.Runtime.Serialization.ISerializable?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
  
 Istnieje wiele innych mapowań binarnych, które można wybrać, ale niektóre mogą spowodować przepełnienie lub wyjątki utraty danych podczas tłumaczenia do bazy danych lub z niej. Aby uzyskać więcej informacji, zobacz [macierze zachowania w czasie wykonywania mapowania typu](#BehaviorMatrix).  
  
### <a name="sql-server-filestream"></a>SQL Server FILESTREAM  

 `FILESTREAM`Atrybut dla `VARBINARY(MAX)` kolumn jest dostępny, zaczynając od Microsoft SQL Server 2008; można go mapować do LINQ to SQL, rozpoczynając od .NET Framework wersji 3,5 SP1.  
  
 Chociaż można mapować `VARBINARY(MAX)` kolumny z `FILESTREAM` atrybutem do <xref:System.Data.Linq.Binary> obiektów, <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> Metoda nie może automatycznie tworzyć kolumn z `FILESTREAM` atrybutem. Aby uzyskać więcej informacji na temat `FILESTREAM` , zobacz [FILESTREAM — Omówienie](/previous-versions/sql/sql-server-2008-r2/bb933993(v=sql.105)).  
  
<a name="BinarySerialization"></a>

### <a name="binary-serialization"></a>Serializacja binarna  

 Jeśli klasa implementuje <xref:System.Runtime.Serialization.ISerializable> interfejs, można serializować obiekt do dowolnego pola binarnego SQL ( `BINARY` , `VARBINARY` , `IMAGE` ). Obiekt jest serializowany i deserializowany zgodnie z <xref:System.Runtime.Serialization.ISerializable> zaimplementowanym interfejsem. Aby uzyskać więcej informacji, zobacz [Serializacja binarna](../../../../../standard/serialization/binary-serialization.md).
  
<a name="MiscMapping"></a>

## <a name="miscellaneous-mapping"></a>Mapowanie różne  

 W poniższej tabeli przedstawiono domyślne mapowania typów dla niektórych typów różnych, które nie zostały jeszcze wymienione. W poniższej tabeli przedstawiono typy CLR, które Projektant O/R i SQLMetal wybiera podczas kompilowania modelu obiektów lub zewnętrznego pliku mapowania na podstawie bazy danych.  
  
|Typ SQL Server|Domyślne mapowanie typu CLR używane przez projektanta O/R i SQLMetal|  
|---------------------|-----------------------------------------------------------------|  
|`UNIQUEIDENTIFIER`|<xref:System.Guid?displayProperty=nameWithType>|  
|`SQL_VARIANT`|<xref:System.Object?displayProperty=nameWithType>|  
  
 W następnej tabeli przedstawiono domyślne mapowania typów używane przez <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> metodę w celu zdefiniowania typu kolumn SQL do zamapowania na typy CLR zdefiniowane w modelu obiektów lub zewnętrznym pliku mapowania.  
  
|Typ CLR|Domyślny typ SQL Server używany przez <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Guid?displayProperty=nameWithType>|`UNIQUEIDENTIFIER`|  
|<xref:System.Object?displayProperty=nameWithType>|`SQL_VARIANT`|  
  
 LINQ to SQL nie obsługuje żadnych innych mapowań typów dla tych typów różnych.  Aby uzyskać więcej informacji, zobacz [macierze zachowania w czasie wykonywania mapowania typu](#BehaviorMatrix).  
  
## <a name="see-also"></a>Zobacz też

- [Mapowanie oparte na atrybutach](attribute-based-mapping.md)
- [Mapowanie zewnętrzne](external-mapping.md)
- [Typy danych i funkcje](data-types-and-functions.md)
- [Niezgodność typu SQL CLR](sql-clr-type-mismatches.md)
