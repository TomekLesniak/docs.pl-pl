---
title: N-warstwowe i zdalne aplikacje z użyciem LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
ms.openlocfilehash: 295be0157c260c05a2e4a7dbbfcd7e5cecbc85de
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548003"
---
# <a name="n-tier-and-remote-applications-with-linq-to-sql"></a>N-warstwowe i zdalne aplikacje z użyciem LINQ to SQL
Można tworzyć aplikacje warstwy n lub wielowarstwowe korzystające z programu [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] . Zazwyczaj [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] kontekst danych, klasy jednostek i logika konstruowania zapytania znajdują się w warstwie środkowej jako warstwa dostępu do danych (dal). Logika biznesowa i wszystkie nietrwałe dane można całkowicie zaimplementować w klasach częściowych i metodach jednostek i kontekście danych albo można je zaimplementować w oddzielnych klasach.

 Klient lub warstwa prezentacji wywołuje metody w interfejsie zdalnym warstwy środkowej, a DAL w tej warstwie wykona zapytania lub procedury składowane, które są mapowane na <xref:System.Data.Linq.DataContext> metody. Warstwa środkowa zwraca dane do klientów zazwyczaj jako reprezentacje XML jednostek lub obiektów proxy.

 W warstwie środkowej jednostki są tworzone przez kontekst danych, który śledzi ich stan i zarządza odroczonym ładowaniem z i przesyłaniem zmian do bazy danych. Te jednostki są "dołączone" do `DataContext` . Jednak po wysłaniu jednostek do innej warstwy przy użyciu serializacji stają się one odłączane, co oznacza, że `DataContext` nie śledzi już stanu. Jednostki wysyłane przez klienta z powrotem do aktualizacji muszą zostać ponownie dołączone do kontekstu danych, zanim będą [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mogły przesłać zmiany do bazy danych. Klient jest odpowiedzialny za dostarczanie oryginalnych wartości i/lub sygnatur czasowych do warstwy środkowej, jeśli są one wymagane do optymistycznych kontroli współbieżności.

 W aplikacjach ASP.NET <xref:System.Web.UI.WebControls.LinqDataSource> zarządza największą z tych złożoności. Aby uzyskać więcej informacji, zobacz [Omówienie kontrolki serwera sieci Web programu LinqDataSource](/previous-versions/aspnet/bb547113(v=vs.100)).

## <a name="additional-resources"></a>Dodatkowe zasoby
 Aby uzyskać więcej informacji na temat implementowania aplikacji n-warstwowych, które korzystają z programu [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , zobacz następujące tematy:

- [N-warstwowa LINQ to SQL z użyciem ASP.NET](linq-to-sql-n-tier-with-aspnet.md)

- [N-warstwowa LINQ to SQL z użyciem usług internetowych](linq-to-sql-n-tier-with-web-services.md)

- [Implementowanie N-warstwowej logiki biznesowej](implementing-business-logic-linq-to-sql.md)

- [Pobieranie danych i operacje CUD w aplikacjach N-warstwowych (LINQ to SQL)](data-retrieval-and-cud-operations-in-n-tier-applications.md)

 Aby uzyskać więcej informacji na temat aplikacji n-warstwowych, które używają zestawów danych ADO.NET, zobacz [Work with datasetss in aplikacje n-warstwowe](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications).

## <a name="see-also"></a>Zobacz także

- [Informacje uzupełniające](background-information.md)
