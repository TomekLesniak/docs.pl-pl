---
title: <connectionManagement>, element (ustawienia sieci)
description: <connectionManagement>Element ustawienia sieci określa maksymalną liczbę połączeń z hostem sieciowym w .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 52b780c739a00cb53694b547ee1a33c1b5d98c86
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167317"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="19ef8-103">\<connectionManagement>, element (ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="19ef8-103">\<connectionManagement> Element (Network Settings)</span></span>

<span data-ttu-id="19ef8-104">Określa maksymalną liczbę połączeń z hostem sieciowym.</span><span class="sxs-lookup"><span data-stu-id="19ef8-104">Specifies the maximum number of connections to a network host.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**

## <a name="syntax"></a><span data-ttu-id="19ef8-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="19ef8-105">Syntax</span></span>  
  
```xml  
<connectionManagement>
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19ef8-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="19ef8-106">Attributes and Elements</span></span>  

 <span data-ttu-id="19ef8-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="19ef8-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19ef8-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="19ef8-108">Attributes</span></span>  

 <span data-ttu-id="19ef8-109">Brak.</span><span class="sxs-lookup"><span data-stu-id="19ef8-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="19ef8-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="19ef8-110">Child Elements</span></span>  
  
|<span data-ttu-id="19ef8-111">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="19ef8-111">**Element**</span></span>|<span data-ttu-id="19ef8-112">**Opis**</span><span class="sxs-lookup"><span data-stu-id="19ef8-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="19ef8-113">add</span><span class="sxs-lookup"><span data-stu-id="19ef8-113">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="19ef8-114">Dodaje adres IP lub nazwę DNS do listy zarządzania połączeniami.</span><span class="sxs-lookup"><span data-stu-id="19ef8-114">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="19ef8-115">Wyczyść</span><span class="sxs-lookup"><span data-stu-id="19ef8-115">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="19ef8-116">Czyści listę zarządzania połączeniami.</span><span class="sxs-lookup"><span data-stu-id="19ef8-116">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="19ef8-117">usuwa</span><span class="sxs-lookup"><span data-stu-id="19ef8-117">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="19ef8-118">Usuwa adres IP lub nazwę DNS z listy zarządzania połączeniami.</span><span class="sxs-lookup"><span data-stu-id="19ef8-118">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19ef8-119">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="19ef8-119">Parent Elements</span></span>  
  
|<span data-ttu-id="19ef8-120">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="19ef8-120">**Element**</span></span>|<span data-ttu-id="19ef8-121">**Opis**</span><span class="sxs-lookup"><span data-stu-id="19ef8-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="19ef8-122">system.net</span><span class="sxs-lookup"><span data-stu-id="19ef8-122">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="19ef8-123">Zawiera ustawienia, które określają, w jaki sposób .NET Framework nawiązuje połączenie z siecią.</span><span class="sxs-lookup"><span data-stu-id="19ef8-123">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19ef8-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="19ef8-124">Remarks</span></span>  

 <span data-ttu-id="19ef8-125">`connectionManagement`Element definiuje maksymalną liczbę połączeń z serwerem lub grupą serwerów.</span><span class="sxs-lookup"><span data-stu-id="19ef8-125">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="19ef8-126">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="19ef8-126">Configuration Files</span></span>  

 <span data-ttu-id="19ef8-127">Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="19ef8-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="19ef8-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="19ef8-128">Example</span></span>  

 <span data-ttu-id="19ef8-129">Poniższy przykład służy do konfigurowania aplikacji do korzystania z czterech połączeń z serwerem `www.contoso.com` i dwóch połączeń z innymi serwerami.</span><span class="sxs-lookup"><span data-stu-id="19ef8-129">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="19ef8-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="19ef8-130">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="19ef8-131">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="19ef8-131">Network Settings Schema</span></span>](index.md)
