---
title: Schemat ustawień sieci
description: Informacje o schemacie dla ustawień sieci, które określają, w jaki sposób .NET Framework nawiązuje połączenie z Internetem i obsługuje identyfikatory URI.
ms.date: 03/30/2017
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
ms.openlocfilehash: 8071fcfcdb16b6e71d8d7af05a704d8842b3e963
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158919"
---
# <a name="network-settings-schema"></a><span data-ttu-id="01095-103">Schemat ustawień sieci</span><span class="sxs-lookup"><span data-stu-id="01095-103">Network Settings Schema</span></span>

<span data-ttu-id="01095-104">Ustawienia sieci określają, w jaki sposób .NET Framework nawiązuje połączenie z Internetem.</span><span class="sxs-lookup"><span data-stu-id="01095-104">Network settings specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="01095-105">\<system.net>Ustawienia określają, w jaki sposób .NET Framework nawiązuje połączenie z siecią.</span><span class="sxs-lookup"><span data-stu-id="01095-105">The \<system.net> settings specify how the .NET Framework connects to the network.</span></span> <span data-ttu-id="01095-106">W poniższej tabeli opisano funkcję każdego podrzędnego elementu konfiguracji w ramach [ \<system.Net> elementu (Ustawienia sieci)](system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="01095-106">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="01095-107">Element</span><span class="sxs-lookup"><span data-stu-id="01095-107">Element</span></span>|<span data-ttu-id="01095-108">Opis</span><span class="sxs-lookup"><span data-stu-id="01095-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01095-109">\<authenticationModules> — Element (Ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="01095-109">\<authenticationModules> Element (Network Settings)</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="01095-110">Określa moduły używane do uwierzytelniania żądań internetowych.</span><span class="sxs-lookup"><span data-stu-id="01095-110">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="01095-111">\<connectionManagement> — Element (Ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="01095-111">\<connectionManagement> Element (Network Settings)</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="01095-112">Określa maksymalną liczbę połączeń z hostami internetowymi.</span><span class="sxs-lookup"><span data-stu-id="01095-112">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="01095-113">\<defaultProxy> — Element (Ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="01095-113">\<defaultProxy> Element (Network Settings)</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="01095-114">Określa serwer proxy używany przez żądania HTTP do Internetu.</span><span class="sxs-lookup"><span data-stu-id="01095-114">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="01095-115">\<mailSettings> — Element (Ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="01095-115">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="01095-116">Zawiera ustawienia dla opcji wysyłania poczty.</span><span class="sxs-lookup"><span data-stu-id="01095-116">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="01095-117">\<requestCaching> — Element (Ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="01095-117">\<requestCaching> Element (Network Settings)</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="01095-118">Kontroluje mechanizm buforowania dla żądań sieci.</span><span class="sxs-lookup"><span data-stu-id="01095-118">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="01095-119">\<webRequestModules> — Element (Ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="01095-119">\<webRequestModules> Element (Network Settings)</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="01095-120">Określa moduły używane do żądania informacji z hostów internetowych.</span><span class="sxs-lookup"><span data-stu-id="01095-120">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
<span data-ttu-id="01095-121">\<uri>Ustawienia określają, w jaki sposób .NET Framework obsługuje adresy sieci Web wyrażone przy użyciu Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="01095-121">The \<uri> settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="01095-122">W poniższej tabeli opisano funkcję każdego podrzędnego elementu konfiguracji w ramach [ \<uri> elementu (ustawienia identyfikatora URI)](uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="01095-122">The following table describes the function of each child configuration element under the [\<uri> Element (Uri Settings)](uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="01095-123">Element</span><span class="sxs-lookup"><span data-stu-id="01095-123">Element</span></span>|<span data-ttu-id="01095-124">Opis</span><span class="sxs-lookup"><span data-stu-id="01095-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01095-125">\<idn> — Element (ustawienia identyfikatora URI)</span><span class="sxs-lookup"><span data-stu-id="01095-125">\<idn> Element (Uri Settings)</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="01095-126">Określa, czy do nazw domen są stosowane analizowanie międzynarodowych nazw domen (IDN).</span><span class="sxs-lookup"><span data-stu-id="01095-126">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="01095-127">\<iriParsing> — Element (ustawienia identyfikatora URI)</span><span class="sxs-lookup"><span data-stu-id="01095-127">\<iriParsing> Element (Uri Settings)</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="01095-128">Określa, czy do <xref:System.Uri> i czy należy zastosować analizę IRI (International Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="01095-128">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="01095-129">\<schemeSettings> — Element (ustawienia identyfikatora URI)</span><span class="sxs-lookup"><span data-stu-id="01095-129">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="01095-130">Określa, w jaki sposób <xref:System.Uri> będzie analizowana dla określonych schematów.</span><span class="sxs-lookup"><span data-stu-id="01095-130">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01095-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="01095-131">See also</span></span>

- [<span data-ttu-id="01095-132">Konfigurowanie aplikacji internetowych</span><span class="sxs-lookup"><span data-stu-id="01095-132">Configuring Internet Applications</span></span>](../../../network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="01095-133">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="01095-133">Configuration File Schema</span></span>](../index.md)
