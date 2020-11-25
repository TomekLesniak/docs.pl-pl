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
# <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a><span data-ttu-id="67e85-103">Obsługa ścieżki plików cookie jest teraz zgodna ze specyfikacją RFC 6265</span><span class="sxs-lookup"><span data-stu-id="67e85-103">Cookie path handling now conforms to RFC 6265</span></span>

<span data-ttu-id="67e85-104">Algorytmy obsługi ścieżki zdefiniowane w [dokumencie RFC 6265](https://tools.ietf.org/html/rfc6265) zostały zaimplementowane dla <xref:System.Net.Cookie> <xref:System.Net.CookieContainer> klas i.</span><span class="sxs-lookup"><span data-stu-id="67e85-104">Path-handling algorithms defined in [RFC 6265](https://tools.ietf.org/html/rfc6265) were implemented for the <xref:System.Net.Cookie> and <xref:System.Net.CookieContainer> classes.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="67e85-105">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="67e85-105">Version introduced</span></span>

<span data-ttu-id="67e85-106">5,0</span><span class="sxs-lookup"><span data-stu-id="67e85-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="67e85-107">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="67e85-107">Change description</span></span>

- <span data-ttu-id="67e85-108"><xref:System.Net.Cookie.Path>Właściwość nie jest już wymagana jako prefiks ścieżki żądania.</span><span class="sxs-lookup"><span data-stu-id="67e85-108">The <xref:System.Net.Cookie.Path> property is no longer required to be a prefix of the request path.</span></span>
- <span data-ttu-id="67e85-109">Obliczenia wartości domyślnej <xref:System.Net.Cookie.Path> i algorytmów dopasowywania ścieżek zostały zaimplementowane zgodnie z definicją w [sekcji 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) RFC 6265.</span><span class="sxs-lookup"><span data-stu-id="67e85-109">The calculation of the default value of <xref:System.Net.Cookie.Path> and path-matching algorithms were implemented as defined in [section 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) of RFC 6265.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="67e85-110">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="67e85-110">Recommended action</span></span>

<span data-ttu-id="67e85-111">W większości przypadków nie trzeba podejmować żadnych działań.</span><span class="sxs-lookup"><span data-stu-id="67e85-111">In most cases, you won't need to take any action.</span></span> <span data-ttu-id="67e85-112">Jeśli jednak kod zależał od <xref:System.Net.Cookie.Path> walidacji, należy zaimplementować wymaganą weryfikację w kodzie.</span><span class="sxs-lookup"><span data-stu-id="67e85-112">However, if your code was dependent on <xref:System.Net.Cookie.Path> validation, you'll need to implement required validation in your code.</span></span> <span data-ttu-id="67e85-113">Jeśli Twój kod zależał na obliczaniu wartości domyślnej dla <xref:System.Net.Cookie.Path> , rozważ podanie <xref:System.Net.Cookie.Path> wartości ręcznie zamiast używać wartości domyślnej.</span><span class="sxs-lookup"><span data-stu-id="67e85-113">If your code was dependent on default value calculation for <xref:System.Net.Cookie.Path>, consider supplying the <xref:System.Net.Cookie.Path> value manually instead of using the default value.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="67e85-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="67e85-114">Affected APIs</span></span>

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

### Category

Networking

-->
