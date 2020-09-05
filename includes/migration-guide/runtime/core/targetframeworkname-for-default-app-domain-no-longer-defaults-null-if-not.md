---
ms.openlocfilehash: 4e685722271a8079e727ea9c2e0e501f68b30fc9
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497403"
---
### <a name="targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a><span data-ttu-id="7ee95-101">TargetFrameworkName dla domyślnej domeny aplikacji nie ma już wartości null, jeśli nie jest ustawiona</span><span class="sxs-lookup"><span data-stu-id="7ee95-101">TargetFrameworkName for default app domain no longer defaults to null if not set</span></span>

#### <a name="details"></a><span data-ttu-id="7ee95-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="7ee95-102">Details</span></span>

<span data-ttu-id="7ee95-103"><xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName>Program był wcześniej pusty w domenie aplikacji domyślnej, chyba że został jawnie ustawiony.</span><span class="sxs-lookup"><span data-stu-id="7ee95-103">The <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> was previously null in the default app domain, unless it was explicitly set.</span></span> <span data-ttu-id="7ee95-104">Począwszy od 4,6, <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> Właściwość domyślnej domeny aplikacji będzie mieć wartość domyślną pochodzącą z TargetFrameworkAttribute (jeśli istnieje).</span><span class="sxs-lookup"><span data-stu-id="7ee95-104">Beginning in 4.6, the <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> property for the default app domain will have a default value derived from the TargetFrameworkAttribute (if one is present).</span></span> <span data-ttu-id="7ee95-105">Domeny aplikacji innych niż domyślne będą nadal dziedziczyć <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> z domyślnej domeny aplikacji (która nie ma wartości null w 4,6), chyba że zostanie jawnie przesłonięty.</span><span class="sxs-lookup"><span data-stu-id="7ee95-105">Non-default app domains will continue to inherit their <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> from the default app domain (which will not default to null in 4.6) unless it is explicitly overridden.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7ee95-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="7ee95-106">Suggestion</span></span>

<span data-ttu-id="7ee95-107">Kod powinien zostać zaktualizowany, aby nie zależał <xref:System.AppDomainSetup.TargetFrameworkName> domyślnego ustawienia wartości null.</span><span class="sxs-lookup"><span data-stu-id="7ee95-107">Code should be updated to not depend on <xref:System.AppDomainSetup.TargetFrameworkName> defaulting to null.</span></span> <span data-ttu-id="7ee95-108">Jeśli jest wymagane, aby ta właściwość kontynuowała szacowanie do wartości null, może być jawnie ustawiona na tę wartość.</span><span class="sxs-lookup"><span data-stu-id="7ee95-108">If it is required that this property continue to evaluate to null, it can be explicitly set to that value.</span></span>

| <span data-ttu-id="7ee95-109">Nazwa</span><span class="sxs-lookup"><span data-stu-id="7ee95-109">Name</span></span>    | <span data-ttu-id="7ee95-110">Wartość</span><span class="sxs-lookup"><span data-stu-id="7ee95-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7ee95-111">Zakres</span><span class="sxs-lookup"><span data-stu-id="7ee95-111">Scope</span></span>   |<span data-ttu-id="7ee95-112">Edge</span><span class="sxs-lookup"><span data-stu-id="7ee95-112">Edge</span></span>|
|<span data-ttu-id="7ee95-113">Wersja</span><span class="sxs-lookup"><span data-stu-id="7ee95-113">Version</span></span>|<span data-ttu-id="7ee95-114">4,6</span><span class="sxs-lookup"><span data-stu-id="7ee95-114">4.6</span></span>|
|<span data-ttu-id="7ee95-115">Typ</span><span class="sxs-lookup"><span data-stu-id="7ee95-115">Type</span></span>|<span data-ttu-id="7ee95-116">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="7ee95-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="7ee95-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="7ee95-117">Affected APIs</span></span>

- <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.AppDomainSetup.TargetFrameworkName`

-->
