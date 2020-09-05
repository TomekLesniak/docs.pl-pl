---
ms.openlocfilehash: ceae6b85c14862b1b1183d01def0dda723ee0c2b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496511"
---
### <a name="ef-no-longer-throws-for-queryviews-with-specific-characteristics"></a>EF nie zgłasza już) obiektów QueryView o określonych cechach

#### <a name="details"></a>Szczegóły

Entity Framework już nie zgłasza <xref:System.StackOverflowException?displayProperty=fullName> wyjątku, gdy aplikacja wykonuje zapytanie, które obejmuje QueryView z właściwością nawigacji 0.. 1, która próbuje dołączyć powiązane jednostki jako część zapytania. Na przykład przez wywołanie metody <code>.Include(e =&gt; e.RelatedNavProp)</code> .

#### <a name="suggestion"></a>Sugestia

Ta zmiana ma wpływ tylko na kod, który używa) obiektów QueryView z 1-0.. 1 relacji podczas wykonywania zapytań wywoływanych przez program. Być. Zwiększa niezawodność i powinien być przejrzysty dla niemal wszystkich aplikacji. Jeśli jednak spowoduje to nieoczekiwane zachowanie, można je wyłączyć, dodając następujący wpis do <code>&lt;appSettings&gt;</code> sekcji w pliku konfiguracji aplikacji:<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyUserSpecifiedViews&quot; value=&quot;false&quot; /&gt;&#13;&#10;</code></pre>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5.2|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
