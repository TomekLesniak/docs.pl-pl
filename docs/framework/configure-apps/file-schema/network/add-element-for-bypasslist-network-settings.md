---
title: <add>, element dla bypasslist (ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 927a43f352fd776d9e6ba52ebea6ba2a1ccd4d48
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149494"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="ee3b6-102">\<add>, element dla bypasslist (ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="ee3b6-102">\<add> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="ee3b6-103">Dodaje adres IP lub nazwę DNS do listy obejścia serwera proxy.</span><span class="sxs-lookup"><span data-stu-id="ee3b6-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="ee3b6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ee3b6-104">Syntax</span></span>  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee3b6-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="ee3b6-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ee3b6-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="ee3b6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee3b6-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="ee3b6-107">Attributes</span></span>  
  
|<span data-ttu-id="ee3b6-108">**Atrybut**</span><span class="sxs-lookup"><span data-stu-id="ee3b6-108">**Attribute**</span></span>|<span data-ttu-id="ee3b6-109">**Opis**</span><span class="sxs-lookup"><span data-stu-id="ee3b6-109">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="ee3b6-110">**Ulica**</span><span class="sxs-lookup"><span data-stu-id="ee3b6-110">**address**</span></span>|<span data-ttu-id="ee3b6-111">Wyrażenie regularne opisujące adres IP lub nazwę DNS.</span><span class="sxs-lookup"><span data-stu-id="ee3b6-111">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee3b6-112">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="ee3b6-112">Child Elements</span></span>  

 <span data-ttu-id="ee3b6-113">Brak.</span><span class="sxs-lookup"><span data-stu-id="ee3b6-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee3b6-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="ee3b6-114">Parent Elements</span></span>  
  
|<span data-ttu-id="ee3b6-115">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="ee3b6-115">**Element**</span></span>|<span data-ttu-id="ee3b6-116">**Opis**</span><span class="sxs-lookup"><span data-stu-id="ee3b6-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ee3b6-117">bypasslist</span><span class="sxs-lookup"><span data-stu-id="ee3b6-117">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="ee3b6-118">Zawiera zestaw wyrażeń regularnych, które opisują adresy, które nie korzystają z serwera proxy.</span><span class="sxs-lookup"><span data-stu-id="ee3b6-118">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee3b6-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ee3b6-119">Remarks</span></span>  

 <span data-ttu-id="ee3b6-120">`add`Element wstawia wyrażenia regularne opisujące adresy IP lub nazwy serwerów DNS do listy adresów, które pomijają serwer proxy.</span><span class="sxs-lookup"><span data-stu-id="ee3b6-120">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="ee3b6-121">Wartość `address` atrybutu powinna być wyrażeniem regularnym opisującym zestaw adresów IP lub nazw hostów.</span><span class="sxs-lookup"><span data-stu-id="ee3b6-121">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="ee3b6-122">Należy zachować ostrożność podczas określania wyrażenia regularnego dla tego elementu.</span><span class="sxs-lookup"><span data-stu-id="ee3b6-122">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="ee3b6-123">Wyrażenie regularne "[a-z] + \\ . contoso \\ . com" dopasowuje dowolny host w domenie contoso.com, ale również jest zgodny z dowolnym hostem w domenie contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="ee3b6-123">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="ee3b6-124">Aby dopasować tylko hosta w domenie contoso.com, użyj kotwicy ("$"): "[a-z] + \\ . contoso \\ . com $".</span><span class="sxs-lookup"><span data-stu-id="ee3b6-124">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="ee3b6-125">Aby uzyskać więcej informacji na temat wyrażeń regularnych, zobacz. [.NET Framework wyrażeń regularnych](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ee3b6-125">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ee3b6-126">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="ee3b6-126">Configuration Files</span></span>  

 <span data-ttu-id="ee3b6-127">Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ee3b6-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee3b6-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="ee3b6-128">Example</span></span>  

 <span data-ttu-id="ee3b6-129">Poniższy przykład dodaje dwa adresy do listy pomijania.</span><span class="sxs-lookup"><span data-stu-id="ee3b6-129">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="ee3b6-130">Najpierw pomija serwer proxy dla wszystkich serwerów w domenie contoso.com; drugi pomija serwer proxy dla wszystkich serwerów, których adres IP rozpoczyna się od 192,168.</span><span class="sxs-lookup"><span data-stu-id="ee3b6-130">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee3b6-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ee3b6-131">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="ee3b6-132">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="ee3b6-132">Network Settings Schema</span></span>](index.md)
