---
title: <remove>, element dla <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: c8ad5a0ce6d7a3059943b3962b9255385cea6e15
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183991"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="67e4f-102">\<remove>, element dla \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="67e4f-102">\<remove> Element for \<namedCaches></span></span>

<span data-ttu-id="67e4f-103">Usuwa wpis nazwanej pamięci podręcznej z `namedCaches` kolekcji dla pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="67e4f-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="67e4f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="67e4f-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="67e4f-105">Typ</span><span class="sxs-lookup"><span data-stu-id="67e4f-105">Type</span></span>  

 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67e4f-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="67e4f-106">Attributes and Elements</span></span>  

 <span data-ttu-id="67e4f-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="67e4f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67e4f-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="67e4f-108">Attributes</span></span>  

 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="67e4f-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="67e4f-109">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="67e4f-110">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="67e4f-110">Parent Elements</span></span>  
  
|<span data-ttu-id="67e4f-111">Element</span><span class="sxs-lookup"><span data-stu-id="67e4f-111">Element</span></span>|<span data-ttu-id="67e4f-112">Opis</span><span class="sxs-lookup"><span data-stu-id="67e4f-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="67e4f-113">Zawiera kolekcję ustawień konfiguracji dla nazwanych <xref:System.Runtime.Caching.MemoryCache> wystąpień.</span><span class="sxs-lookup"><span data-stu-id="67e4f-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67e4f-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="67e4f-114">Remarks</span></span>  

 <span data-ttu-id="67e4f-115">`remove`Element usuwa `namedCache` wpis z kolekcji nazwanych pamięci podręcznej dla pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="67e4f-115">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67e4f-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="67e4f-116">See also</span></span>

- [<span data-ttu-id="67e4f-117">\<namedCaches> — Element (ustawienia pamięci podręcznej)</span><span class="sxs-lookup"><span data-stu-id="67e4f-117">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
