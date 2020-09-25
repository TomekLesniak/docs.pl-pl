---
title: <system.Net>, element (ustawienia sieci)
description: <system.Net> ustawień sieciowych zawiera ustawienia, które określają sposób, w jaki .NET Framework łączy się z opcjami sieci w .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 80d54df40c6798e146013b4f2d867386ae35169c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201723"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="d392c-103">\<system.Net>, element (ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="d392c-103">\<system.Net> Element (Network Settings)</span></span>

<span data-ttu-id="d392c-104">Zawiera ustawienia, które określają, w jaki sposób .NET Framework nawiązuje połączenie z siecią.</span><span class="sxs-lookup"><span data-stu-id="d392c-104">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a><span data-ttu-id="d392c-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="d392c-105">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d392c-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="d392c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="d392c-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="d392c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d392c-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="d392c-108">Attributes</span></span>  

 <span data-ttu-id="d392c-109">Brak.</span><span class="sxs-lookup"><span data-stu-id="d392c-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d392c-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="d392c-110">Child Elements</span></span>  
  
|<span data-ttu-id="d392c-111">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="d392c-111">**Element**</span></span>|<span data-ttu-id="d392c-112">**Opis**</span><span class="sxs-lookup"><span data-stu-id="d392c-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d392c-113">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="d392c-113">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="d392c-114">Określa moduły używane do uwierzytelniania żądań internetowych.</span><span class="sxs-lookup"><span data-stu-id="d392c-114">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="d392c-115">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="d392c-115">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="d392c-116">Określa maksymalną liczbę połączeń z hostem internetowym.</span><span class="sxs-lookup"><span data-stu-id="d392c-116">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="d392c-117">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="d392c-117">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="d392c-118">Konfiguruje serwer proxy protokołu HTTP (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="d392c-118">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="d392c-119">mailSettings</span><span class="sxs-lookup"><span data-stu-id="d392c-119">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="d392c-120">Konfiguruje opcje wysyłania poczty SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="d392c-120">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="d392c-121">requestCaching</span><span class="sxs-lookup"><span data-stu-id="d392c-121">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="d392c-122">Kontroluje mechanizm buforowania dla żądań sieci.</span><span class="sxs-lookup"><span data-stu-id="d392c-122">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="d392c-123">ustawienia</span><span class="sxs-lookup"><span data-stu-id="d392c-123">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="d392c-124">Konfiguruje podstawowe opcje sieci dla klas w <xref:System.Net> i powiązanych podrzędnych obszarach nazw.</span><span class="sxs-lookup"><span data-stu-id="d392c-124">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="d392c-125">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="d392c-125">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="d392c-126">Określa moduły, które mają być używane do żądania informacji z hostów internetowych.</span><span class="sxs-lookup"><span data-stu-id="d392c-126">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d392c-127">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="d392c-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d392c-128">**Postaci**</span><span class="sxs-lookup"><span data-stu-id="d392c-128">**Element**</span></span>|<span data-ttu-id="d392c-129">**Opis**</span><span class="sxs-lookup"><span data-stu-id="d392c-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d392c-130">skonfigurować</span><span class="sxs-lookup"><span data-stu-id="d392c-130">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="d392c-131">Zawiera ustawienia dla wszystkich przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="d392c-131">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d392c-132">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d392c-132">Remarks</span></span>  

 <span data-ttu-id="d392c-133">[\<system.net>](system-net-element-network-settings.md)Element zawiera ustawienia dla klas z <xref:System.Net> i powiązane podrzędne przestrzenie nazw.</span><span class="sxs-lookup"><span data-stu-id="d392c-133">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="d392c-134">Ustawienia Konfiguruj moduły uwierzytelniania, zarządzanie połączeniami, ustawienia poczty, serwer proxy i moduły żądania internetowe, aby otrzymywać informacje z hostów internetowych.</span><span class="sxs-lookup"><span data-stu-id="d392c-134">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d392c-135">Przykład</span><span class="sxs-lookup"><span data-stu-id="d392c-135">Example</span></span>  

 <span data-ttu-id="d392c-136">Poniższy przykład przedstawia typową konfigurację używaną przez <xref:System.Net> klasy.</span><span class="sxs-lookup"><span data-stu-id="d392c-136">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d392c-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d392c-137">See also</span></span>

- [<span data-ttu-id="d392c-138">Schemat ustawień sieciowych</span><span class="sxs-lookup"><span data-stu-id="d392c-138">Network Settings Schema</span></span>](index.md)
