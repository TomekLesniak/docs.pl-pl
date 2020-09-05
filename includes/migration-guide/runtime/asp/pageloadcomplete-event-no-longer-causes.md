---
ms.openlocfilehash: a84d72813a46d6bb39f4710b35d2c9dc859e30ef
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497014"
---
### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>Zdarzenie Page. LoadComplete nie powoduje już wystąpienia elementu System. Web. UI. WebControls. kontrolka EntityDataSource do wywołania powiązania danych

#### <a name="details"></a>Szczegóły

<xref:System.Web.UI.Page.LoadComplete>Zdarzenie nie powoduje już <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> wywołania powiązania danych dla zmian w celu tworzenia/aktualizowania/usuwania parametrów. Ta zmiana eliminuje niezależną podróż do bazy danych, zapobiega resetowaniu wartości formantów oraz tworzy zachowanie zgodne z innymi kontrolkami danych, takimi jak <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> i <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName> . Ta zmiana powoduje inne zachowanie w przypadku, gdy aplikacje są zależne od wywołującego powiązania danych w <xref:System.Web.UI.Page.LoadComplete> zdarzeniu.

#### <a name="suggestion"></a>Sugestia

Jeśli istnieje potrzeba wiązania z danymi, ręcznie Wywołaj wywołanie metody wywołania zwrotnego w zdarzeniu, które jest wcześniej wykonywane po zakończeniu.

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
