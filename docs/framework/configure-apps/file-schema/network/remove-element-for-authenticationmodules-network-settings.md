---
title: <remove>, element dla authenticationModules (ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
ms.openlocfilehash: 0829f57d8dca91c2d895085dceaeea422229537c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176204"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="96353-102">\<remove>, element dla authenticationModules (ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="96353-102">\<remove> Element for authenticationModules (Network Settings)</span></span>

<span data-ttu-id="96353-103">Usuwa moduł uwierzytelniania z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="96353-103">Removes an authentication module from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="96353-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="96353-104">Syntax</span></span>  
  
```xml  
<remove
   type="authentication module name"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96353-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="96353-105">Attributes and Elements</span></span>  

 <span data-ttu-id="96353-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="96353-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96353-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="96353-107">Attributes</span></span>  
  
|<span data-ttu-id="96353-108">**Atrybut**</span><span class="sxs-lookup"><span data-stu-id="96353-108">**Attribute**</span></span>|<span data-ttu-id="96353-109">**Opis**</span><span class="sxs-lookup"><span data-stu-id="96353-109">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="96353-110">**Wprowadź**</span><span class="sxs-lookup"><span data-stu-id="96353-110">**type**</span></span>|<span data-ttu-id="96353-111">Nazwa modułu uwierzytelniania do usunięcia.</span><span class="sxs-lookup"><span data-stu-id="96353-111">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96353-112">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="96353-112">Child Elements</span></span>  

 <span data-ttu-id="96353-113">Brak.</span><span class="sxs-lookup"><span data-stu-id="96353-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="96353-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="96353-114">Parent Elements</span></span>  
  
|<span data-ttu-id="96353-115">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="96353-115">**Element**</span></span>|<span data-ttu-id="96353-116">**Opis**</span><span class="sxs-lookup"><span data-stu-id="96353-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="96353-117">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="96353-117">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="96353-118">Określa moduły używane do uwierzytelniania żądań sieci.</span><span class="sxs-lookup"><span data-stu-id="96353-118">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96353-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="96353-119">Remarks</span></span>  

 <span data-ttu-id="96353-120">`remove`Element usuwa moduły uwierzytelniania zdefiniowane wcześniej w pliku konfiguracyjnym lub na wyższym poziomie w hierarchii konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="96353-120">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="96353-121">Wartość `type` atrybutu powinna być prawidłową nazwą klasy.</span><span class="sxs-lookup"><span data-stu-id="96353-121">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="96353-122">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="96353-122">Configuration Files</span></span>  

 <span data-ttu-id="96353-123">Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="96353-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="96353-124">Przykład</span><span class="sxs-lookup"><span data-stu-id="96353-124">Example</span></span>  

 <span data-ttu-id="96353-125">Poniższy przykład usuwa moduł uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="96353-125">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="96353-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="96353-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="96353-127">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="96353-127">Network Settings Schema</span></span>](index.md)
