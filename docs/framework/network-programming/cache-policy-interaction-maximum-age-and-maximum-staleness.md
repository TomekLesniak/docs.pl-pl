---
title: Interakcja z zasadami pamięci podręcznej — maksymalny wiek i maksymalna nieaktualność
ms.date: 03/30/2017
helpviewer_keywords:
- maximum staleness
- freshness of cached resources
- time, cached resources
- maximum age policy
- staleness of cached resources
- age of cached resources
ms.assetid: 7f775925-89a1-4956-ba90-c869c1749a94
ms.openlocfilehash: bdfa608b5169755b2b4daaaa26e562308ae2be01
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250609"
---
# <a name="cache-policy-interactionmaximum-age-and-maximum-staleness"></a><span data-ttu-id="7dd8d-102">Interakcja z zasadami pamięci podręcznej — maksymalny wiek i maksymalna nieaktualność</span><span class="sxs-lookup"><span data-stu-id="7dd8d-102">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>

<span data-ttu-id="7dd8d-103">Aby zapewnić, że najnowsza zawartość jest zwracana do aplikacji klienckiej, interakcja z zasadami pamięci podręcznej klienta i wymagania dotyczące ponownego sprawdzania poprawności serwera zawsze będą mieć najważniejsze zasady pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-103">To help ensure that the freshest content is returned to the client application, the interaction of client cache policy and server revalidation requirements always results in the most conservative cache policy.</span></span> <span data-ttu-id="7dd8d-104">We wszystkich przykładach w tym temacie przedstawiono zasady pamięci podręcznej dla zasobu, który jest buforowany 1 stycznia i wygasa 4 stycznia.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-104">All the examples in this topic illustrate the cache policy for a resource that is cached on January 1 and expires on January 4.</span></span>  
  
 <span data-ttu-id="7dd8d-105">W poniższych przykładach maksymalna wartość nieodświeżona ( `maxStale` ) jest używana w połączeniu z maksymalnym wiekiem ( `maxAge` ):</span><span class="sxs-lookup"><span data-stu-id="7dd8d-105">In the following examples, the maximum staleness value (`maxStale`) is used in conjunction with a maximum age (`maxAge`):</span></span>  
  
- <span data-ttu-id="7dd8d-106">Jeśli zasady pamięci podręcznej są ustawione na `maxAge` 5 dni i nie określają `maxStale` wartości, zgodnie z `maxAge` wartością, zawartość będzie można użyć do 6 stycznia.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-106">If the cache policy sets `maxAge` = 5 days and does not specify a `maxStale` value, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="7dd8d-107">Jednak zgodnie z wymaganiami dotyczącymi weryfikacji serwera zawartość wygasa 4 stycznia.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-107">However, according to the server's revalidation requirements, the content expires on January 4.</span></span> <span data-ttu-id="7dd8d-108">Ponieważ data wygaśnięcia zawartości jest bardziej ostrożna (wcześniej), ma pierwszeństwo przed `maxAge` zasadami.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-108">Because the content expiration date is more conservative (sooner), it takes precedence over the `maxAge` policy.</span></span> <span data-ttu-id="7dd8d-109">W związku z tym zawartość wygasa 4 stycznia i należy ponownie sprawdzić poprawność, nawet jeśli nie osiągnięto maksymalnego wieku.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-109">Therefore, the content expires on January 4 and must be revalidated even though its maximum age has not been reached.</span></span>  
  
- <span data-ttu-id="7dd8d-110">Jeśli zasady pamięci podręcznej określają `maxAge` 5 dni i `maxStale` = 3 dni, zgodnie z `maxAge` wartością, zawartość będzie można użyć do 6 stycznia.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-110">If the cache policy sets `maxAge` = 5 days and `maxStale` = 3 days, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="7dd8d-111">Według `maxStale` wartości, zawartość jest użyteczna do 7 stycznia.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-111">According to the `maxStale` value, the content is usable until January 7.</span></span> <span data-ttu-id="7dd8d-112">W związku z tym zawartość zostanie ponownie sprawdzona w dniu 6 stycznia.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-112">Therefore, the content gets revalidated on January 6.</span></span>  
  
