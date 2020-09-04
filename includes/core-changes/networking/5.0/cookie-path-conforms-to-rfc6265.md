---
ms.openlocfilehash: 7140f6d4cac063088b3663ab98d292104218b542
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465519"
---
### <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a><span data-ttu-id="6744c-101">Obsługa ścieżki plików cookie jest teraz zgodna ze specyfikacją RFC 6265</span><span class="sxs-lookup"><span data-stu-id="6744c-101">Cookie Path handling now conforms to RFC 6265</span></span>

<span data-ttu-id="6744c-102">Algorytmy obsługi ścieżki zdefiniowane w [dokumencie RFC 6265](https://tools.ietf.org/html/rfc6265) zostały zaimplementowane dla <xref:System.Net.Cookie> <xref:System.Net.CookieContainer> klas i.</span><span class="sxs-lookup"><span data-stu-id="6744c-102">Path-handling algorithms defined in [RFC 6265](https://tools.ietf.org/html/rfc6265) were implemented for the <xref:System.Net.Cookie> and <xref:System.Net.CookieContainer> classes.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6744c-103">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="6744c-103">Version introduced</span></span>

<span data-ttu-id="6744c-104">5,0</span><span class="sxs-lookup"><span data-stu-id="6744c-104">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="6744c-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="6744c-105">Change description</span></span>

- <span data-ttu-id="6744c-106"><xref:System.Net.Cookie.Path>Właściwość nie jest już wymagana jako prefiks ścieżki żądania.</span><span class="sxs-lookup"><span data-stu-id="6744c-106">The <xref:System.Net.Cookie.Path> property is no longer required to be a prefix of the request path.</span></span>
- <span data-ttu-id="6744c-107">Obliczenia wartości domyślnej <xref:System.Net.Cookie.Path> i algorytmów dopasowywania ścieżek zostały zaimplementowane zgodnie z definicją w [sekcji 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) RFC 6265.</span><span class="sxs-lookup"><span data-stu-id="6744c-107">The calculation of the default value of <xref:System.Net.Cookie.Path> and path-matching algorithms were implemented as defined in [section 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) of RFC 6265.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6744c-108">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="6744c-108">Recommended action</span></span>

<span data-ttu-id="6744c-109">W większości przypadków nie trzeba podejmować żadnych działań.</span><span class="sxs-lookup"><span data-stu-id="6744c-109">In most cases, you won't need to take any action.</span></span> <span data-ttu-id="6744c-110">Jeśli jednak kod zależał od <xref:System.Net.Cookie.Path> walidacji, należy zaimplementować wymaganą weryfikację w kodzie.</span><span class="sxs-lookup"><span data-stu-id="6744c-110">However, if your code was dependent on <xref:System.Net.Cookie.Path> validation, you'll need to implement required validation in your code.</span></span> <span data-ttu-id="6744c-111">Jeśli Twój kod zależał na obliczaniu wartości domyślnej dla <xref:System.Net.Cookie.Path> , rozważ podanie <xref:System.Net.Cookie.Path> wartości ręcznie zamiast używać wartości domyślnej.</span><span class="sxs-lookup"><span data-stu-id="6744c-111">If your code was dependent on default value calculation for <xref:System.Net.Cookie.Path>, consider supplying the <xref:System.Net.Cookie.Path> value manually instead of using the default value.</span></span>

#### <a name="category"></a><span data-ttu-id="6744c-112">Kategoria</span><span class="sxs-lookup"><span data-stu-id="6744c-112">Category</span></span>

<span data-ttu-id="6744c-113">Networking</span><span class="sxs-lookup"><span data-stu-id="6744c-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6744c-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="6744c-114">Affected APIs</span></span>

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

-->
