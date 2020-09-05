---
ms.openlocfilehash: bbeca87b3f498213b91d942cc4f197c9d80457a8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497414"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a>Próba połączenia TCP/IP z SQL Server bazą danych, która jest rozpoznawana jako `localhost` Niepowodzenie

#### <a name="details"></a>Szczegóły

W .NET Framework 4,6 i 4.6.1 próbuje nawiązać połączenie TCP/IP z bazą danych SQL Server, która jest rozpoznawana jako <code>localhost</code> błąd, &quot; Wystąpił błąd związany z siecią lub wystąpieniem podczas nawiązywania połączenia z SQL Server. Serwer nie został znaleziony lub był niedostępny. Sprawdź, czy nazwa wystąpienia jest poprawna i czy SQL Server jest skonfigurowany do zezwalania na połączenia zdalne. (Dostawca: interfejsy sieciowe SQL, błąd: 26 — błąd lokalizowania określonego serwera/wystąpienia)&quot;

#### <a name="suggestion"></a>Sugestia

Ten problem został rozwiązany i poprzednie zachowanie zostało przywrócone w .NET Framework 4.6.2. Aby nawiązać połączenie z bazą danych SQL Server, która jest rozpoznawana jako <code>localhost</code> , należy przeprowadzić uaktualnienie do .NET Framework 4.6.2.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4,6|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
