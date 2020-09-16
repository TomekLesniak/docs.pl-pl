---
title: Izolacja sieci dla aplikacji ze sklepu Windows Store
ms.date: 03/30/2017
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
ms.openlocfilehash: 0f9288b53b969838cac64c24d3c9861a0f841aca
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558462"
---
# <a name="network-isolation-for-windows-store-apps"></a><span data-ttu-id="f5368-102">Izolacja sieci dla aplikacji ze sklepu Windows Store</span><span class="sxs-lookup"><span data-stu-id="f5368-102">Network Isolation for Windows Store Apps</span></span>

<span data-ttu-id="f5368-103">Klasy w <xref:System.Net> , <xref:System.Net.Http> i i <xref:System.Net.Http.Headers> przestrzenie nazw mogą służyć do tworzenia aplikacji do sklepu Windows lub aplikacji klasycznych.</span><span class="sxs-lookup"><span data-stu-id="f5368-103">Classes in the <xref:System.Net>, <xref:System.Net.Http>, and <xref:System.Net.Http.Headers> namespaces can be used to develop Windows Store  apps  or desktop apps.</span></span> <span data-ttu-id="f5368-104">W przypadku użycia w aplikacji ze sklepu Windows na klasy w tych obszarach nazw ma wpływ izolacja sieci, która jest częścią modelu zabezpieczeń aplikacji używanego w systemie Windows 8.</span><span class="sxs-lookup"><span data-stu-id="f5368-104">When used in a Windows Store app, classes in these namespaces are affected by network isolation, part of the application security model used by Windows 8.</span></span> <span data-ttu-id="f5368-105">Odpowiednie możliwości sieci muszą być włączone w manifeście aplikacji dla aplikacji ze sklepu Windows dla systemu, aby umożliwić dostęp do sieci.</span><span class="sxs-lookup"><span data-stu-id="f5368-105">The appropriate network capabilities must be enabled in the app manifest for a Windows Store app for the system to allow network access.</span></span>  
  
## <a name="checklist-for-network-isolation"></a><span data-ttu-id="f5368-106">Lista kontrolna dotycząca izolacji sieci</span><span class="sxs-lookup"><span data-stu-id="f5368-106">Checklist for Network Isolation</span></span>  

<span data-ttu-id="f5368-107">Użyj tej listy kontrolnej, aby upewnić się, że izolacja sieciowa jest skonfigurowana dla aplikacji ze sklepu Windows.</span><span class="sxs-lookup"><span data-stu-id="f5368-107">Use this checklist to be sure that network isolation is configured for your Windows Store app.</span></span>  
  
1. <span data-ttu-id="f5368-108">Określ kierunek żądań dostępu do sieci wymaganych przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="f5368-108">Determine the direction of network access requests needed by the app.</span></span> <span data-ttu-id="f5368-109">Może to być wychodzące żądania inicjowane przez klienta lub przychodzące żądania, które może być połączeniem obu tych typów żądań sieciowych.</span><span class="sxs-lookup"><span data-stu-id="f5368-109">This can be either outbound client-initiated requests or inbound unsolicited requests or it could be a combination of both of these network request types.</span></span>  
  
2. <span data-ttu-id="f5368-110">Określ typ zasobów sieciowych, z którymi będzie komunikować się aplikacja.</span><span class="sxs-lookup"><span data-stu-id="f5368-110">Determine the type of network resources that the app will communicate with.</span></span> <span data-ttu-id="f5368-111">Aplikacja może wymagać komunikacji z zaufanymi zasobami w sieci domowej lub służbowej.</span><span class="sxs-lookup"><span data-stu-id="f5368-111">An app may need to communicate with trusted resources on a Home or Work network.</span></span> <span data-ttu-id="f5368-112">Aplikacja może wymagać komunikacji z zasobami w Internecie.</span><span class="sxs-lookup"><span data-stu-id="f5368-112">An app might need to communicate with resources on the Internet.</span></span> <span data-ttu-id="f5368-113">Aplikacja może potrzebować dostępu do obu typów zasobów sieciowych.</span><span class="sxs-lookup"><span data-stu-id="f5368-113">An app might need access to both types of network resources.</span></span>  
  
3. <span data-ttu-id="f5368-114">Skonfiguruj minimalną wymaganą izolację sieciową w manifeście aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f5368-114">Configure the minimum-required networking isolation capabilities in the app manifest.</span></span>  
  
4. <span data-ttu-id="f5368-115">Wdróż i uruchom aplikację w celu przetestowania jej przy użyciu narzędzi do izolacji sieciowej dostępnych do rozwiązywania problemów.</span><span class="sxs-lookup"><span data-stu-id="f5368-115">Deploy and run your app to test it using the network isolation tools provided for troubleshooting.</span></span>  
  
<span data-ttu-id="f5368-116">Aby uzyskać bardziej szczegółowe informacje na temat konfigurowania możliwości sieci i narzędzi do izolacji w celu rozwiązywania problemów z izolacją sieci, zobacz [jak skonfigurować możliwości izolacji sieci](/previous-versions/windows/apps/hh770532(v=win.10)) w dokumentacji dla deweloperów Sklepu Windows 8. x.</span><span class="sxs-lookup"><span data-stu-id="f5368-116">For more detailed information on how to configure network capabilities and isolation tools used for troubleshooting network isolation, see [How to configure network isolation capabilities](/previous-versions/windows/apps/hh770532(v=win.10)) in the Windows 8.x Store developer documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f5368-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f5368-117">See also</span></span>

- <span data-ttu-id="f5368-118">[Łączenie z usługą sieci Web](/previous-versions/windows/apps/hh761504(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="f5368-118">[Connecting to a web service](/previous-versions/windows/apps/hh761504(v=win.10))</span></span>
- <span data-ttu-id="f5368-119">[Wskazówki i Lista kontrolna izolacji sieci](/previous-versions/windows/apps/hh770532(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="f5368-119">[Guidelines and checklist for network isolation](/previous-versions/windows/apps/hh770532(v=win.10))</span></span>
- <span data-ttu-id="f5368-120">[Szybki Start: Łączenie przy użyciu HttpClient](/previous-versions/windows/apps/hh781239(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="f5368-120">[Quickstart: Connecting using HttpClient](/previous-versions/windows/apps/hh781239(v=win.10))</span></span>
- <span data-ttu-id="f5368-121">[Jak używać programów obsługi HttpClient](/previous-versions/windows/apps/hh781241(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="f5368-121">[How to use HttpClient handlers](/previous-versions/windows/apps/hh781241(v=win.10))</span></span>
- <span data-ttu-id="f5368-122">[Jak zabezpieczyć połączenia HttpClient](/previous-versions/windows/apps/hh781240(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="f5368-122">[How to secure HttpClient connections](/previous-versions/windows/apps/hh781240(v=win.10))</span></span>
- [<span data-ttu-id="f5368-123">Przykład HttpClient</span><span class="sxs-lookup"><span data-stu-id="f5368-123">HttpClient Sample</span></span>](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664)
