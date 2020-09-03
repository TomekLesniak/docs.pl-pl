---
ms.openlocfilehash: fdbe8ca9b6dbf24c08a2d041c5c7f2e869995f69
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414460"
---
### <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a><span data-ttu-id="8075f-101">Obsługa ścieżki plików cookie jest teraz zgodna ze specyfikacją RFC 6265</span><span class="sxs-lookup"><span data-stu-id="8075f-101">Cookie Path handling now conforms to RFC 6265</span></span>

<span data-ttu-id="8075f-102">Algorytmy obsługi ścieżki zdefiniowane w [dokumencie RFC 6265](https://tools.ietf.org/html/rfc6265) zostały zaimplementowane dla `Cookie` `CookieContainer` klas i.</span><span class="sxs-lookup"><span data-stu-id="8075f-102">Path handling algorithms defined in [RFC 6265](https://tools.ietf.org/html/rfc6265) were implemented for `Cookie` and `CookieContainer` classes.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8075f-103">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="8075f-103">Version introduced</span></span>

<span data-ttu-id="8075f-104">5,0</span><span class="sxs-lookup"><span data-stu-id="8075f-104">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="8075f-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="8075f-105">Change description</span></span>

- <span data-ttu-id="8075f-106">Ograniczenie dla `Path` atrybutu jest usuwane (nie oczekuje się, że jest to prefiks ścieżki żądania).</span><span class="sxs-lookup"><span data-stu-id="8075f-106">Restriction for the `Path` attribute is removed (it's no longer expected to be a prefix of the request path).</span></span>
- <span data-ttu-id="8075f-107">Obliczenia wartości domyślnej `Path` i algorytmy dopasowywania ścieżek zostały zaimplementowane zgodnie z definicją w [sekcji 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) RFC 6265.</span><span class="sxs-lookup"><span data-stu-id="8075f-107">Calculation of the default value of `Path` and path matching algorithms were implemented as defined in [section 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) of RFC 6265.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8075f-108">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="8075f-108">Recommended action</span></span>

<span data-ttu-id="8075f-109">W większości przypadków nie trzeba podejmować żadnych działań.</span><span class="sxs-lookup"><span data-stu-id="8075f-109">In most cases, you won't need to take any action.</span></span> <span data-ttu-id="8075f-110">Jeśli jednak kod zależał od `Path` walidacji, należy zaimplementować wymaganą weryfikację w kodzie, lub jeśli kod został zależny od `Path` domyślnego obliczenia wartości, można podać `Path` wartość ręcznie zamiast korzystać z wartości domyślnej.</span><span class="sxs-lookup"><span data-stu-id="8075f-110">However, if your code was dependent on `Path` validation you would need to implement required validation in your code; or if your code was dependent on `Path`'s default value calculation, you might want to supply the `Path` value manually instead of using the default value.</span></span>

#### <a name="category"></a><span data-ttu-id="8075f-111">Kategoria</span><span class="sxs-lookup"><span data-stu-id="8075f-111">Category</span></span>

<span data-ttu-id="8075f-112">Networking</span><span class="sxs-lookup"><span data-stu-id="8075f-112">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8075f-113">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="8075f-113">Affected APIs</span></span>

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

-->
