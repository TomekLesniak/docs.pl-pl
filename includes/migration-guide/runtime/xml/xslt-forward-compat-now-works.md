---
ms.openlocfilehash: 8c8477ae3719cfcc2060459ba85bcc9e76f11c41
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497922"
---
### <a name="xslt-forward-compat-now-works"></a>Teraz działa progresywne przekształcenie XSLT

#### <a name="details"></a>Szczegóły

W .NET Framework 4, przexslt 1,0 do przodu ma następujące problemy:<ul><li>Ładowanie arkusza stylów kończyło się niepowodzeniem, jeśli jego wersja miała wartość 2.0, a analizator napotkał nierozpoznaną konstrukcję specyfikacji XSLT 1.0.</li><li><code>xsl:sort</code>Konstrukcja nie może sortować danych, jeśli ustawiono wersję arkusza stylów na 1,1.</li></ul>W .NET Framework 4,5 te problemy zostały rozwiązane, a tryb zgodności z przekazywaniem do przodu XSLT 1,0 działa prawidłowo.

#### <a name="suggestion"></a>Sugestia

W przypadku większości aplikacji nie ma to żadnego oddziaływania, jednak w niektórych przypadkach dane będą sortowane w różny sposób, gdy jest to kod XSL: sort. Jeśli <code>xsl:sort</code> jest używany w arkuszach stylów 1,1, potwierdź, że aplikacje nie były w zależności od kolejności danych. Jeśli aplikacje są zależne od zachowania sortowania 4,0, Usuń <code>xsl:sort</code> z arkusza stylów.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Xml.Xsl.XslCompiledTransform`

-->
