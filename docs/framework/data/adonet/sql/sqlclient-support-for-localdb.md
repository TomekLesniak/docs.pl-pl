---
title: Obsługa SqlClient w bazie danych LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 55ab1346de6f5c14f15d01344a984c18edf30e02
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824483"
---
# <a name="sqlclient-support-for-localdb"></a>Obsługa SqlClient w bazie danych LocalDB

W tym artykule omówiono sposób nawiązywania połączenia z bazą danych LocalDB. LocalDB to uproszczona wersja SQL Server.
  
## <a name="remarks"></a>Uwagi
  
 Aby podsumować, co możesz zrobić z LocalDB:  
  
- Twórz i uruchamiaj wystąpienia LocalDB za pomocą sqllocaldb.exe lub pliku app.config.  
  
- Użyj sqlcmd.exe, aby dodać i zmodyfikować bazy danych w wystąpieniu LocalDB. Na przykład `sqlcmd -S (localdb)\myinst`.  
  
- Użyj `AttachDBFilename` słowa kluczowego Connection, aby dodać bazę danych do wystąpienia usługi LocalDB. Jeśli używasz `AttachDBFilename` , jeśli nie określisz nazwy bazy danych za pomocą `Database` słowa kluczowego Connection, baza danych zostanie usunięta z wystąpienia LocalDB, gdy aplikacja zostanie zamknięta.  
  
- Określ wystąpienie LocalDB w parametrach połączenia. Na przykład nazwa wystąpienia to `myInstance` , ciąg połączenia:  
  
    `server=(localdb)\\myInstance`  
  
 `User Instance=True` nie jest dozwolone podczas nawiązywania połączenia z bazą danych LocalDB.  
  
Informacje o instalowaniu LocalDB można znaleźć w temacie [SQL Server Express LocalDB](/sql/database-engine/configure-windows/sql-server-express-localdb).
  
## <a name="programmatically-create-a-named-instance"></a>Programowe tworzenie nazwanego wystąpienia  

 Aplikacja może utworzyć nazwane wystąpienie i określić bazę danych w następujący sposób:  
  
- Określ wystąpienia LocalDB do utworzenia w pliku app.config w następujący sposób.  Numer wersji wystąpienia powinien być taki sam jak numer wersji instalacji programu LocalDB.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
- Określ nazwę wystąpienia za pomocą `server` słowa kluczowego parametrów połączenia.  Nazwa wystąpienia określona w `server` słowie kluczowym parametrów połączenia musi być zgodna z nazwą określoną w pliku app.config.  
  
- Użyj `AttachDBFilename` słowa kluczowego Connection, aby określić. Plik MDF.  
  
## <a name="see-also"></a>Zobacz także

- [Funkcje Serwera SQL i ADO.NET](sql-server-features-and-adonet.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
