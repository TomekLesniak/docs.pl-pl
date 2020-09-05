---
ms.openlocfilehash: 26facb645de175d7ef0432394fc2b84f59e8437d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497500"
---
### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a>Kody błędów dla 'Maxrequestlength lub maxReceivedMessageSize są różne

#### <a name="details"></a>Szczegóły

Komunikaty w usługach sieci Web WCF hostowanych w Internet Information Services (IIS) lub ASP.NET Development Server, które przekraczają 'Maxrequestlength (w ASP.NET) lub maxReceivedMessageSize (w programie WCF), mają różne błędy codeThe kod stanu HTTP został zmieniony z 400 (złe żądanie) na 413 (jednostka żądania jest zbyt duża) i komunikaty, które przekraczają albo wartość parametru 'Maxrequestlength lub maxReceivedMessageSize, zgłaszają <xref:System.ServiceModel.ProtocolException?displayProperty=fullName> wyjątek. Obejmuje to przypadki, w których tryb transferu jest przesyłany strumieniowo.

#### <a name="suggestion"></a>Sugestia

Ta zmiana ułatwia debugowanie w przypadkach, gdy długość komunikatu przekracza limity dozwolone przez ASP.NET lub WCF. Należy zmodyfikować każdy kod, który wykonuje przetwarzanie na podstawie kodu stanu HTTP 400.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
