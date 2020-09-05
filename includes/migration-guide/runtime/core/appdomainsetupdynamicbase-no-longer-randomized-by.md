---
ms.openlocfilehash: 26c50ac8b0e570e31a38b1913f73acbe21fae08b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497839"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a><span data-ttu-id="62d44-101">AppDomainSetup. DynamicBase nie jest już losowo określana przez UseRandomizedStringHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="62d44-101">AppDomainSetup.DynamicBase is no longer randomized by UseRandomizedStringHashAlgorithm</span></span>

#### <a name="details"></a><span data-ttu-id="62d44-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="62d44-102">Details</span></span>

<span data-ttu-id="62d44-103">Przed .NET Framework 4,6 wartość zostanie przetworzona <xref:System.AppDomainSetup.DynamicBase> losowo między domenami aplikacji lub między procesami, jeśli UseRandomizedStringHashAlgorithm został włączony w pliku konfiguracji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="62d44-103">Prior to the .NET Framework 4.6, the value of <xref:System.AppDomainSetup.DynamicBase> would be randomized between application domains, or between processes, if UseRandomizedStringHashAlgorithm was enabled in the app's config file.</span></span> <span data-ttu-id="62d44-104">Począwszy od .NET Framework 4,6, <xref:System.AppDomainSetup.DynamicBase> zwróci stabilny wynik między różnymi wystąpieniami aplikacji i między różnymi domenami aplikacji.</span><span class="sxs-lookup"><span data-stu-id="62d44-104">Beginning in the .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> will return a stable result between different instances of an app running, and between different app domains.</span></span> <span data-ttu-id="62d44-105">Dynamiczne bazy nadal różnią się w zależności od różnych aplikacji; Ta zmiana powoduje jedynie usunięcie losowego elementu nazewnictwa dla różnych wystąpień tej samej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="62d44-105">Dynamic bases will still differ for different apps; this change only removes the random naming element for different instances of the same app.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="62d44-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="62d44-106">Suggestion</span></span>

<span data-ttu-id="62d44-107">Należy pamiętać, że włączenie <code>UseRandomizedStringHashAlgorithm</code> nie spowoduje <xref:System.AppDomainSetup.DynamicBase> losowego uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="62d44-107">Be aware that enabling <code>UseRandomizedStringHashAlgorithm</code> will not result in <xref:System.AppDomainSetup.DynamicBase> being randomized.</span></span> <span data-ttu-id="62d44-108">Jeśli jest wymagana Losowa baza, należy ją utworzyć w kodzie aplikacji, a nie za pośrednictwem tego interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="62d44-108">If a random base is needed, it must be produced in your app's code rather than via this API.</span></span>

| <span data-ttu-id="62d44-109">Nazwa</span><span class="sxs-lookup"><span data-stu-id="62d44-109">Name</span></span>    | <span data-ttu-id="62d44-110">Wartość</span><span class="sxs-lookup"><span data-stu-id="62d44-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="62d44-111">Zakres</span><span class="sxs-lookup"><span data-stu-id="62d44-111">Scope</span></span>   |<span data-ttu-id="62d44-112">Edge</span><span class="sxs-lookup"><span data-stu-id="62d44-112">Edge</span></span>|
|<span data-ttu-id="62d44-113">Wersja</span><span class="sxs-lookup"><span data-stu-id="62d44-113">Version</span></span>|<span data-ttu-id="62d44-114">4,6</span><span class="sxs-lookup"><span data-stu-id="62d44-114">4.6</span></span>|
|<span data-ttu-id="62d44-115">Typ</span><span class="sxs-lookup"><span data-stu-id="62d44-115">Type</span></span>|<span data-ttu-id="62d44-116">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="62d44-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="62d44-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="62d44-117">Affected APIs</span></span>

- <xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.AppDomainSetup.DynamicBase`

-->
