---
title: <add>, element dla webRequestModules (ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
ms.openlocfilehash: 8d792b967d967540469dca7c090e0f905ecb2e6b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201762"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="f3545-102">\<add>, element dla webRequestModules (ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="f3545-102">\<add> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="f3545-103">Dodaje niestandardowy moduł żądania sieci Web do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f3545-103">Adds a custom Web request module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="f3545-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f3545-104">Syntax</span></span>  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3545-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="f3545-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f3545-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="f3545-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3545-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="f3545-107">Attributes</span></span>  
  
|<span data-ttu-id="f3545-108">**Atrybut**</span><span class="sxs-lookup"><span data-stu-id="f3545-108">**Attribute**</span></span>|<span data-ttu-id="f3545-109">**Opis**</span><span class="sxs-lookup"><span data-stu-id="f3545-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="f3545-110">Prefiks identyfikatora URI dla żądań obsłużonych przez ten moduł żądania sieci Web.</span><span class="sxs-lookup"><span data-stu-id="f3545-110">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="f3545-111">W pełni kwalifikowana nazwa typu (wskazywana przez <xref:System.Type.FullName%2A> Właściwość) i nazwa zestawu (wskazywanym przez <xref:System.Reflection.Assembly.FullName%2A> Właściwość) oddzielona przecinkem, który implementuje ten moduł żądania sieci Web.</span><span class="sxs-lookup"><span data-stu-id="f3545-111">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3545-112">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="f3545-112">Child Elements</span></span>  

 <span data-ttu-id="f3545-113">Brak.</span><span class="sxs-lookup"><span data-stu-id="f3545-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3545-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="f3545-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f3545-115">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="f3545-115">**Element**</span></span>|<span data-ttu-id="f3545-116">**Opis**</span><span class="sxs-lookup"><span data-stu-id="f3545-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f3545-117">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="f3545-117">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="f3545-118">Określa moduły, które mają być używane do żądania informacji z hostów sieciowych.</span><span class="sxs-lookup"><span data-stu-id="f3545-118">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3545-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f3545-119">Remarks</span></span>  

 <span data-ttu-id="f3545-120">Ten `prefix` atrybut definiuje prefiks identyfikatora URI, który używa określonego modułu żądania sieci Web.</span><span class="sxs-lookup"><span data-stu-id="f3545-120">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="f3545-121">Moduły żądania sieci Web są zwykle zarejestrowane w celu obsługi określonego protokołu, takiego jak HTTP lub FTP, ale mogą być zarejestrowane w celu obsługi żądania do określonego serwera lub ścieżki na serwerze.</span><span class="sxs-lookup"><span data-stu-id="f3545-121">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="f3545-122">Moduł żądania sieci Web jest tworzony, gdy do metody jest przesyłany prefiks zgodny z identyfikatorem URI <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f3545-122">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="f3545-123">Wartość `prefix` atrybutu powinna być wiodącymi znakami prawidłowego identyfikatora URI.</span><span class="sxs-lookup"><span data-stu-id="f3545-123">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="f3545-124">Na przykład: `http` lub `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="f3545-124">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="f3545-125">Wartość `type` atrybutu powinna być prawidłową nazwą typu i odpowiadającą jej nazwą zestawu, rozdzieloną przecinkami.</span><span class="sxs-lookup"><span data-stu-id="f3545-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="f3545-126">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="f3545-126">Configuration Files</span></span>  

 <span data-ttu-id="f3545-127">Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f3545-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3545-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="f3545-128">Example</span></span>  

 <span data-ttu-id="f3545-129">Poniższy przykład rejestruje niestandardowy moduł żądania sieci Web dla protokołu HTTP.</span><span class="sxs-lookup"><span data-stu-id="f3545-129">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="f3545-130">Należy zastąpić wartości wersji i PublicKeyToken wartościami prawidłowymi dla określonego modułu.</span><span class="sxs-lookup"><span data-stu-id="f3545-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f3545-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f3545-131">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="f3545-132">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="f3545-132">Network Settings Schema</span></span>](index.md)
