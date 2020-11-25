---
title: 'Istotna zmiana: domyślne mechanizmy szyfrowania TLS dla platformy .NET w systemie Linux'
description: Dowiedz się więcej o istotnej zmianie w programie .NET 5,0, w której platforma .NET w systemie Linux uwzględnia konfigurację OpenSSL dla domyślnych mechanizmów szyfrowania podczas przeprowadzania protokołów TLS/SSL.
ms.date: 10/16/2020
ms.openlocfilehash: f1c23517161ac213a9cd7cf6e7da8eebeb91583b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761320"
---
# <a name="default-tls-cipher-suites-for-net-on-linux"></a><span data-ttu-id="ff943-103">Domyślne mechanizmy szyfrowania TLS dla platformy .NET w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="ff943-103">Default TLS cipher suites for .NET on Linux</span></span>

<span data-ttu-id="ff943-104">Platforma .NET w systemie Linux uwzględnia teraz konfigurację OpenSSL dla domyślnych mechanizmów szyfrowania podczas wykonywania protokołu TLS/SSL za pośrednictwem <xref:System.Net.Security.SslStream> klasy lub operacji wyższego poziomu, takich jak https za pośrednictwem <xref:System.Net.Http.HttpClient> klasy.</span><span class="sxs-lookup"><span data-stu-id="ff943-104">.NET, on Linux, now respects the OpenSSL configuration for default cipher suites when doing TLS/SSL via the <xref:System.Net.Security.SslStream> class or higher-level operations, such as HTTPS via the <xref:System.Net.Http.HttpClient> class.</span></span> <span data-ttu-id="ff943-105">Jeśli domyślne mechanizmy szyfrowania nie są skonfigurowane jawnie, platforma .NET w systemie Linux używa ściśle ograniczonej listy dozwolonych mechanizmów szyfrowania.</span><span class="sxs-lookup"><span data-stu-id="ff943-105">When default cipher suites aren't explicitly configured, .NET on Linux uses a tightly restricted list of permitted cipher suites.</span></span>

## <a name="change-description"></a><span data-ttu-id="ff943-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="ff943-106">Change description</span></span>

<span data-ttu-id="ff943-107">W poprzednich wersjach .NET program .NET nie szanuje konfiguracji systemu dla domyślnych mechanizmów szyfrowania.</span><span class="sxs-lookup"><span data-stu-id="ff943-107">In previous .NET versions, .NET does not respect system configuration for default cipher suites.</span></span> <span data-ttu-id="ff943-108">Domyślna lista mechanizmów szyfrowania dla platformy .NET w systemie Linux jest bardzo zależna.</span><span class="sxs-lookup"><span data-stu-id="ff943-108">The default cipher suite list for .NET on Linux is very permissive.</span></span>

<span data-ttu-id="ff943-109">Począwszy od platformy .NET 5,0, .NET w systemie Linux uwzględnia konfigurację OpenSSL dla domyślnych mechanizmów szyfrowania, gdy jest ona określona w *OpenSSL. cnf*.</span><span class="sxs-lookup"><span data-stu-id="ff943-109">Starting in .NET 5.0, .NET on Linux respects the OpenSSL configuration for default cipher suites when it's specified in *openssl.cnf*.</span></span> <span data-ttu-id="ff943-110">Jeśli mechanizmy szyfrowania nie są jawnie skonfigurowane, Jedynymi dozwolonymi mechanizmami szyfrowania są następujące:</span><span class="sxs-lookup"><span data-stu-id="ff943-110">When cipher suites aren't explicitly configured, the only permitted cipher suites are as follows:</span></span>

- <span data-ttu-id="ff943-111">Mechanizmy szyfrowania TLS 1,3</span><span class="sxs-lookup"><span data-stu-id="ff943-111">TLS 1.3 cipher suites</span></span>
- <span data-ttu-id="ff943-112">TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384</span><span class="sxs-lookup"><span data-stu-id="ff943-112">TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384</span></span>
- <span data-ttu-id="ff943-113">TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256</span><span class="sxs-lookup"><span data-stu-id="ff943-113">TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256</span></span>
- <span data-ttu-id="ff943-114">TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384</span><span class="sxs-lookup"><span data-stu-id="ff943-114">TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384</span></span>
- <span data-ttu-id="ff943-115">TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256</span><span class="sxs-lookup"><span data-stu-id="ff943-115">TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256</span></span>
- <span data-ttu-id="ff943-116">TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384</span><span class="sxs-lookup"><span data-stu-id="ff943-116">TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384</span></span>
- <span data-ttu-id="ff943-117">TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="ff943-117">TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256</span></span>
- <span data-ttu-id="ff943-118">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384</span><span class="sxs-lookup"><span data-stu-id="ff943-118">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384</span></span>
- <span data-ttu-id="ff943-119">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="ff943-119">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256</span></span>

