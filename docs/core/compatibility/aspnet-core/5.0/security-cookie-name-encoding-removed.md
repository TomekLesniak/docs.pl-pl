---
title: 'Zmiana podziału: zabezpieczenia: kodowanie nazw plików cookie zostało usunięte'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 z tytułem zabezpieczeń: kodowanie nazwy pliku cookie zostało usunięte'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 3cd40d2b04d0cdf0863e3a3fb6d790c2b35692bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761692"
---
# <a name="security-cookie-name-encoding-removed"></a><span data-ttu-id="88fde-103">Zabezpieczenia: kodowanie nazwy pliku cookie zostało usunięte</span><span class="sxs-lookup"><span data-stu-id="88fde-103">Security: Cookie name encoding removed</span></span>

<span data-ttu-id="88fde-104">[Standard plików cookie protokołu HTTP](https://tools.ietf.org/html/rfc6265#section-4.1.1) zezwala tylko na określone znaki w nazwach i wartościach plików cookie.</span><span class="sxs-lookup"><span data-stu-id="88fde-104">The [HTTP cookie standard](https://tools.ietf.org/html/rfc6265#section-4.1.1) allows only specific characters in cookie names and values.</span></span> <span data-ttu-id="88fde-105">Aby zapewnić obsługę niedozwolonych znaków, ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="88fde-105">To support disallowed characters, ASP.NET Core:</span></span>

* <span data-ttu-id="88fde-106">Kodowanie podczas tworzenia pliku cookie odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="88fde-106">Encodes when creating a response cookie.</span></span>
* <span data-ttu-id="88fde-107">Dekoduje podczas odczytywania pliku cookie żądania.</span><span class="sxs-lookup"><span data-stu-id="88fde-107">Decodes when reading a request cookie.</span></span>

<span data-ttu-id="88fde-108">W ASP.NET Core 5,0 to zachowanie kodowania zostało zmienione w odpowiedzi na problem z zabezpieczeniami.</span><span class="sxs-lookup"><span data-stu-id="88fde-108">In ASP.NET Core 5.0, this encoding behavior changed in response to a security concern.</span></span>

<span data-ttu-id="88fde-109">Aby zapoznać się z omówieniem, zobacz sekcję dotyczącą usługi GitHub wydaj [/aspnetcore # 23578](https://github.com/dotnet/aspnetcore/issues/23578).</span><span class="sxs-lookup"><span data-stu-id="88fde-109">For discussion, see GitHub issue [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="88fde-110">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="88fde-110">Version introduced</span></span>

<span data-ttu-id="88fde-111">5,0 wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="88fde-111">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="88fde-112">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="88fde-112">Old behavior</span></span>

<span data-ttu-id="88fde-113">Nazwy plików cookie odpowiedzi są zakodowane.</span><span class="sxs-lookup"><span data-stu-id="88fde-113">Response cookie names are encoded.</span></span> <span data-ttu-id="88fde-114">Nazwy plików cookie żądania są zdekodowane.</span><span class="sxs-lookup"><span data-stu-id="88fde-114">Request cookie names are decoded.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="88fde-115">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="88fde-115">New behavior</span></span>

<span data-ttu-id="88fde-116">Kodowanie i dekodowanie nazw plików cookie zostało usunięte.</span><span class="sxs-lookup"><span data-stu-id="88fde-116">Encoding and decoding of cookie names was removed.</span></span> <span data-ttu-id="88fde-117">W przypadku wcześniejszych [obsługiwanych wersji](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ASP.NET Core zespół planuje wyeliminować problem związany z dekodowaniem.</span><span class="sxs-lookup"><span data-stu-id="88fde-117">For prior [supported versions](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) of ASP.NET Core, the team plans to mitigate the decoding issue in-place.</span></span> <span data-ttu-id="88fde-118">Ponadto wywołanie <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> z nieprawidłową nazwą pliku cookie zgłasza wyjątek typu <xref:System.ArgumentException> .</span><span class="sxs-lookup"><span data-stu-id="88fde-118">Additionally, calling <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> with an invalid cookie name throws an exception of type <xref:System.ArgumentException>.</span></span> <span data-ttu-id="88fde-119">Kodowanie i dekodowanie wartości plików cookie pozostaje niezmienione.</span><span class="sxs-lookup"><span data-stu-id="88fde-119">Encoding and decoding of cookie values remains unchanged.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="88fde-120">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="88fde-120">Reason for change</span></span>

<span data-ttu-id="88fde-121">Wykryto problem w [wielu strukturach sieci Web](https://github.com/advisories/GHSA-j6w9-fv6q-3q52).</span><span class="sxs-lookup"><span data-stu-id="88fde-121">An issue was discovered in [multiple web frameworks](https://github.com/advisories/GHSA-j6w9-fv6q-3q52).</span></span> <span data-ttu-id="88fde-122">Kodowanie i dekodowanie może umożliwić atakującemu obejście funkcji zabezpieczeń o nazwie [prefiksy plików cookie](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) przez sfałszowanie zarezerwowanych prefiksów, takich jak `__Host-` z wartościami zakodowanymi, takimi jak `__%48ost-` .</span><span class="sxs-lookup"><span data-stu-id="88fde-122">The encoding and decoding could allow an attacker to bypass a security feature called [cookie prefixes](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) by spoofing reserved prefixes like `__Host-` with encoded values like `__%48ost-`.</span></span> <span data-ttu-id="88fde-123">Atak wymaga dodatkowego luki w zabezpieczeniach w celu dodania sfałszowanych plików cookie, takich jak usterka skryptów między lokacjami (XSS), w witrynie sieci Web.</span><span class="sxs-lookup"><span data-stu-id="88fde-123">The attack requires a secondary exploit to inject the spoofed cookies, such as a cross-site scripting (XSS) vulnerability, in the website.</span></span> <span data-ttu-id="88fde-124">Te prefiksy nie są domyślnie używane w ASP.NET Core lub `Microsoft.Owin` bibliotekach lub szablonach.</span><span class="sxs-lookup"><span data-stu-id="88fde-124">These prefixes aren't used by default in ASP.NET Core or `Microsoft.Owin` libraries or templates.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="88fde-125">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="88fde-125">Recommended action</span></span>

<span data-ttu-id="88fde-126">Jeśli przenosisz projekty do ASP.NET Core 5,0 lub nowszego, upewnij się, że ich nazwy plików cookie są zgodne z [wymaganiami dotyczącymi specyfikacji tokenu](https://tools.ietf.org/html/rfc2616#section-2.2): znaki ASCII z wyjątkiem formantów i separatorów `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT` .</span><span class="sxs-lookup"><span data-stu-id="88fde-126">If you're moving projects to ASP.NET Core 5.0 or later, ensure that their cookie names conform to the [token specification requirements](https://tools.ietf.org/html/rfc2616#section-2.2): ASCII characters excluding controls and separators `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`.</span></span> <span data-ttu-id="88fde-127">Użycie znaków innych niż ASCII w nazwach plików cookie lub innych nagłówkach HTTP może spowodować wystąpienie wyjątku z serwera lub być niepoprawnie przeprowadzona przez klienta.</span><span class="sxs-lookup"><span data-stu-id="88fde-127">The use of non-ASCII characters in cookie names or other HTTP headers may cause an exception from the server or be improperly round-tripped by the client.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="88fde-128">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="88fde-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.HttpRequest.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpResponse.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinRequest.Cookies?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinResponse.Cookies?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.HttpRequest.Cookies`
- `Overload:Microsoft.AspNetCore.Http.HttpResponse.Cookies`
- `P:Microsoft.Owin.IOwinRequest.Cookies`
- `P:Microsoft.Owin.IOwinResponse.Cookies`

-->
