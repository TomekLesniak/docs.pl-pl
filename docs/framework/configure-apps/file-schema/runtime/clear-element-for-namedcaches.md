---
title: <clear>, element dla <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: d65712f091c5fb9212167b4759c70db7e5d744c1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149416"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="ad7fe-102">\<clear>, element dla \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="ad7fe-102">\<clear> Element for \<namedCaches></span></span>

<span data-ttu-id="ad7fe-103">Czyści wszystkie `namedCache` wpisy w kolekcji pamięci `namedCaches` podręcznej pamięci.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="ad7fe-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ad7fe-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="ad7fe-105">Typ</span><span class="sxs-lookup"><span data-stu-id="ad7fe-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad7fe-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="ad7fe-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ad7fe-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad7fe-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="ad7fe-108">Attributes</span></span>  

 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="ad7fe-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="ad7fe-109">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="ad7fe-110">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="ad7fe-110">Parent Elements</span></span>  
  
|<span data-ttu-id="ad7fe-111">Element</span><span class="sxs-lookup"><span data-stu-id="ad7fe-111">Element</span></span>|<span data-ttu-id="ad7fe-112">Opis</span><span class="sxs-lookup"><span data-stu-id="ad7fe-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="ad7fe-113">Zawiera kolekcję ustawień konfiguracji dla nazwanych <xref:System.Runtime.Caching.MemoryCache> wystąpień.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad7fe-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ad7fe-114">Remarks</span></span>  

 <span data-ttu-id="ad7fe-115">`clear`Element czyści wszystkie `namedCache` wpisy w kolekcji nazwanych pamięci podręcznej dla pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-115">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="ad7fe-116">Można użyć `clear` elementu przed użyciem `add` elementu, aby dodać nowy nazwany wpis pamięci podręcznej w celu uzyskania pewności, że w kolekcji nie ma innych nazwanych pamięci podręcznych.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-116">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad7fe-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ad7fe-117">See also</span></span>

- [<span data-ttu-id="ad7fe-118">\<namedCaches> — Element (ustawienia pamięci podręcznej)</span><span class="sxs-lookup"><span data-stu-id="ad7fe-118">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
