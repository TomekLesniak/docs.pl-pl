---
title: <remove>, element dla connectionManagement (ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
ms.openlocfilehash: 46157482d7ceb42b352c68dc9b0eab4f7688bc5c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176178"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="5f1bd-102">\<remove>, element dla connectionManagement (ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="5f1bd-102">\<remove> Element for connectionManagement (Network Settings)</span></span>

<span data-ttu-id="5f1bd-103">Usuwa adres IP lub nazwę DNS z listy zarządzania połączeniami.</span><span class="sxs-lookup"><span data-stu-id="5f1bd-103">Removes an IP address or DNS name from the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="5f1bd-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5f1bd-104">Syntax</span></span>  
  
```xml  
<remove
  address="server name or IP address"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f1bd-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="5f1bd-105">Attributes and Elements</span></span>  

 <span data-ttu-id="5f1bd-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="5f1bd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f1bd-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="5f1bd-107">Attributes</span></span>  
  
|<span data-ttu-id="5f1bd-108">**Atrybut**</span><span class="sxs-lookup"><span data-stu-id="5f1bd-108">**Attribute**</span></span>|<span data-ttu-id="5f1bd-109">**Opis**</span><span class="sxs-lookup"><span data-stu-id="5f1bd-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="5f1bd-110">Adres IP lub nazwa DNS.</span><span class="sxs-lookup"><span data-stu-id="5f1bd-110">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5f1bd-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="5f1bd-111">Child Elements</span></span>  

 <span data-ttu-id="5f1bd-112">Brak.</span><span class="sxs-lookup"><span data-stu-id="5f1bd-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5f1bd-113">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="5f1bd-113">Parent Elements</span></span>  
  
|<span data-ttu-id="5f1bd-114">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="5f1bd-114">**Element**</span></span>|<span data-ttu-id="5f1bd-115">**Opis**</span><span class="sxs-lookup"><span data-stu-id="5f1bd-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5f1bd-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="5f1bd-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="5f1bd-117">Określa maksymalną liczbę połączeń z hostem sieciowym.</span><span class="sxs-lookup"><span data-stu-id="5f1bd-117">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f1bd-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5f1bd-118">Remarks</span></span>  

 <span data-ttu-id="5f1bd-119">`remove`Element usuwa wpis listy zarządzania połączeniami dla określonego serwera.</span><span class="sxs-lookup"><span data-stu-id="5f1bd-119">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="5f1bd-120">Wartość `address` atrybutu powinna być prawidłowym adresem IP lub nazwą hosta.</span><span class="sxs-lookup"><span data-stu-id="5f1bd-120">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5f1bd-121">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="5f1bd-121">Configuration Files</span></span>  

 <span data-ttu-id="5f1bd-122">Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5f1bd-122">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f1bd-123">Przykład</span><span class="sxs-lookup"><span data-stu-id="5f1bd-123">Example</span></span>  

 <span data-ttu-id="5f1bd-124">Poniższy przykład usuwa wszystkie wpisy listy zarządzania połączeniami dla serwera `www.adventure-works.com` , a następnie konfiguruje aplikację do korzystania z czterech połączeń z serwerem `www.contoso.com` i dwóch połączeń z innymi serwerami.</span><span class="sxs-lookup"><span data-stu-id="5f1bd-124">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f1bd-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5f1bd-125">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="5f1bd-126">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="5f1bd-126">Network Settings Schema</span></span>](index.md)
