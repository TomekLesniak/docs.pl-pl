---
title: <Directives> — Element (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 524c30872e218f6428491507bbfb4ca54b6061b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251103"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="78445-102">\<Directives> — Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="78445-102">\<Directives> Element (.NET Native)</span></span>

<span data-ttu-id="78445-103">Element główny w każdym pliku dyrektywy środowiska uruchomieniowego dla .NET Native.</span><span class="sxs-lookup"><span data-stu-id="78445-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a><span data-ttu-id="78445-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="78445-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="78445-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="78445-105">Attributes</span></span>  
  
|<span data-ttu-id="78445-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="78445-106">Attribute</span></span>|<span data-ttu-id="78445-107">Opis</span><span class="sxs-lookup"><span data-stu-id="78445-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="78445-108">Przestrzeń nazw XML.</span><span class="sxs-lookup"><span data-stu-id="78445-108">The XML namespace.</span></span> <span data-ttu-id="78445-109">Jego wartość jest zawsze `http://schemas.microsoft.com/netfx/2013/01/metadata` .</span><span class="sxs-lookup"><span data-stu-id="78445-109">Its value is always `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="78445-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="78445-110">Child elements</span></span>  
  
|<span data-ttu-id="78445-111">Element</span><span class="sxs-lookup"><span data-stu-id="78445-111">Element</span></span>|<span data-ttu-id="78445-112">Opis</span><span class="sxs-lookup"><span data-stu-id="78445-112">Description</span></span>|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|<span data-ttu-id="78445-113">Służy jako kontener dla typów i składowych dla całej aplikacji, których metadane są dostępne do odbicia.</span><span class="sxs-lookup"><span data-stu-id="78445-113">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[\<Library>](library-element-net-native.md)|<span data-ttu-id="78445-114">Definiuje zestaw, którego typy podrzędne i elementy członkowskie typu wymagają metadanych w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="78445-114">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78445-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="78445-115">Remarks</span></span>  

 <span data-ttu-id="78445-116">Każdy plik dyrektywy środowiska uruchomieniowego może zawierać tylko jeden `<Directives>` element.</span><span class="sxs-lookup"><span data-stu-id="78445-116">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="78445-117">`<Directives>`Element może zawierać zero lub jeden [\<Application>](application-element-net-native.md) element oraz zero, jeden lub więcej [\<Library>](library-element-net-native.md) elementów.</span><span class="sxs-lookup"><span data-stu-id="78445-117">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78445-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="78445-118">See also</span></span>

- [<span data-ttu-id="78445-119">Dokumentacja pliku konfiguracji dyrektyw środowiska uruchomieniowego (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="78445-119">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="78445-120">Elementy dyrektyw środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="78445-120">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
