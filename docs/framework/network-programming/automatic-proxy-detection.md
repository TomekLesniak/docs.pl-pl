---
title: Automatyczne wykrywanie serwera proxy
description: Informacje o automatycznym wykrywaniu serwera proxy, gdzie system identyfikuje serwer proxy sieci Web i używa go do wysyłania żądań w imieniu klienta.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic proxy detections
- Web Proxy Auto-Discovery
- Web proxy
- detecting proxies automatically
- WebProxy class, automatic proxy detections
- proxies, automatically detecting
- network
- WPAD (Web Proxy Auto-Discovery)
ms.assetid: fcd9c3bd-93de-4c92-8ff3-837327ad18de
ms.openlocfilehash: 8d1b904a8acc6d3960a076c54c2d5f5de54820c0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250635"
---
# <a name="automatic-proxy-detection"></a><span data-ttu-id="515b5-103">Automatyczne wykrywanie serwera proxy</span><span class="sxs-lookup"><span data-stu-id="515b5-103">Automatic Proxy Detection</span></span>

<span data-ttu-id="515b5-104">Automatyczne wykrywanie serwera proxy to proces, za pomocą którego serwer proxy sieci Web jest identyfikowany przez system i używany do wysyłania żądań w imieniu klienta.</span><span class="sxs-lookup"><span data-stu-id="515b5-104">Automatic proxy detection is a process by which a Web proxy server is identified by the system and used to send requests on behalf of the client.</span></span> <span data-ttu-id="515b5-105">Ta funkcja jest nazywana również autowykrywaniem serwera proxy sieci Web (WPAD).</span><span class="sxs-lookup"><span data-stu-id="515b5-105">This feature is also known as Web Proxy Auto-Discovery (WPAD).</span></span> <span data-ttu-id="515b5-106">Gdy automatyczne wykrywanie serwera proxy jest włączone, system próbuje zlokalizować skrypt konfiguracji serwera proxy, który jest odpowiedzialny za zwracanie zestawu serwerów proxy, których można użyć dla żądania.</span><span class="sxs-lookup"><span data-stu-id="515b5-106">When automatic proxy detection is enabled, the system attempts to locate a proxy configuration script that is responsible for returning the set of proxies that can be used for the request.</span></span> <span data-ttu-id="515b5-107">Jeśli zostanie znaleziony skrypt konfiguracji serwera proxy, skrypt zostanie pobrany, skompilowany i uruchomiony na komputerze lokalnym, gdy informacje o serwerze proxy, strumieniu żądania lub odpowiedzi zostaną uzyskane dla żądania, które używa <xref:System.Net.WebProxy> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="515b5-107">If the proxy configuration script is found, the script is downloaded, compiled, and run on the local computer when proxy information, the request stream, or the response is obtained for a request that uses a <xref:System.Net.WebProxy> instance.</span></span>  
  
 <span data-ttu-id="515b5-108">Automatyczne wykrywanie serwera proxy jest wykonywane przez <xref:System.Net.WebProxy> klasę i może korzystać z ustawień na poziomie żądania, ustawień w plikach konfiguracji i ustawień określonych przy użyciu okna dialogowego **sieci lokalnej (LAN)** programu Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="515b5-108">Automatic proxy detection is performed by the <xref:System.Net.WebProxy> class and can employ request-level settings, settings in configuration files, and settings specified using the Internet Explorer **Local Area Network (LAN)** dialog box.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="515b5-109">Możesz wyświetlić okno dialogowe **Ustawienia sieci lokalnej (LAN)** programu Internet Explorer, wybierając pozycję **Narzędzia** z menu głównego programu Internet Explorer, a następnie wybierając pozycję **Opcje internetowe**.</span><span class="sxs-lookup"><span data-stu-id="515b5-109">You can display the Internet Explorer **Local Area Network (LAN) Settings** dialog box by selecting **Tools** from the Internet Explorer main menu and then selecting **Internet Options**.</span></span> <span data-ttu-id="515b5-110">Następnie wybierz kartę **połączenia** , a następnie kliknij pozycję **Ustawienia sieci LAN**.</span><span class="sxs-lookup"><span data-stu-id="515b5-110">Next, select the **Connections** tab, and click **LAN Settings**.</span></span>  
  
 <span data-ttu-id="515b5-111">Gdy automatyczne wykrywanie serwera proxy jest włączone, <xref:System.Net.WebProxy> Klasa próbuje zlokalizować skrypt konfiguracji serwera proxy w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="515b5-111">When automatic proxy detection is enabled, the <xref:System.Net.WebProxy> class attempts to locate the proxy configuration script as follows:</span></span>  
  
