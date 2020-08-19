---
ms.openlocfilehash: cf51d5f6b3eee7189fd9613b3d780a829d197a04
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558010"
---
### <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a>System. Security. Cryptography. OID jest funkcjonalnie init-Only

<xref:System.Security.Cryptography.Oid?displayProperty=fullName>Klasa, która jest używana do reprezentowania wartości identyfikatora obiektu ASN. 1 oraz ich "przyjaznych" nazw, była poprzednio w pełni modyfikowalna. Ten zmienność był często zaszukiwany lub nieoczekiwany. Metody ustawiające właściwości teraz generują <xref:System.PlatformNotSupportedException> podczas próby zmiany wartości po jej przypisaniu.

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach metody ustawiające właściwości on <xref:System.Security.Cryptography.Oid> mogą służyć do zmiany wartości <xref:System.Security.Cryptography.Oid.FriendlyName> <xref:System.Security.Cryptography.Oid.Value> właściwości i.

W programie .NET 5,0 i nowszych wersjach metody ustawiające właściwości mogą być używane tylko w celu zainicjowania wartości. Gdy właściwość ma wartość, albo z konstruktora lub poprzedniego wywołania metody ustawiającej właściwość, Metoda ustawiająca Właściwość zawsze zgłasza <xref:System.PlatformNotSupportedException> .

#### <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana umożliwia ponowne użycie <xref:System.Security.Cryptography.Oid> obiektów jako część wartości zwracanych w publicznych interfejsach API w celu zmniejszenia profilów alokacji obiektów. Pozwala to uniknąć konieczności tworzenia tymczasowych kopii "obronnych", gdy <xref:System.Security.Cryptography.Oid> wartości są używane jako dane wejściowe.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 wersja zapoznawcza 8

#### <a name="recommended-action"></a>Zalecana akcja

Unikaj używania metod <xref:System.Security.Cryptography.Oid> ustawiających właściwości innych niż w przypadku inicjowania obiektu. Aby reprezentować nową wartość, Użyj nowego wystąpienia zamiast zmieniać wartość istniejącego obiektu.

#### <a name="category"></a>Kategoria

Kryptografia

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

-->
