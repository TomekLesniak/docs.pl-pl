---
title: <remove>, element dla webRequestModules (ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: 65e8b1f2088015b86d4f981f07875d236a11a617
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176191"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="cd845-102">\<remove>, element dla webRequestModules (ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="cd845-102">\<remove> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="cd845-103">Usuwa niestandardowy moduł żądania sieci Web z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="cd845-103">Removes a custom Web request module from the application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**
  
## <a name="syntax"></a><span data-ttu-id="cd845-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cd845-104">Syntax</span></span>  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd845-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="cd845-105">Attributes and Elements</span></span>  

 <span data-ttu-id="cd845-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="cd845-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd845-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="cd845-107">Attributes</span></span>  
  
|<span data-ttu-id="cd845-108">**Atrybut**</span><span class="sxs-lookup"><span data-stu-id="cd845-108">**Attribute**</span></span>|<span data-ttu-id="cd845-109">**Opis**</span><span class="sxs-lookup"><span data-stu-id="cd845-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="cd845-110">Prefiks identyfikatora URI dla żądań obsłużonych przez ten moduł żądania sieci Web.</span><span class="sxs-lookup"><span data-stu-id="cd845-110">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd845-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="cd845-111">Child Elements</span></span>  

 <span data-ttu-id="cd845-112">Brak.</span><span class="sxs-lookup"><span data-stu-id="cd845-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd845-113">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="cd845-113">Parent Elements</span></span>  
  
|<span data-ttu-id="cd845-114">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="cd845-114">**Element**</span></span>|<span data-ttu-id="cd845-115">**Opis**</span><span class="sxs-lookup"><span data-stu-id="cd845-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cd845-116">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="cd845-116">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="cd845-117">Określa moduły, które mają być używane do żądania informacji z hostów sieciowych.</span><span class="sxs-lookup"><span data-stu-id="cd845-117">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd845-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cd845-118">Remarks</span></span>  

 <span data-ttu-id="cd845-119">`remove`Element usuwa zarejestrowany moduł żądania sieci Web dla określonego prefiksu URI.</span><span class="sxs-lookup"><span data-stu-id="cd845-119">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="cd845-120">Wartość `prefix` atrybutu powinna być wiodącymi znakami prawidłowego identyfikatora URI — na przykład " `http` " lub " `http://www.contoso.com` ".</span><span class="sxs-lookup"><span data-stu-id="cd845-120">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cd845-121">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="cd845-121">Configuration Files</span></span>  

 <span data-ttu-id="cd845-122">Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="cd845-122">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd845-123">Przykład</span><span class="sxs-lookup"><span data-stu-id="cd845-123">Example</span></span>  

<span data-ttu-id="cd845-124">Poniższy przykład usuwa istniejący moduł żądania sieci Web dla protokołu HTTP, a następnie rejestruje nowy niestandardowy moduł żądania sieci Web dla żądań HTTP `www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="cd845-124">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd845-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cd845-125">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="cd845-126">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="cd845-126">Network Settings Schema</span></span>](index.md)
