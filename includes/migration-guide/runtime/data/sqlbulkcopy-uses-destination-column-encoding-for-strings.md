---
ms.openlocfilehash: fd9f4f3de8f7be39242d4ff6924d480f20a1a06b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497085"
---
### <a name="sqlbulkcopy-uses-destination-column-encoding-for-strings"></a>SqlBulkCopy używa kodowania kolumn docelowych dla ciągów

#### <a name="details"></a>Szczegóły

Podczas wstawiania danych do kolumny program <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> używa kodowania kolumny docelowej zamiast domyślnego kodowania dla <code>VARCHAR</code> <code>CHAR</code> typów i. Ta zmiana eliminuje możliwość uszkodzenia danych na skutek użycia domyślnego kodowania w sytuacji, gdy w kolumnie docelowej nie jest używane kodowanie domyślne. W rzadkich przypadkach istniejąca aplikacja może zgłosić wyjątek SqlException, jeśli zmiana kodowania powoduje, że dane są zbyt duże, aby mieściły się w kolumnie docelowej.

#### <a name="suggestion"></a>Sugestia

Należy oczekiwać, że <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> dane nie będą już uszkodzone z powodu różnic między kodowaniem. Jeśli są kopiowane ciągi bliskie rozmiaru kolumny docelowej, może być konieczne przeprowadzenie wstępnej kodowania danych (do skopiowania w celu sprawdzenia, czy dane zmieszczą się w kolumnie docelowej), czy do przechwycenia <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> .

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)>

<!--

#### Affected APIs

- `T:System.Data.SqlClient.SqlBulkCopy`
- `M:System.Data.SqlClient.SqlBulkCopy.#ctor(System.Data.SqlClient.SqlConnection)`

-->
