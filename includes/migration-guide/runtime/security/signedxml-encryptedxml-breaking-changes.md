---
ms.openlocfilehash: 5c8ea3565fbe599dd53a71ba8bd339704f7d7f8a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497364"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a>Zmiany SignedXml i EncryptedXml

#### <a name="details"></a>Szczegóły

W .NET Framework 4.6.2, poprawki zabezpieczeń w <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> i <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> prowadzą do różnych zachowań w czasie wykonywania. Przykład:<ul><li>Jeśli dokument ma wiele elementów z tym samym <code>id</code> atrybutem, a podpis jednego z tych elementów jako element główny podpisu, dokument będzie teraz traktowany jako nieprawidłowy.</li><li>Dokumenty używające niekanonicznych algorytmów transformacji XPath w odwołaniach są teraz uznawane za nieprawidłowe.</li><li>Dokumenty korzystające z algorytmów transformacji XSLT inne niż kanoniczne w odwołaniach są teraz traktowane jako nieprawidłowe.</li><li>Nie będzie można wykonać żadnego programu korzystającego z odłączonych podpisów zasobów zewnętrznych.</li></ul>

#### <a name="suggestion"></a>Sugestia

Deweloperzy mogą chcieć przejrzeć użycie <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> i <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> , jak również typy pochodne od momentu, gdy <xref:System.Security.Cryptography.Xml.Transform> odbiorca dokumentu może nie być w stanie go przetworzyć.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.6.2|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.Xml.Transform`
- `T:System.Security.Cryptography.Xml.XmlDsigXPathTransform`
- `T:System.Security.Cryptography.Xml.XmlDsigXsltTransform`

-->
