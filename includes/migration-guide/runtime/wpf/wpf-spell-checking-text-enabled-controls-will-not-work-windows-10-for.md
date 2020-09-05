---
ms.openlocfilehash: 6d7f998cda6326e1f584713576a0aa27b3a68655
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497847"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a>Sprawdzanie pisowni WPF w kontrolkach z obsługą tekstu nie będzie działało w systemie Windows 10 dla języków, które nie są na liście języków wejściowych systemu operacyjnego

#### <a name="details"></a>Szczegóły

W przypadku uruchamiania w systemie Windows 10 sprawdzanie pisowni może nie działać w przypadku kontrolek z obsługą tekstu WPF, ponieważ możliwości sprawdzania pisowni platformy są dostępne tylko dla języków znajdujących się na liście języków wejściowych. W systemie Windows 10 po dodaniu języka do listy dostępnych klawiatur system Windows automatycznie pobiera i instaluje odpowiedni pakiet funkcji na żądanie (FDZ), który zapewnia możliwości sprawdzania pisowni. Po dodaniu języka do listy języków wejściowych sprawdzanie pisowni będzie obsługiwane.

#### <a name="suggestion"></a>Sugestia

Należy pamiętać, że język lub tekst do sprawdzenia pisowni należy dodać jako język wejściowy do sprawdzania pisowni w systemie Windows 10.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4,6|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
