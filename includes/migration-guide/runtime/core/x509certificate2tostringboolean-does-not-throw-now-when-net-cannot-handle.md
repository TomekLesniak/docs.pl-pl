---
ms.openlocfilehash: 7f8f97adcca7e66fa5756212bb977daadd92b8b6
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497125"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a><span data-ttu-id="e5630-101">X509Certificate2. ToString (wartość logiczna) nie jest teraz zgłaszana, gdy platforma .NET nie może obsłużyć certyfikatu</span><span class="sxs-lookup"><span data-stu-id="e5630-101">X509Certificate2.ToString(Boolean) does not throw now when .NET cannot handle the certificate</span></span>

#### <a name="details"></a><span data-ttu-id="e5630-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="e5630-102">Details</span></span>

<span data-ttu-id="e5630-103">W .NET Framework 4.5.2 i starszych wersjach ta metoda zostałaby <code>true</code> zgłoszona, jeśli została przeniesiona do parametru verbose i zainstalowano certyfikaty, które nie były obsługiwane przez .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e5630-103">In .NET Framework 4.5.2 and earlier versions, this method would throw if <code>true</code> was passed for the verbose parameter and there were certificates installed that weren't supported by the .NET Framework.</span></span> <span data-ttu-id="e5630-104">Teraz Metoda zakończy się pomyślnie i zwróci prawidłowy ciąg, który pomija niedostępne fragmenty certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="e5630-104">Now, the method will succeed and return a valid string that omits the inaccessible portions of the certificate.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e5630-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="e5630-105">Suggestion</span></span>

<span data-ttu-id="e5630-106">Każdy kod w zależności od tego <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> należy zaktualizować, aby oczekiwać, że zwrócony ciąg może wykluczyć niektóre dane certyfikatu (takie jak klucz publiczny, klucz prywatny i rozszerzenia) w niektórych przypadkach, w których interfejs API zostałby wcześniej wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="e5630-106">Any code depending on <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> should be updated to expect that the returned string may exclude some certificate data (such as public key, private key, and extensions) in some cases in which the API would have previously thrown.</span></span>

| <span data-ttu-id="e5630-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="e5630-107">Name</span></span>    | <span data-ttu-id="e5630-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="e5630-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e5630-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="e5630-109">Scope</span></span>   |<span data-ttu-id="e5630-110">Edge</span><span class="sxs-lookup"><span data-stu-id="e5630-110">Edge</span></span>|
|<span data-ttu-id="e5630-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="e5630-111">Version</span></span>|<span data-ttu-id="e5630-112">4,6</span><span class="sxs-lookup"><span data-stu-id="e5630-112">4.6</span></span>|
|<span data-ttu-id="e5630-113">Typ</span><span class="sxs-lookup"><span data-stu-id="e5630-113">Type</span></span>|<span data-ttu-id="e5630-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="e5630-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="e5630-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="e5630-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)`

-->
