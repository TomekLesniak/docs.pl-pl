---
title: <developmentMode> Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
ms.openlocfilehash: ddcabb831193baee30016f663f32d8562283d936
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205025"
---
# <a name="developmentmode-element"></a><span data-ttu-id="af6fe-102">\<developmentMode> Element</span><span class="sxs-lookup"><span data-stu-id="af6fe-102">\<developmentMode> Element</span></span>

<span data-ttu-id="af6fe-103">Określa, czy środowisko uruchomieniowe wyszukuje zestawy w katalogach określonych przez zmienną środowiskową DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="af6fe-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**  
  
## <a name="syntax"></a><span data-ttu-id="af6fe-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="af6fe-104">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af6fe-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="af6fe-105">Attributes and Elements</span></span>  

 <span data-ttu-id="af6fe-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="af6fe-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af6fe-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="af6fe-107">Attributes</span></span>  
  
|<span data-ttu-id="af6fe-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="af6fe-108">Attribute</span></span>|<span data-ttu-id="af6fe-109">Opis</span><span class="sxs-lookup"><span data-stu-id="af6fe-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af6fe-110">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="af6fe-110">**developerInstallation**</span></span>|<span data-ttu-id="af6fe-111">Określa, czy środowisko uruchomieniowe wyszukuje zestawy w katalogach określonych przez zmienną środowiskową DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="af6fe-111">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="af6fe-112">developerInstallation — atrybut</span><span class="sxs-lookup"><span data-stu-id="af6fe-112">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="af6fe-113">Wartość</span><span class="sxs-lookup"><span data-stu-id="af6fe-113">Value</span></span>|<span data-ttu-id="af6fe-114">Opis</span><span class="sxs-lookup"><span data-stu-id="af6fe-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="af6fe-115">**oznacza**</span><span class="sxs-lookup"><span data-stu-id="af6fe-115">**true**</span></span>|<span data-ttu-id="af6fe-116">Wyszukuje zestawy w katalogach określonych przez zmienną środowiskową DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="af6fe-116">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="af6fe-117">**false**</span><span class="sxs-lookup"><span data-stu-id="af6fe-117">**false**</span></span>|<span data-ttu-id="af6fe-118">Nie wyszukuje zestawów w katalogach określonych przez zmienną środowiskową DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="af6fe-118">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="af6fe-119">Jest to wartość domyślna</span><span class="sxs-lookup"><span data-stu-id="af6fe-119">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af6fe-120">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="af6fe-120">Child Elements</span></span>  

 <span data-ttu-id="af6fe-121">Brak.</span><span class="sxs-lookup"><span data-stu-id="af6fe-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af6fe-122">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="af6fe-122">Parent Elements</span></span>  
  
|<span data-ttu-id="af6fe-123">Element</span><span class="sxs-lookup"><span data-stu-id="af6fe-123">Element</span></span>|<span data-ttu-id="af6fe-124">Opis</span><span class="sxs-lookup"><span data-stu-id="af6fe-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="af6fe-125">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="af6fe-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="af6fe-126">Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="af6fe-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af6fe-127">Uwagi</span><span class="sxs-lookup"><span data-stu-id="af6fe-127">Remarks</span></span>  

 <span data-ttu-id="af6fe-128">Tego ustawienia należy używać tylko w czasie projektowania.</span><span class="sxs-lookup"><span data-stu-id="af6fe-128">Use this setting only at development time.</span></span> <span data-ttu-id="af6fe-129">Środowisko uruchomieniowe nie sprawdza wersji w zestawach o silnej nazwie znalezionych w DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="af6fe-129">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="af6fe-130">Po prostu używa pierwszego zestawu, który znajdzie.</span><span class="sxs-lookup"><span data-stu-id="af6fe-130">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af6fe-131">Przykład</span><span class="sxs-lookup"><span data-stu-id="af6fe-131">Example</span></span>  

 <span data-ttu-id="af6fe-132">Poniższy przykład pokazuje, jak spowodować, że środowisko uruchomieniowe wyszukuje zestawy w katalogach określonych przez zmienną środowiskową DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="af6fe-132">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="af6fe-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="af6fe-133">See also</span></span>

- [<span data-ttu-id="af6fe-134">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="af6fe-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="af6fe-135">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="af6fe-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="af6fe-136">Instrukcje: Lokalizowanie zestawów za pomocą DEVPATH</span><span class="sxs-lookup"><span data-stu-id="af6fe-136">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