1. <span data-ttu-id="515b5-112">Funkcja WinINet `InternetQueryOption` służy do lokalizowania ostatnio wykrytego skryptu konfiguracji serwera proxy przez program Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="515b5-112">The WinINet `InternetQueryOption` function is used to locate the proxy configuration script most recently detected by Internet Explorer.</span></span>  
  
2. <span data-ttu-id="515b5-113">Jeśli skrypt nie znajduje się, <xref:System.Net.WebProxy> Klasa używa Dynamic Host Configuration Protocol (DHCP) do lokalizowania skryptu.</span><span class="sxs-lookup"><span data-stu-id="515b5-113">If the script is not located, the <xref:System.Net.WebProxy> class uses the Dynamic Host Configuration Protocol (DHCP) to locate the script.</span></span> <span data-ttu-id="515b5-114">Serwer DHCP może odpowiedzieć na lokalizację (nazwę hosta) skryptu lub z pełnym adresem URL dla skryptu.</span><span class="sxs-lookup"><span data-stu-id="515b5-114">The DHCP server can respond either with the location (host name) of the script or with the full URL for the script.</span></span>  
  
3. <span data-ttu-id="515b5-115">Jeśli usługa DHCP nie zidentyfikuje hosta WPAD, do usługi DNS jest wysyłane zapytanie dla hosta z usługą WPAD jako jego nazwy lub aliasu.</span><span class="sxs-lookup"><span data-stu-id="515b5-115">If DHCP does not identify the WPAD host, DNS is queried for a host with WPAD as its name or alias.</span></span>  
  
