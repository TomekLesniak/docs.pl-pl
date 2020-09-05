---
ms.openlocfilehash: 9ab1686f60bcdbfef5f18576be17aee8c931f9aa
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496742"
---
### <a name="sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>Element SqlConnection. Open kończy się niepowodzeniem w systemie Windows 7 z obecnym zestawu Winsock lub LSP

#### <a name="details"></a>Szczegóły

<xref:System.Data.SqlClient.SqlConnection.Open> i <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)> Niepowodzenie w .NET Framework 4,5 w przypadku uruchamiania na komputerze z systemem Windows 7, na którym znajdują się na nim zestawu Winsock Aby określić, czy zainstalowano program zestawu Winsock lub LSP, użyj <code>netsh WinSock Show Catalog</code> polecenia i sprawdź każdy <code>Winsock Catalog Provider Entry</code> zwracany element. Jeśli wartość flag usługi ma <code>0x20000</code> ustawiony bit, Dostawca używa dojść IFS i będzie działał poprawnie. Jeśli <code>0x20000</code> bit jest wyczyszczony (nie ustawiono), jest to NIEIFS zestawu Winsock lub LSP.

#### <a name="suggestion"></a>Sugestia

Ta usterka została rozwiązana w .NET Framework 4.5.2, dlatego można ją uniknąć, uaktualniając .NET Framework. Alternatywnie można to uniknąć, usuwając wszystkie zainstalowane Lspy Winsock inne niż IFS.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Data.SqlClient.SqlConnection.Open`
- `M:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)`

-->
