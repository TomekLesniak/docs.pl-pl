---
ms.openlocfilehash: 04d1c1162dc79bbcb0578c6661466f4d58a57acc
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497757"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a>Sqlschemaexception teraz ustawia prawidłowo pozycje wierszy

#### <a name="details"></a>Szczegóły

Jeśli <xref:System.Xml.Linq.LoadOptions.SetLineInfo> wartość jest przenoszona do metody Load i wystąpi błąd walidacji, <xref:System.Xml.Schema.XmlSchemaException.LineNumber> <xref:System.Xml.Schema.XmlSchemaException.LinePosition> właściwości i zawierają teraz informacje o wierszu.

#### <a name="suggestion"></a>Sugestia

Kod obsługi wyjątków, który przyjmuje <xref:System.Xml.Schema.XmlSchemaException.LineNumber> i <xref:System.Xml.Schema.XmlSchemaException.LinePosition> nie zostanie ustawiony, należy zaktualizować, ponieważ te właściwości będą teraz prawidłowo ustawione, gdy SetLineInfo jest używany podczas ładowania kodu XML.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Xml.Linq.LoadOptions.SetLineInfo`

-->
