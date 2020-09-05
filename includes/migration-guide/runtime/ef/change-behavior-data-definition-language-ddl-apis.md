---
ms.openlocfilehash: 4416a7c09f2d163961fe2fe3d6dfaa8bd5e66f93
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497914"
---
### <a name="change-in-behavior-in-data-definition-language-ddl-apis"></a>Zmiana zachowania w interfejsie API języka definicji danych (DDL)

#### <a name="details"></a>Szczegóły

Zachowanie interfejsów API DDL po określeniu AttachDBFilename zmieniło się w następujący sposób:<ul><li>Parametry połączenia nie muszą określać początkowej wartości katalogu. Wcześniej są wymagane zarówno AttachDBFilename, jak i katalog początkowy.</li><li>Jeśli określono zarówno AttachDBFilename, jak i katalog początkowy, a dany plik MDF istnieje, <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A> Metoda zwraca <code>true</code> . Wcześniej zwrócone <code>false</code> .</li><li>Jeśli określono zarówno AttachDBFilename, jak i katalog początkowy, a dany plik MDF istnieje, wywołanie <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> metody spowoduje usunięcie plików.</li><li>Jeśli <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> jest wywoływana, gdy parametry połączenia określają wartość AttachDBFileName z MDF, która nie istnieje i początkowy wykaz, który nie istnieje, metoda zgłasza <xref:System.InvalidOperationException> wyjątek. Wcześniej wywołał <xref:System.Data.SqlClient.SqlException> wyjątek.</li></ul>

#### <a name="suggestion"></a>Sugestia

Te zmiany ułatwiają tworzenie narzędzi i aplikacji używających interfejsów API języka DDL. Te zmiany mogą wpływać na zgodność aplikacji w następujących scenariuszach:<ul><li>Użytkownik zapisuje kod, który wykonuje <code>DROP DATABASE</code> polecenie bezpośrednio, zamiast wywołania <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> if <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A> Returns <code>true</code> . Przerywa to działanie istniejącego kodu, jeśli baza danych nie jest dołączona, ale plik MDF istnieje.</li><li>Użytkownik zapisuje kod, który oczekuje <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> metody do wygenerowania a, a nie do <xref:System.Data.SqlClient.SqlException> <xref:System.InvalidOperationException> momentu, gdy katalog początkowy i plik MDF nie istnieją.</li></ul>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
