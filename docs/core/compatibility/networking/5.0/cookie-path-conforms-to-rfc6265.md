---
title: 'Istotna zmiana: obsługa ścieżki plików cookie jest teraz zgodna ze specyfikacją RFC 6265'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, w której zostały zaimplementowane algorytmy obsługi ścieżek zdefiniowane w RFC 6265 dla klas cookie i CookieContainer.
ms.date: 08/18/2020
ms.openlocfilehash: 4aea06f434c4bbbef7d94b4b39ff647dd954745e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761448"
---
# <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a>Obsługa ścieżki plików cookie jest teraz zgodna ze specyfikacją RFC 6265

Algorytmy obsługi ścieżki zdefiniowane w [dokumencie RFC 6265](https://tools.ietf.org/html/rfc6265) zostały zaimplementowane dla <xref:System.Net.Cookie> <xref:System.Net.CookieContainer> klas i.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="change-description"></a>Zmień opis

- <xref:System.Net.Cookie.Path>Właściwość nie jest już wymagana jako prefiks ścieżki żądania.
- Obliczenia wartości domyślnej <xref:System.Net.Cookie.Path> i algorytmów dopasowywania ścieżek zostały zaimplementowane zgodnie z definicją w [sekcji 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) RFC 6265.

## <a name="recommended-action"></a>Zalecana akcja

W większości przypadków nie trzeba podejmować żadnych działań. Jeśli jednak kod zależał od <xref:System.Net.Cookie.Path> walidacji, należy zaimplementować wymaganą weryfikację w kodzie. Jeśli Twój kod zależał na obliczaniu wartości domyślnej dla <xref:System.Net.Cookie.Path> , rozważ podanie <xref:System.Net.Cookie.Path> wartości ręcznie zamiast używać wartości domyślnej.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

### Category

Networking

-->
