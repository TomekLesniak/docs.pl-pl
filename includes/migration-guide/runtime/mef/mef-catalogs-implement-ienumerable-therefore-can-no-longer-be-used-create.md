---
ms.openlocfilehash: 6f22d6211ec9238fd1c7786643ca95db02bfca64
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496397"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>Wykazy MEF implementują interfejs IEnumerable i w związku z tym nie mogą być już używane do tworzenia serializatora

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4,5, wykazy MEF implementują interfejs IEnumerable i w związku z tym nie można już używać do tworzenia serializatora ( <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> obiektu). Próba serializowania katalogu MEF powoduje zgłoszenie wyjątku.

#### <a name="suggestion"></a>Sugestia

Nie można już używać MEF do tworzenia serializatora

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Duży|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
