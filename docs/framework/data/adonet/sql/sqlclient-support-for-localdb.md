---
title: Obsługa SqlClient w bazie danych LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 841c455605b0b32668d26cab16a6207dc1c0f716
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203426"
---
# <a name="sqlclient-support-for-localdb"></a>Obsługa SqlClient w bazie danych LocalDB

Począwszy od SQL Server nazwy Denali, zostanie udostępniona uproszczona wersja SQL Server o nazwie LocalDB. W tym temacie omówiono sposób nawiązywania połączenia z bazą danych LocalDB.  
  
## <a name="remarks"></a>Uwagi  

 Aby uzyskać więcej informacji na temat LocalDB, w tym sposobu instalowania LocalDB i konfigurowania wystąpienia LocalDB, zobacz SQL Server Books Online.  
  
 Aby podsumować, co możesz zrobić z LocalDB:  
  
- Twórz i uruchamiaj wystąpienia LocalDB za pomocą sqllocaldb.exe lub pliku app.config.  
  
- Użyj sqlcmd.exe, aby dodać i zmodyfikować bazy danych w wystąpieniu LocalDB. Na przykład `sqlcmd -S (localdb)\myinst`.  
  
- Użyj `AttachDBFilename` słowa kluczowego Connection, aby dodać bazę danych do wystąpienia usługi LocalDB. Jeśli używasz `AttachDBFilename` , jeśli nie określisz nazwy bazy danych za pomocą `Database` słowa kluczowego Connection, baza danych zostanie usunięta z wystąpienia LocalDB, gdy aplikacja zostanie zamknięta.  
  
- Określ wystąpienie LocalDB w parametrach połączenia. Na przykład nazwa wystąpienia to `myInstance` , ciąg połączenia:  
  
    `server=(localdb)\\myInstance`  
  
 `User Instance=True` nie jest dozwolone podczas nawiązywania połączenia z bazą danych LocalDB.  
  
 Możesz pobrać LocalDB z [pakietu Feature Pack Microsoft SQL Server 2012](https://www.microsoft.com/download/en/details.aspx?id=29065). Jeśli będziesz używać sqlcmd.exe do modyfikowania danych w wystąpieniu usługi LocalDB, będziesz potrzebować narzędzia sqlcmd z SQL Server 2012, które można także pobrać z pakietu funkcji SQL Server 2012.  
  
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
  
## <a name="see-also"></a>Zobacz też

- [Funkcje Serwera SQL i ADO.NET](sql-server-features-and-adonet.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
