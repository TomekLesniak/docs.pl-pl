---
title: <probing> Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing
- http://schemas.microsoft.com/.NetConfiguration/v2.0#probing
helpviewer_keywords:
- <probing> element
- container tags, <probing> element
- probing element
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
ms.openlocfilehash: 1435ee8ea887b5d7d3e785eef0f25ffed14b1b97
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195275"
---
# <a name="probing-element"></a><span data-ttu-id="ec379-102">\<probing> Element</span><span class="sxs-lookup"><span data-stu-id="ec379-102">\<probing> Element</span></span>

<span data-ttu-id="ec379-103">Określa podkatalogi bazy aplikacji dla środowiska uruchomieniowego języka wspólnego do przeszukania podczas ładowania zestawów.</span><span class="sxs-lookup"><span data-stu-id="ec379-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**  
  
## <a name="syntax"></a><span data-ttu-id="ec379-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ec379-104">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec379-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="ec379-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ec379-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="ec379-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec379-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="ec379-107">Attributes</span></span>  
  
|<span data-ttu-id="ec379-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="ec379-108">Attribute</span></span>|<span data-ttu-id="ec379-109">Opis</span><span class="sxs-lookup"><span data-stu-id="ec379-109">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="ec379-110">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="ec379-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="ec379-111">Określa podkatalogi katalogu podstawowego aplikacji, który może zawierać zestawy.</span><span class="sxs-lookup"><span data-stu-id="ec379-111">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="ec379-112">Rozdziel każdy podkatalog średnikami.</span><span class="sxs-lookup"><span data-stu-id="ec379-112">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec379-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="ec379-113">Child Elements</span></span>  

<span data-ttu-id="ec379-114">Brak.</span><span class="sxs-lookup"><span data-stu-id="ec379-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec379-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="ec379-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ec379-116">Element</span><span class="sxs-lookup"><span data-stu-id="ec379-116">Element</span></span>|<span data-ttu-id="ec379-117">Opis</span><span class="sxs-lookup"><span data-stu-id="ec379-117">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="ec379-118">Zawiera informacje o przekierowaniu wersji zestawu i lokalizacji zestawów.</span><span class="sxs-lookup"><span data-stu-id="ec379-118">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="ec379-119">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ec379-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ec379-120">Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="ec379-120">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ec379-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="ec379-121">Example</span></span>  

 <span data-ttu-id="ec379-122">Poniższy przykład pokazuje, jak określić podkatalogi bazy aplikacji środowisko uruchomieniowe powinno wyszukiwać zestawy.</span><span class="sxs-lookup"><span data-stu-id="ec379-122">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec379-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ec379-123">See also</span></span>

- [<span data-ttu-id="ec379-124">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="ec379-124">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="ec379-125">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="ec379-125">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="ec379-126">Określ lokalizację zestawu</span><span class="sxs-lookup"><span data-stu-id="ec379-126">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="ec379-127">Jak środowisko uruchomieniowe lokalizuje zestawy</span><span class="sxs-lookup"><span data-stu-id="ec379-127">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
