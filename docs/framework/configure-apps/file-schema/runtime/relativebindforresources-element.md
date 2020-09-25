---
title: <relativeBindForResources> Element
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: daf576488e38bed28c7c0e5222bc053659372ff0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184004"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="47a94-102">\<relativeBindForResources> Element</span><span class="sxs-lookup"><span data-stu-id="47a94-102">\<relativeBindForResources> Element</span></span>

<span data-ttu-id="47a94-103">Optymalizuje sondę dla zestawów satelickich.</span><span class="sxs-lookup"><span data-stu-id="47a94-103">Optimizes the probe for satellite assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**  
  
## <a name="syntax"></a><span data-ttu-id="47a94-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="47a94-104">Syntax</span></span>  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47a94-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="47a94-105">Attributes and Elements</span></span>  

 <span data-ttu-id="47a94-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="47a94-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47a94-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="47a94-107">Attributes</span></span>  
  
|<span data-ttu-id="47a94-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="47a94-108">Attribute</span></span>|<span data-ttu-id="47a94-109">Opis</span><span class="sxs-lookup"><span data-stu-id="47a94-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="47a94-110">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="47a94-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="47a94-111">Określa, czy środowisko uruchomieniowe języka wspólnego optymalizuje sondę dla zestawów satelickich.</span><span class="sxs-lookup"><span data-stu-id="47a94-111">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="47a94-112">Atrybut włączony</span><span class="sxs-lookup"><span data-stu-id="47a94-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="47a94-113">Wartość</span><span class="sxs-lookup"><span data-stu-id="47a94-113">Value</span></span>|<span data-ttu-id="47a94-114">Opis</span><span class="sxs-lookup"><span data-stu-id="47a94-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="47a94-115">Środowisko uruchomieniowe nie optymalizuje sondy dla zestawów satelickich.</span><span class="sxs-lookup"><span data-stu-id="47a94-115">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="47a94-116">Jest to wartość domyślna.</span><span class="sxs-lookup"><span data-stu-id="47a94-116">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="47a94-117">Środowisko uruchomieniowe optymalizuje sondę dla zestawów satelickich.</span><span class="sxs-lookup"><span data-stu-id="47a94-117">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47a94-118">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="47a94-118">Child Elements</span></span>  

 <span data-ttu-id="47a94-119">Brak.</span><span class="sxs-lookup"><span data-stu-id="47a94-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="47a94-120">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="47a94-120">Parent Elements</span></span>  
  
|<span data-ttu-id="47a94-121">Element</span><span class="sxs-lookup"><span data-stu-id="47a94-121">Element</span></span>|<span data-ttu-id="47a94-122">Opis</span><span class="sxs-lookup"><span data-stu-id="47a94-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="47a94-123">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="47a94-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="47a94-124">Zawiera informacje dotyczące opcji inicjowania środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="47a94-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47a94-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="47a94-125">Remarks</span></span>  

 <span data-ttu-id="47a94-126">Ogólnie rzecz biorąc, Menedżer zasobów sondy dla zasobów, zgodnie z opisem w temacie [pakowanie i wdrażanie zasobów](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) .</span><span class="sxs-lookup"><span data-stu-id="47a94-126">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="47a94-127">Oznacza to, że podczas Menedżer zasobów sond dla konkretnej zlokalizowanej wersji zasobu może on wyglądać w globalnej pamięci podręcznej zestawów, wyszukać w folderze specyficznym dla kultury w bazie kodu aplikacji, Instalator Windows zapytań dla zestawów satelickich i zgłosić <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="47a94-127">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="47a94-128">`<relativeBindForResources>`Element optymalizuje sposób, w jaki Menedżer zasobów sondy dla zestawów satelickich.</span><span class="sxs-lookup"><span data-stu-id="47a94-128">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="47a94-129">Może zwiększyć wydajność podczas sondowania zasobów w następujących warunkach:</span><span class="sxs-lookup"><span data-stu-id="47a94-129">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="47a94-130">Gdy zestaw satelicki zostanie wdrożony w tej samej lokalizacji co zestaw kodu.</span><span class="sxs-lookup"><span data-stu-id="47a94-130">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="47a94-131">Innymi słowy, jeśli zestaw kodu jest zainstalowany w globalnej pamięci podręcznej zestawów, należy również zainstalować w tym miejscu zestawy satelickie.</span><span class="sxs-lookup"><span data-stu-id="47a94-131">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="47a94-132">Jeśli zestaw kodu jest zainstalowany w bazie kodu aplikacji, zestawy satelickie muszą być również zainstalowane w folderze specyficznym dla kultury w bazie kodu.</span><span class="sxs-lookup"><span data-stu-id="47a94-132">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="47a94-133">Gdy Instalator Windows nie jest używany lub jest używany rzadko w przypadku instalacji zestawów satelitarnych na żądanie.</span><span class="sxs-lookup"><span data-stu-id="47a94-133">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="47a94-134">Gdy kod aplikacji nie obsługuje <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="47a94-134">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="47a94-135">Ustawienie `enabled` atrybutu `<relativeBindForResources>` elementu w celu `true` optymalizacji sondy Menedżer zasobów dla zestawów satelickich w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="47a94-135">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="47a94-136">Używa lokalizacji zestawu kodu nadrzędnego do sondowania dla zestawu satelickiego.</span><span class="sxs-lookup"><span data-stu-id="47a94-136">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="47a94-137">Nie bada Instalator Windows dla zestawów satelickich.</span><span class="sxs-lookup"><span data-stu-id="47a94-137">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="47a94-138">Nie zgłasza <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="47a94-138">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a94-139">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="47a94-139">See also</span></span>

- [<span data-ttu-id="47a94-140">Opakowanie i wdrażanie zasobów</span><span class="sxs-lookup"><span data-stu-id="47a94-140">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="47a94-141">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="47a94-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="47a94-142">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="47a94-142">Configuration File Schema</span></span>](../index.md)
