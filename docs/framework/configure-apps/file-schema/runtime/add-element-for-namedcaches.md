---
title: <add>, element dla <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: cd920b58290050fcc30ea5d0a1ac113a333902fa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195366"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="c872e-102">\<add>, element dla \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="c872e-102">\<add> Element for \<namedCaches></span></span>

<span data-ttu-id="c872e-103">Dodaje `namedCache` wpis do `namedCaches` kolekcji dla pamięci podręcznej pamięci.</span><span class="sxs-lookup"><span data-stu-id="c872e-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="c872e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c872e-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="c872e-105">Typ</span><span class="sxs-lookup"><span data-stu-id="c872e-105">Type</span></span>  

 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c872e-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="c872e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c872e-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="c872e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c872e-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="c872e-108">Attributes</span></span>  
  
|<span data-ttu-id="c872e-109">Atrybut</span><span class="sxs-lookup"><span data-stu-id="c872e-109">Attribute</span></span>|<span data-ttu-id="c872e-110">Opis</span><span class="sxs-lookup"><span data-stu-id="c872e-110">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="c872e-111">Wartość całkowita określająca maksymalny dozwolony rozmiar (w megabajtach), do którego wystąpienie <xref:System.Runtime.Caching.MemoryCache> może się rozwijać.</span><span class="sxs-lookup"><span data-stu-id="c872e-111">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="c872e-112">Wartość domyślna to 0, co oznacza, że <xref:System.Runtime.Caching.MemoryCache> algorytmy autowymiarowania klasy są używane domyślnie.</span><span class="sxs-lookup"><span data-stu-id="c872e-112">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="c872e-113">Nazwa pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="c872e-113">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="c872e-114">Wartość całkowita z zakresu od 0 do 100, która określa maksymalną wartość procentową fizycznie zainstalowanej pamięci komputera, która może być używana przez pamięć podręczną.</span><span class="sxs-lookup"><span data-stu-id="c872e-114">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="c872e-115">Wartość domyślna to 0, co oznacza, że <xref:System.Runtime.Caching.MemoryCache> algorytmy autowymiarowania klasy są używane domyślnie.</span><span class="sxs-lookup"><span data-stu-id="c872e-115">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="c872e-116">Wartość, która wskazuje przedział czasu, po upływie którego implementacja pamięci podręcznej porównuje bieżące obciążenie pamięci z limitami pamięci bezwzględnej i procentową ustawioną dla wystąpienia pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="c872e-116">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="c872e-117">Ta wartość jest wprowadzana w formacie "gg: MM: SS".</span><span class="sxs-lookup"><span data-stu-id="c872e-117">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c872e-118">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="c872e-118">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="c872e-119">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="c872e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c872e-120">Element</span><span class="sxs-lookup"><span data-stu-id="c872e-120">Element</span></span>|<span data-ttu-id="c872e-121">Opis</span><span class="sxs-lookup"><span data-stu-id="c872e-121">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="c872e-122">Zawiera kolekcję ustawień konfiguracji dla nazwanych <xref:System.Runtime.Caching.MemoryCache> wystąpień.</span><span class="sxs-lookup"><span data-stu-id="c872e-122">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c872e-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c872e-123">Remarks</span></span>  

 <span data-ttu-id="c872e-124">`add`Element dodaje wpis do `namedCaches` kolekcji dla pamięci podręcznej pamięci.</span><span class="sxs-lookup"><span data-stu-id="c872e-124">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="c872e-125">Można użyć elementu [Clear](clear-element-for-namedcaches.md) przed użyciem `add` elementu, aby mieć pewność, że w kolekcji nie ma innych nazwanych pamięci podręcznych.</span><span class="sxs-lookup"><span data-stu-id="c872e-125">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="c872e-126">Ten element może być używany w pliku machine.config i w pliku Web.config.</span><span class="sxs-lookup"><span data-stu-id="c872e-126">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c872e-127">Przykład</span><span class="sxs-lookup"><span data-stu-id="c872e-127">Example</span></span>  

 <span data-ttu-id="c872e-128">Poniższy przykład pokazuje, jak zdefiniować ustawienia domyślnego `namedCache` wpisu do `namedCaches` kolekcji dla pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="c872e-128">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c872e-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c872e-129">See also</span></span>

- [<span data-ttu-id="c872e-130">\<namedCaches> — Element (ustawienia pamięci podręcznej)</span><span class="sxs-lookup"><span data-stu-id="c872e-130">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
