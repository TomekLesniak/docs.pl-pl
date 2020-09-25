---
title: <authenticationModules>, element (ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: 154a73a5fe3fa9e2b6b1c9e5c462b76bdc1ba640
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201749"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="32115-102">\<authenticationModules>, element (ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="32115-102">\<authenticationModules> Element (Network Settings)</span></span>

<span data-ttu-id="32115-103">Określa moduły używane do uwierzytelniania żądań sieci.</span><span class="sxs-lookup"><span data-stu-id="32115-103">Specifies modules used to authenticate network requests.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**

## <a name="syntax"></a><span data-ttu-id="32115-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="32115-104">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32115-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="32115-105">Attributes and Elements</span></span>  

 <span data-ttu-id="32115-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="32115-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32115-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="32115-107">Attributes</span></span>  

 <span data-ttu-id="32115-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="32115-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="32115-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="32115-109">Child Elements</span></span>  
  
|<span data-ttu-id="32115-110">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="32115-110">**Element**</span></span>|<span data-ttu-id="32115-111">**Opis**</span><span class="sxs-lookup"><span data-stu-id="32115-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="32115-112">add</span><span class="sxs-lookup"><span data-stu-id="32115-112">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="32115-113">Dodaje moduł uwierzytelniania do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="32115-113">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="32115-114">Wyczyść</span><span class="sxs-lookup"><span data-stu-id="32115-114">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="32115-115">Czyści wszystkie moduły uwierzytelniania z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="32115-115">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="32115-116">usuwa</span><span class="sxs-lookup"><span data-stu-id="32115-116">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="32115-117">Usuwa moduł uwierzytelniania z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="32115-117">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="32115-118">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="32115-118">Parent Elements</span></span>  
  
|<span data-ttu-id="32115-119">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="32115-119">**Element**</span></span>|<span data-ttu-id="32115-120">**Opis**</span><span class="sxs-lookup"><span data-stu-id="32115-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="32115-121">system.net</span><span class="sxs-lookup"><span data-stu-id="32115-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="32115-122">Zawiera ustawienia, które określają, w jaki sposób .NET Framework nawiązuje połączenie z siecią.</span><span class="sxs-lookup"><span data-stu-id="32115-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32115-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="32115-123">Remarks</span></span>  

 <span data-ttu-id="32115-124">`authenticationModule`Element określa moduły uwierzytelniania, które przeprowadzą proces uwierzytelniania z serwerem.</span><span class="sxs-lookup"><span data-stu-id="32115-124">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="32115-125">Moduł uwierzytelniania musi implementować <xref:System.Net.IAuthenticationModule> interfejs.</span><span class="sxs-lookup"><span data-stu-id="32115-125">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="32115-126">Pliki konfiguracji</span><span class="sxs-lookup"><span data-stu-id="32115-126">Configuration Files</span></span>  

 <span data-ttu-id="32115-127">Tego elementu można użyć w pliku konfiguracyjnym aplikacji lub pliku konfiguracji komputera (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="32115-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="32115-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="32115-128">Example</span></span>  

 <span data-ttu-id="32115-129">Poniższy przykład umożliwia włączenie modułu uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="32115-129">The following example enables an authentication module.</span></span> <span data-ttu-id="32115-130">Należy zastąpić wartości wersji i PublicKeyToken wartościami prawidłowymi dla określonego modułu.</span><span class="sxs-lookup"><span data-stu-id="32115-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="32115-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="32115-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="32115-132">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="32115-132">Network Settings Schema</span></span>](index.md)