<span data-ttu-id="ff943-120">Ponieważ ta wartość domyślna nie obejmuje żadnych mechanizmów szyfrowania, które są zgodne z protokołem TLS 1,0 lub TLS 1,1, te starsze wersje protokołów są skutecznie wyłączone.</span><span class="sxs-lookup"><span data-stu-id="ff943-120">Since this fallback default doesn't include any cipher suites that are compatible with TLS 1.0 or TLS 1.1, these older protocol versions are effectively disabled by default.</span></span>

<span data-ttu-id="ff943-121">Dostarczenie wartości CipherSuitePolicy do SslStream dla określonej sesji nadal zastępuje zawartość pliku konfiguracji i/lub wartość domyślną dla platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="ff943-121">Supplying a CipherSuitePolicy value to SslStream for a specific session will still replace the configuration file content and/or .NET fallback default.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ff943-122">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="ff943-122">Reason for change</span></span>

<span data-ttu-id="ff943-123">Użytkownicy korzystający z platformy .NET w systemie Linux zażądali zmiany konfiguracji domyślnej na <xref:System.Net.Security.SslStream> taką, która zapewnia wysoką ocenę zabezpieczeń z narzędzi do oceny innych firm.</span><span class="sxs-lookup"><span data-stu-id="ff943-123">Users running .NET on Linux requested that the default configuration for <xref:System.Net.Security.SslStream> be changed to one that provided a high security rating from third-party assessment tools.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ff943-124">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="ff943-124">Version introduced</span></span>

<span data-ttu-id="ff943-125">5,0</span><span class="sxs-lookup"><span data-stu-id="ff943-125">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ff943-126">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="ff943-126">Recommended action</span></span>

<span data-ttu-id="ff943-127">Nowe wartości domyślne mogą być wykonywane podczas komunikowania się z nowoczesnymi klientami lub serwerami.</span><span class="sxs-lookup"><span data-stu-id="ff943-127">The new defaults are likely to work when communicating with modern clients or servers.</span></span> <span data-ttu-id="ff943-128">Jeśli musisz rozwinąć listę domyślnych pakietów szyfrowania, aby akceptować starszych klientów (lub aby skontaktować się z starszymi serwerami), określ `CipherSuitePolicy` wartość lub Zmień plik konfiguracji OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="ff943-128">If you need to expand the default cipher suite list to accept legacy clients (or to contact legacy servers), either specify a `CipherSuitePolicy` value or change the OpenSSL configuration file.</span></span> <span data-ttu-id="ff943-129">W przypadku wielu dystrybucji systemu Linux plik konfiguracji OpenSSL ma */etc/SSL/OpenSSL.cnf*.</span><span class="sxs-lookup"><span data-stu-id="ff943-129">On many Linux distributions, the OpenSSL configuration file is at */etc/ssl/openssl.cnf*.</span></span>

<span data-ttu-id="ff943-130">Ten przykładowy plik *OpenSSL. cnf* jest minimalnym plikiem równoważnym z domyślnymi zasadami szyfrowania dla platformy .NET 5,0 i nowszych w systemie Linux.</span><span class="sxs-lookup"><span data-stu-id="ff943-130">This sample *openssl.cnf* file is a minimal file that's equivalent to the default cipher suites policy for .NET 5.0 and later on Linux.</span></span> <span data-ttu-id="ff943-131">Zamiast zamieniać plik systemowy, należy scalić te koncepcje z plikiem, który jest obecny w systemie.</span><span class="sxs-lookup"><span data-stu-id="ff943-131">Instead of replacing the system file, merge these concepts with the file that's present on your system.</span></span>

```ini
openssl_conf = default_conf

[default_conf]
ssl_conf = ssl_sect

[ssl_sect]
system_default = system_default_sect

[system_default_sect]
CipherString = ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES256-SHA384:ECDHE-RSA-AES128-SHA256
```

<span data-ttu-id="ff943-132">W przypadku Red Hat Enterprise Linux, CentOS i dystrybucji Fedora domyślnie aplikacje platformy .NET są mechanizmami szyfrowania dozwolonymi przez zasady kryptograficzne całego systemu.</span><span class="sxs-lookup"><span data-stu-id="ff943-132">On the Red Hat Enterprise Linux, CentOS, and Fedora distributions, .NET applications default to the cipher suites permitted by the system-wide cryptographic policies.</span></span> <span data-ttu-id="ff943-133">W tych dystrybucjach Użyj konfiguracji zasad kryptograficznych zamiast *OpenSSL. cnf*.</span><span class="sxs-lookup"><span data-stu-id="ff943-133">On these distributions, use the crypto-policies configuration instead of *openssl.cnf*.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ff943-134">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="ff943-134">Affected APIs</span></span>

<span data-ttu-id="ff943-135">Nie detectible za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="ff943-135">Not detectible via API analysis.</span></span>

<!--

### Affected APIs

- Not detectible via API analysis.

### Category

- Cryptography
- Security

-->
