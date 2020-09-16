---
ms.openlocfilehash: e65ba0edb132f5cded244a69d58e43ffea76a039
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606956"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a>Element SqlConnection nie może już łączyć się z SQL Server 1997 lub bazami danych przy użyciu adaptera VIA

#### <a name="details"></a>Szczegóły

Połączenia z bazami danych SQL Server przy użyciu [protokołu wirtualnej karty interfejsu (Via)](/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) nie są już obsługiwane. Protokół używany do nawiązywania połączenia z SQL Server bazą danych jest widoczny w parametrach połączenia. Połączenie TELEFONICZne będzie zawierać: &lt; servername &gt; . Jeśli ta aplikacja nawiązuje połączenie z usługą SQL za pośrednictwem protokołu innego niż VIA (TCP: lub np.), nie zostanie napotkana żadna przerwana zmiana. Ponadto połączenia z SQL Server 7 (1997) nie są już obsługiwane.

#### <a name="suggestion"></a>Sugestia

Protokół VIA jest przestarzały, więc do łączenia się z bazami danych SQL należy używać alternatywnego protokołu. Najczęściej używanym protokołem jest TCP/IP. Aby uzyskać więcej informacji na temat nawiązywania połączenia za pośrednictwem protokołu TCP/IP, zobacz [Włączanie protokołu TCP/IP dla wystąpienia bazy danych](/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)). Jeśli dostęp do bazy danych odbywa się tylko z intranetu, protokół współużytkowanych potoków może zapewnić lepszą wydajność w przypadku powolnej sieci.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)>
- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)>

<!--

#### Affected APIs

- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String)`
- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String,System.Data.SqlClient.SqlCredential)`

-->
