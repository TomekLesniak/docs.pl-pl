---
ms.openlocfilehash: 7140f6d4cac063088b3663ab98d292104218b542
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465519"
---
### <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a>Obsługa ścieżki plików cookie jest teraz zgodna ze specyfikacją RFC 6265

Algorytmy obsługi ścieżki zdefiniowane w [dokumencie RFC 6265](https://tools.ietf.org/html/rfc6265) zostały zaimplementowane dla <xref:System.Net.Cookie> <xref:System.Net.CookieContainer> klas i.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0

#### <a name="change-description"></a>Zmień opis

- <xref:System.Net.Cookie.Path>Właściwość nie jest już wymagana jako prefiks ścieżki żądania.
- Obliczenia wartości domyślnej <xref:System.Net.Cookie.Path> i algorytmów dopasowywania ścieżek zostały zaimplementowane zgodnie z definicją w [sekcji 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) RFC 6265.

#### <a name="recommended-action"></a>Zalecana akcja

W większości przypadków nie trzeba podejmować żadnych działań. Jeśli jednak kod zależał od <xref:System.Net.Cookie.Path> walidacji, należy zaimplementować wymaganą weryfikację w kodzie. Jeśli Twój kod zależał na obliczaniu wartości domyślnej dla <xref:System.Net.Cookie.Path> , rozważ podanie <xref:System.Net.Cookie.Path> wartości ręcznie zamiast używać wartości domyślnej.

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
