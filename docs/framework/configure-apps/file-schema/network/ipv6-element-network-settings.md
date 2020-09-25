---
title: <ipv6>, element (ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: 44ef0b8e1b6dc6ad0efde6b26ad7d4700e06f2c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178336"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="a0017-102">\<ipv6>, element (ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="a0017-102">\<ipv6> Element (Network Settings)</span></span>

<span data-ttu-id="a0017-103">Włącza odpowiedzi protokołu internetowego w wersji 6 (IPv6) od przestarzałych elementów członkowskich <xref:System.Net.Dns> klasy.</span><span class="sxs-lookup"><span data-stu-id="a0017-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ipv6>**

## <a name="syntax"></a><span data-ttu-id="a0017-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a0017-104">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0017-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="a0017-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a0017-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="a0017-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0017-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="a0017-107">Attributes</span></span>  
  
|<span data-ttu-id="a0017-108">**Atrybut**</span><span class="sxs-lookup"><span data-stu-id="a0017-108">**Attribute**</span></span>|<span data-ttu-id="a0017-109">**Opis**</span><span class="sxs-lookup"><span data-stu-id="a0017-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="a0017-110">Określa, czy elementy członkowskie <xref:System.Net.Dns> klasy zwracają adresy protokołu internetowego w wersji 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="a0017-110">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="a0017-111">Wartość domyślna to `false`.</span><span class="sxs-lookup"><span data-stu-id="a0017-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0017-112">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="a0017-112">Child Elements</span></span>  

 <span data-ttu-id="a0017-113">Brak.</span><span class="sxs-lookup"><span data-stu-id="a0017-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0017-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="a0017-114">Parent Elements</span></span>  
  
|<span data-ttu-id="a0017-115">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="a0017-115">**Element**</span></span>|<span data-ttu-id="a0017-116">**Opis**</span><span class="sxs-lookup"><span data-stu-id="a0017-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a0017-117">ustawienia</span><span class="sxs-lookup"><span data-stu-id="a0017-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="a0017-118">Konfiguruje podstawowe opcje sieci dla <xref:System.Net> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="a0017-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0017-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a0017-119">Remarks</span></span>  

 <span data-ttu-id="a0017-120">To ustawienie umożliwia obsługę protokołu IPv6 dla przestarzałych elementów członkowskich <xref:System.Net.Dns> klasy: <xref:System.Net.Dns.BeginGetHostByName%2A> ,,,,, <xref:System.Net.Dns.BeginResolve%2A> <xref:System.Net.Dns.EndGetHostByName%2A> <xref:System.Net.Dns.EndResolve%2A> <xref:System.Net.Dns.GetHostByAddress%2A> <xref:System.Net.Dns.GetHostByName%2A> i <xref:System.Net.Dns.Resolve%2A> .</span><span class="sxs-lookup"><span data-stu-id="a0017-120">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="a0017-121">W przypadku innych elementów członkowskich <xref:System.Net?displayProperty=nameWithType> przestrzeni nazw adresy IPv6 mogą być zwracane, jeśli w systemie operacyjnym jest włączony protokół IPv6.</span><span class="sxs-lookup"><span data-stu-id="a0017-121">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a0017-122">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="a0017-122">Configuration Files</span></span>  

 <span data-ttu-id="a0017-123">Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a0017-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0017-124">Przykład</span><span class="sxs-lookup"><span data-stu-id="a0017-124">Example</span></span>  

 <span data-ttu-id="a0017-125">Poniższy przykład pokazuje, jak włączyć obsługę protokołu IPv6 dla <xref:System.Net.Dns> klasy.</span><span class="sxs-lookup"><span data-stu-id="a0017-125">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0017-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a0017-126">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a0017-127">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="a0017-127">Network Settings Schema</span></span>](index.md)
