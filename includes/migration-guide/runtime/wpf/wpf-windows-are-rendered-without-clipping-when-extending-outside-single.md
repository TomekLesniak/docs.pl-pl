---
ms.openlocfilehash: a133c2ea48df11915f8708029c70549e8a1ccefd
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497619"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a>Okna WPF są renderowane bez obcinania podczas rozszerzania poza pojedynczy monitor

#### <a name="details"></a>Szczegóły

W .NET Framework 4,6 działający w systemie Windows 8 i nowszych całe okno jest renderowane bez przycinania, gdy rozciąga się poza pojedynczym ekranem w scenariuszu z obsługą kilku monitorów. Różni się to od poprzednich wersji .NET Framework, które powinny wyciąć okna WPF, które przekroczą pojedynczy ekran.

#### <a name="suggestion"></a>Sugestia

Takie zachowanie (bez względu na to, czy ma być obcinane czy nie) można jawnie ustawić przy użyciu <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> elementu w <code>&lt;appSettings&gt;</code> pliku konfiguracyjnym aplikacji lub przez ustawienie <code>EnableMultiMonitorDisplayClipping</code> właściwości przy uruchamianiu aplikacji.

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
