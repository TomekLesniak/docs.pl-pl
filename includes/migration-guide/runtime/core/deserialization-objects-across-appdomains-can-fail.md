---
ms.openlocfilehash: 3f82a4daac3b5d8981532f0c82e9a76f13c68b6e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496622"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="bf994-101">Deserializacja obiektów w domenach AppDomain może zakończyć się niepowodzeniem</span><span class="sxs-lookup"><span data-stu-id="bf994-101">Deserialization of objects across appdomains can fail</span></span>

#### <a name="details"></a><span data-ttu-id="bf994-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="bf994-102">Details</span></span>

<span data-ttu-id="bf994-103">W niektórych przypadkach, gdy aplikacja używa dwóch lub większej liczby domen aplikacji z różnymi bazami aplikacji, próba deserializacji obiektów w kontekście wywołania logicznego między domenami aplikacji zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="bf994-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bf994-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="bf994-104">Suggestion</span></span>

<span data-ttu-id="bf994-105">Zobacz [łagodzenie: deserializacja obiektów w domenach aplikacji](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span><span class="sxs-lookup"><span data-stu-id="bf994-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>

| <span data-ttu-id="bf994-106">Nazwa</span><span class="sxs-lookup"><span data-stu-id="bf994-106">Name</span></span>    | <span data-ttu-id="bf994-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="bf994-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bf994-108">Zakres</span><span class="sxs-lookup"><span data-stu-id="bf994-108">Scope</span></span>   |<span data-ttu-id="bf994-109">Edge</span><span class="sxs-lookup"><span data-stu-id="bf994-109">Edge</span></span>|
|<span data-ttu-id="bf994-110">Wersja</span><span class="sxs-lookup"><span data-stu-id="bf994-110">Version</span></span>|<span data-ttu-id="bf994-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="bf994-111">4.5.1</span></span>|
|<span data-ttu-id="bf994-112">Typ</span><span class="sxs-lookup"><span data-stu-id="bf994-112">Type</span></span>|<span data-ttu-id="bf994-113">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="bf994-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="bf994-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="bf994-114">Affected APIs</span></span>

<span data-ttu-id="bf994-115">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="bf994-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
