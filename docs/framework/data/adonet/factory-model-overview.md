---
title: Omówienie modelu fabryki
ms.date: 03/30/2017
ms.assetid: b5dc81c4-7554-44b9-b513-769bd61e2e7b
ms.openlocfilehash: 7cee3966ab3a37d2dbc6dd0ea9ab26b485ef63fd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156397"
---
# <a name="factory-model-overview"></a>Omówienie modelu fabryki

W ADO.NET 2,0 wprowadzono nowe klasy bazowe w <xref:System.Data.Common> przestrzeni nazw. Klasy podstawowe są abstrakcyjne, co oznacza, że nie można ich bezpośrednio utworzyć. Obejmują one <xref:System.Data.Common.DbConnection> , <xref:System.Data.Common.DbCommand> i <xref:System.Data.Common.DbDataAdapter> i są współużytkowane przez dostawców danych .NET Framework, takich jak <xref:System.Data.SqlClient> i <xref:System.Data.OleDb> . Dodanie klas bazowych upraszcza Dodawanie funkcji do .NET Framework dostawców danych bez konieczności tworzenia nowych interfejsów.  
  
 W ADO.NET 2,0 wprowadzono również abstrakcyjne klasy podstawowe, które umożliwiają deweloperowi pisanie ogólnego kodu dostępu do danych, który nie zależy od określonego dostawcy danych.  
  
## <a name="the-factory-design-pattern"></a>Wzorzec projektowy fabryki  

 Model programowania służący do pisania kodu niezależnego od dostawcy jest oparty na użyciu wzorca projektowego "Factory", który używa jednego interfejsu API do uzyskiwania dostępu do baz danych przez wielu dostawców. Ten wzorzec to aptly o nazwie, ponieważ wywołuje użycie wyspecjalizowanego obiektu wyłącznie do tworzenia innych obiektów, podobnie jak w przypadku fabryki rzeczywistej. Aby zapoznać się z bardziej szczegółowym opisem wzorca projektowego, zobacz [pisanie ogólnego kodu dostępu do danych w ASP.NET 2,0 i ADO.NET 2,0](/previous-versions/dotnet/articles/ms971499(v=msdn.10)).
  
 Począwszy od ADO.NET 2,0, <xref:System.Data.Common.DbProviderFactories> Klasa zawiera `static` metody (lub `Shared` w Visual Basic) do tworzenia <xref:System.Data.Common.DbProviderFactory> wystąpienia. Wystąpienie zwraca poprawną silnie wpisaną obiekt na podstawie informacji o dostawcy i parametrów połączenia dostarczonych w czasie wykonywania.  
  
## <a name="see-also"></a>Zobacz też

- [Uzyskiwanie DbProviderFactory](obtaining-a-dbproviderfactory.md)
- [DbConnection, DbCommand i DbException](dbconnection-dbcommand-and-dbexception.md)
- [Modyfikowanie danych za pomocą obiektu DbDataAdapter](modifying-data-with-a-dbdataadapter.md)
- [Omówienie ADO.NET](ado-net-overview.md)
