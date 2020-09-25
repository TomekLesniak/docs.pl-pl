---
title: <clear>, element dla webRequestModules (ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
ms.openlocfilehash: 892058dd8af8a38bd7bde868b34a2c6899d9a989
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184043"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="c2520-102">\<clear>, element dla webRequestModules (ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="c2520-102">\<clear> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="c2520-103">Usuwa wszystkie zarejestrowane moduły żądania sieci Web z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c2520-103">Removes all registered Web request modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="c2520-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c2520-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2520-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="c2520-105">Attributes and Elements</span></span>  

 <span data-ttu-id="c2520-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="c2520-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2520-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="c2520-107">Attributes</span></span>  

 <span data-ttu-id="c2520-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="c2520-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c2520-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="c2520-109">Child Elements</span></span>  

 <span data-ttu-id="c2520-110">Brak.</span><span class="sxs-lookup"><span data-stu-id="c2520-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c2520-111">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="c2520-111">Parent Elements</span></span>  
  
|<span data-ttu-id="c2520-112">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="c2520-112">**Element**</span></span>|<span data-ttu-id="c2520-113">**Opis**</span><span class="sxs-lookup"><span data-stu-id="c2520-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c2520-114">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="c2520-114">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="c2520-115">Określa moduły, które mają być używane do żądania informacji z hostów sieciowych.</span><span class="sxs-lookup"><span data-stu-id="c2520-115">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2520-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c2520-116">Remarks</span></span>  

 <span data-ttu-id="c2520-117">`clear`Element usuwa wszystkie zarejestrowane moduły żądania sieci Web, które zostały zdefiniowane wcześniej w pliku konfiguracyjnym lub na wyższym poziomie w hierarchii konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c2520-117">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c2520-118">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="c2520-118">Configuration Files</span></span>  

 <span data-ttu-id="c2520-119">Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c2520-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2520-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="c2520-120">Example</span></span>  

 <span data-ttu-id="c2520-121">Poniższy przykład czyści wszystkie moduły żądania sieci Web, a następnie rejestruje moduł żądania sieci Web dla protokołu HTTP.</span><span class="sxs-lookup"><span data-stu-id="c2520-121">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2520-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c2520-122">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="c2520-123">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="c2520-123">Network Settings Schema</span></span>](index.md)