4. <span data-ttu-id="515b5-116">Jeśli host nie zostanie zidentyfikowany i lokalizacja skryptu konfiguracji serwera proxy jest określona przez ustawienia sieci LAN programu Internet Explorer lub plik konfiguracji, Ta lokalizacja jest używana.</span><span class="sxs-lookup"><span data-stu-id="515b5-116">If the host is not identified and the location of a proxy configuration script is specified by the Internet Explorer LAN settings or a configuration file, this location is used.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="515b5-117">Aplikacje działające jako usługa NT lub jako część ASP.NET używają ustawień serwera proxy programu Internet Explorer (jeśli są dostępne) dla użytkownika wywołującego.</span><span class="sxs-lookup"><span data-stu-id="515b5-117">Applications running as an NT Service or as part of ASP.NET use the Internet Explorer proxy server settings (if available) of the invoking user.</span></span> <span data-ttu-id="515b5-118">Te ustawienia mogą być niedostępne dla wszystkich aplikacji usługi.</span><span class="sxs-lookup"><span data-stu-id="515b5-118">These settings may not be available for all service applications.</span></span>  
  
 <span data-ttu-id="515b5-119">Serwery proxy są konfigurowane na podstawie Connectoid.</span><span class="sxs-lookup"><span data-stu-id="515b5-119">Proxies are configured on a per-connectoid basis.</span></span> <span data-ttu-id="515b5-120">Connectoid to element w oknie dialogowym połączenia sieciowego, który może być fizycznym urządzeniem sieciowym (modemem lub kartą sieci Ethernet) lub interfejsem wirtualnym (na przykład połączeniem sieci VPN działającym przez urządzenie sieciowe).</span><span class="sxs-lookup"><span data-stu-id="515b5-120">A connectoid is an item in the network connection dialog, and can be a physical network device (a modem or Ethernet card) or a virtual interface (such as a VPN connection running over a network device).</span></span> <span data-ttu-id="515b5-121">Gdy Connectoid zmiany (na przykład połączenie bezprzewodowe zmienia punkt dostępu lub sieć VPN jest włączona), algorytm wykrywania serwera proxy jest uruchamiany ponownie.</span><span class="sxs-lookup"><span data-stu-id="515b5-121">When a connectoid changes (for example, a wireless connection changes an access point, or a VPN is enabled), the proxy detection algorithm is run again.</span></span>  
  
 <span data-ttu-id="515b5-122">Domyślnie ustawienia serwera proxy programu Internet Explorer są używane do wykrywania serwera proxy.</span><span class="sxs-lookup"><span data-stu-id="515b5-122">By default, the Internet Explorer proxy settings are used to detect the proxy.</span></span> <span data-ttu-id="515b5-123">Jeśli aplikacja działa w ramach konta nieinterakcyjnego (bez wygodnego sposobu konfigurowania ustawień serwera proxy programu IE) lub jeśli chcesz użyć ustawień serwera proxy innych niż ustawienia programu IE, możesz skonfigurować serwer proxy, tworząc plik konfiguracji z [ \<defaultProxy> elementem (Ustawienia sieci)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) i [ \<proxy> element (Ustawienia sieci)](../configure-apps/file-schema/network/proxy-element-network-settings.md) zdefiniowane.</span><span class="sxs-lookup"><span data-stu-id="515b5-123">If your application is running under a non-interactive account (without a convenient way to configure IE proxy settings), or if you want to use proxy settings different than the IE settings, you can configure your proxy by creating a configuration file with the [\<defaultProxy> Element (Network Settings)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) and [\<proxy> Element (Network Settings)](../configure-apps/file-schema/network/proxy-element-network-settings.md) elements defined.</span></span>  
  
 <span data-ttu-id="515b5-124">W przypadku żądań, które tworzysz, można wyłączyć automatyczne wykrywanie serwera proxy na poziomie żądania przy użyciu wartości null <xref:System.Net.WebRequest.Proxy%2A> z żądaniem, jak pokazano w poniższym przykładzie kodu.</span><span class="sxs-lookup"><span data-stu-id="515b5-124">For requests that you create, you can disable automatic proxy detection at the request level by using a null <xref:System.Net.WebRequest.Proxy%2A> with your request, as shown in the following code example.</span></span>  
  
```csharp  
public static void DisableForMyRequest (Uri resource)  
{  
    WebRequest request = WebRequest.Create (resource);  
    request.Proxy = null;  
    WebResponse response = request.GetResponse ();  
}  
```  
  
```vb  
Public Shared Sub DisableForMyRequest(ByVal resource As Uri)  
    Dim request As WebRequest = WebRequest.Create(resource)  
    request.Proxy = Nothing  
    Dim response As WebResponse = request.GetResponse()  
    End Sub
```  
  
 <span data-ttu-id="515b5-125">Żądania, które nie mają serwera proxy, używają domyślnego serwera proxy domeny aplikacji, który jest dostępny we <xref:System.Net.WebRequest.DefaultWebProxy%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="515b5-125">Requests that do not have a proxy use your application domain's default proxy, which is available in the <xref:System.Net.WebRequest.DefaultWebProxy%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="515b5-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="515b5-126">See also</span></span>

- <xref:System.Net.WebProxy>
- <xref:System.Net.WebRequest>
- [<span data-ttu-id="515b5-127">\<system.Net> — Element (Ustawienia sieci)</span><span class="sxs-lookup"><span data-stu-id="515b5-127">\<system.Net> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/system-net-element-network-settings.md)
