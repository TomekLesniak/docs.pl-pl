---
title: <webRequestModules>, element (ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: 9396ca393523dce5593531f332e5c07241987947
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91187007"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="a669e-102">\<webRequestModules>, element (ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="a669e-102">\<webRequestModules> Element (Network Settings)</span></span>

<span data-ttu-id="a669e-103">Określa moduły, które mają być używane do żądania informacji z hostów sieciowych.</span><span class="sxs-lookup"><span data-stu-id="a669e-103">Specifies modules to use to request information from network hosts.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules>  
  
## <a name="syntax"></a><span data-ttu-id="a669e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a669e-104">Syntax</span></span>  
  
```xml  
<webRequestModules>
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a669e-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="a669e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a669e-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="a669e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a669e-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="a669e-107">Attributes</span></span>  

 <span data-ttu-id="a669e-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="a669e-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a669e-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="a669e-109">Child Elements</span></span>  
  
|<span data-ttu-id="a669e-110">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="a669e-110">**Element**</span></span>|<span data-ttu-id="a669e-111">**Opis**</span><span class="sxs-lookup"><span data-stu-id="a669e-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a669e-112">add</span><span class="sxs-lookup"><span data-stu-id="a669e-112">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="a669e-113">Dodaje niestandardowy moduł żądania sieci Web do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a669e-113">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="a669e-114">Wyczyść</span><span class="sxs-lookup"><span data-stu-id="a669e-114">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="a669e-115">Usuwa wszystkie zarejestrowane moduły żądania sieci Web z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a669e-115">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="a669e-116">usuwa</span><span class="sxs-lookup"><span data-stu-id="a669e-116">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="a669e-117">Usuwa niestandardowy moduł żądania sieci Web z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a669e-117">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a669e-118">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="a669e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a669e-119">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="a669e-119">**Element**</span></span>|<span data-ttu-id="a669e-120">**Opis**</span><span class="sxs-lookup"><span data-stu-id="a669e-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a669e-121">system.net</span><span class="sxs-lookup"><span data-stu-id="a669e-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="a669e-122">Zawiera ustawienia, które określają, w jaki sposób .NET Framework nawiązuje połączenie z siecią.</span><span class="sxs-lookup"><span data-stu-id="a669e-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a669e-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a669e-123">Remarks</span></span>  

 <span data-ttu-id="a669e-124">`webRequestModules`Element rejestruje elementy podrzędne <xref:System.Net.WebRequest> klasy do obsługi żądań informacji do hostów sieciowych.</span><span class="sxs-lookup"><span data-stu-id="a669e-124">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="a669e-125">Moduły żądania sieci Web muszą implementować <xref:System.Net.IWebRequestCreate> interfejs.</span><span class="sxs-lookup"><span data-stu-id="a669e-125">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="a669e-126">.NET Framework obejmuje moduły żądania sieci Web dla identyfikatorów URI zaczynających się od `http://` , `https://` i `file://` .</span><span class="sxs-lookup"><span data-stu-id="a669e-126">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="a669e-127">Moduły domyślne można zastąpić tylko przez zarejestrowanie modułu niestandardowego w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="a669e-127">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a669e-128">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="a669e-128">Configuration Files</span></span>  

 <span data-ttu-id="a669e-129">Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a669e-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a669e-130">Przykład</span><span class="sxs-lookup"><span data-stu-id="a669e-130">Example</span></span>  

 <span data-ttu-id="a669e-131">Poniższy przykład rejestruje domyślny moduł HTTP.</span><span class="sxs-lookup"><span data-stu-id="a669e-131">The following example registers the default HTTP module.</span></span> <span data-ttu-id="a669e-132">Należy zastąpić wartości wersji i PublicKeyToken wartościami prawidłowymi dla określonego modułu.</span><span class="sxs-lookup"><span data-stu-id="a669e-132">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a669e-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a669e-133">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="a669e-134">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="a669e-134">Network Settings Schema</span></span>](index.md)
