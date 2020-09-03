---
ms.openlocfilehash: fdbe8ca9b6dbf24c08a2d041c5c7f2e869995f69
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414460"
---
### <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a>Obsługa ścieżki plików cookie jest teraz zgodna ze specyfikacją RFC 6265

Algorytmy obsługi ścieżki zdefiniowane w [dokumencie RFC 6265](https://tools.ietf.org/html/rfc6265) zostały zaimplementowane dla `Cookie` `CookieContainer` klas i.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0

#### <a name="change-description"></a>Zmień opis

- Ograniczenie dla `Path` atrybutu jest usuwane (nie oczekuje się, że jest to prefiks ścieżki żądania).
- Obliczenia wartości domyślnej `Path` i algorytmy dopasowywania ścieżek zostały zaimplementowane zgodnie z definicją w [sekcji 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) RFC 6265.

#### <a name="recommended-action"></a>Zalecana akcja

W większości przypadków nie trzeba podejmować żadnych działań. Jeśli jednak kod zależał od `Path` walidacji, należy zaimplementować wymaganą weryfikację w kodzie, lub jeśli kod został zależny od `Path` domyślnego obliczenia wartości, można podać `Path` wartość ręcznie zamiast korzystać z wartości domyślnej.

#### <a name="category"></a>Kategoria

Networking

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

-->
