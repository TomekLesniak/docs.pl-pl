---
title: <clear>, element dla authenticationModules (ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, authenticationModules
- <authenticationModules>, clear element
- <clear> element, authenticationModules
- authenticationModules, clear element
ms.assetid: dc522c45-4a80-4831-8955-f7b68a47edfd
ms.openlocfilehash: 6ac2287ba9b17727835d43a3e3b8876f210fb5c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167330"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="566fb-102">\<clear>, element dla authenticationModules (ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="566fb-102">\<clear> Element for authenticationModules (Network Settings)</span></span>

<span data-ttu-id="566fb-103">Czyści wszystkie moduły uwierzytelniania z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="566fb-103">Clears all authentication modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="566fb-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="566fb-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="566fb-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="566fb-105">Attributes and Elements</span></span>  

 <span data-ttu-id="566fb-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="566fb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="566fb-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="566fb-107">Attributes</span></span>  

 <span data-ttu-id="566fb-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="566fb-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="566fb-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="566fb-109">Child Elements</span></span>  

 <span data-ttu-id="566fb-110">Brak.</span><span class="sxs-lookup"><span data-stu-id="566fb-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="566fb-111">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="566fb-111">Parent Elements</span></span>  
  
|<span data-ttu-id="566fb-112">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="566fb-112">**Element**</span></span>|<span data-ttu-id="566fb-113">**Opis**</span><span class="sxs-lookup"><span data-stu-id="566fb-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="566fb-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="566fb-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="566fb-115">Określa moduły używane do uwierzytelniania żądań sieci.</span><span class="sxs-lookup"><span data-stu-id="566fb-115">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="566fb-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="566fb-116">Remarks</span></span>  

 <span data-ttu-id="566fb-117">`clear`Element usuwa wszystkie moduły uwierzytelniania zdefiniowane wcześniej w pliku konfiguracyjnym lub na wyższym poziomie w hierarchii konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="566fb-117">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="566fb-118">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="566fb-118">Configuration Files</span></span>  

 <span data-ttu-id="566fb-119">Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="566fb-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="566fb-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="566fb-120">Example</span></span>  

 <span data-ttu-id="566fb-121">Poniższy przykład usuwa wszystkie skonfigurowane moduły uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="566fb-121">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="566fb-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="566fb-122">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="566fb-123">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="566fb-123">Network Settings Schema</span></span>](index.md)