- <span data-ttu-id="7dd8d-113">Jeśli zasady pamięci podręcznej określają `maxAge` 5 dni i `maxStale` = 1 dzień, zgodnie z `maxAge` wartością, zawartość będzie można użyć do 6 stycznia.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-113">If the cache policy sets `maxAge` = 5 days and `maxStale` = 1 day, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="7dd8d-114">Według `maxStale` wartości, zawartość jest użyteczna do 5 stycznia.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-114">According to the `maxStale` value, the content is usable until January 5.</span></span> <span data-ttu-id="7dd8d-115">W związku z tym zawartość zostanie ponownie zweryfikowana 5 stycznia.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-115">Therefore, the content gets revalidated on January 5.</span></span>  
  
 <span data-ttu-id="7dd8d-116">Gdy maksymalny wiek jest krótszy niż data wygaśnięcia zawartości, bardziej ostrożne zachowanie buforowania jest zawsze przeważane, a maksymalna wartość starej wartości nie ma żadnego wpływu.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-116">When the maximum age is less than the content expiration date, the more conservative caching behavior always prevails and the maximum staleness value has no effect.</span></span> <span data-ttu-id="7dd8d-117">Poniższe przykłady ilustrują efekt ustawienia maksymalnej wartości starej ( `maxStale` ) w przypadku osiągnięcia maksymalnego wieku ( `maxAge` ) przed wygaśnięciem zawartości:</span><span class="sxs-lookup"><span data-stu-id="7dd8d-117">The following examples illustrate the effect of setting a maximum staleness (`maxStale`) value when the maximum age (`maxAge`) is reached before the content expires:</span></span>  
  
- <span data-ttu-id="7dd8d-118">Jeśli zasady pamięci podręcznej są ustawione na `maxAge` 1 dzień i nie określają wartości `maxStale` , zawartość jest ponownie weryfikowana w dniu 2 stycznia, nawet jeśli nie wygasła.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-118">If the cache policy sets `maxAge` = 1 day and does not specify a value for `maxStale` value, the content is revalidated on January 2 even though it has not expired.</span></span>  
  
- <span data-ttu-id="7dd8d-119">Jeśli zasady pamięci podręcznej określają `maxAge` 1 dzień i `maxStale` = 3 dni, zawartość jest ponownie weryfikowana w dniu 2 stycznia, aby wymusić bardziej niewykonalne ustawienie zasad.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-119">If the cache policy sets `maxAge` = 1 day and `maxStale` = 3 days, the content is revalidated on January 2 to enforce the more conservative policy setting.</span></span>  
  
- <span data-ttu-id="7dd8d-120">Jeśli zasady pamięci podręcznej określają `maxAge` 1 dzień i `maxStale` = 1 dzień, zawartość jest ponownie weryfikowana 2 stycznia.</span><span class="sxs-lookup"><span data-stu-id="7dd8d-120">If the cache policy sets `maxAge` = 1 day and `maxStale` = 1 day, the content is revalidated on January 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dd8d-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7dd8d-121">See also</span></span>

- [<span data-ttu-id="7dd8d-122">Zarządzanie pamięcią podręczną dla aplikacji sieciowych</span><span class="sxs-lookup"><span data-stu-id="7dd8d-122">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="7dd8d-123">Zasady pamięci podręcznej</span><span class="sxs-lookup"><span data-stu-id="7dd8d-123">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="7dd8d-124">Zasady pamięci podręcznej oparte na lokalizacji</span><span class="sxs-lookup"><span data-stu-id="7dd8d-124">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- [<span data-ttu-id="7dd8d-125">Zasady pamięci podręcznej oparte na czasie</span><span class="sxs-lookup"><span data-stu-id="7dd8d-125">Time-Based Cache Policies</span></span>](time-based-cache-policies.md)
- [<span data-ttu-id="7dd8d-126">Konfigurowanie pamięci podręcznej w aplikacjach sieciowych</span><span class="sxs-lookup"><span data-stu-id="7dd8d-126">Configuring Caching in Network Applications</span></span>](configuring-caching-in-network-applications.md)
- [<span data-ttu-id="7dd8d-127">Interakcja z zasadami pamięci podręcznej — maksymalny wiek i minimalna świeżość</span><span class="sxs-lookup"><span data-stu-id="7dd8d-127">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>](cache-policy-interaction-maximum-age-and-minimum-freshness.md)
