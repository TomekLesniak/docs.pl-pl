---
title: NetworkInformation
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
ms.openlocfilehash: 550555be7cc95cafebabfd3ac230ced024a9202c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261621"
---
# <a name="networkinformation"></a><span data-ttu-id="3a69c-102">NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="3a69c-102">NetworkInformation</span></span>

<span data-ttu-id="3a69c-103"><xref:System.Net.NetworkInformation>Przestrzeń nazw umożliwia gromadzenie informacji o zdarzeniach, zmianach, statystykach i właściwościach sieci.</span><span class="sxs-lookup"><span data-stu-id="3a69c-103">The <xref:System.Net.NetworkInformation> namespace enables you to gather information about network events, changes, statistics, and properties.</span></span> <span data-ttu-id="3a69c-104">Można również określić, czy host zdalny jest osiągalny za pomocą <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> klasy.</span><span class="sxs-lookup"><span data-stu-id="3a69c-104">You can also determine whether a remote host is reachable by using the <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> class.</span></span>  
  
## <a name="network-availability-and-events"></a><span data-ttu-id="3a69c-105">Dostępność i zdarzenia sieci</span><span class="sxs-lookup"><span data-stu-id="3a69c-105">Network Availability and Events</span></span>  

 <span data-ttu-id="3a69c-106"><xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType>Klasa umożliwia określenie, czy adres sieciowy lub dostępność uległy zmianie.</span><span class="sxs-lookup"><span data-stu-id="3a69c-106">The <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> class enables you to determine whether the network address or availability has changed.</span></span> <span data-ttu-id="3a69c-107">Aby użyć tej klasy, należy utworzyć procedurę obsługi zdarzeń w celu przetworzenia zmiany i skojarzyć ją z <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> lub <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="3a69c-107">To use this class, create an event handler to process the change, and associate it with a <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> or a <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>.</span></span> <span data-ttu-id="3a69c-108">Aby uzyskać więcej informacji, zobacz [How to: Detecting Network Availability and address Changes](how-to-detect-network-availability-and-address-changes.md).</span><span class="sxs-lookup"><span data-stu-id="3a69c-108">For more information, see [How to: Detect Network Availability and Address Changes](how-to-detect-network-availability-and-address-changes.md).</span></span>  
  
## <a name="network-statistics-and-properties"></a><span data-ttu-id="3a69c-109">Statystyka i właściwości sieci</span><span class="sxs-lookup"><span data-stu-id="3a69c-109">Network Statistics and Properties</span></span>  

 <span data-ttu-id="3a69c-110">Można zbierać dane statystyczne i właściwości sieci w interfejsie lub protokole.</span><span class="sxs-lookup"><span data-stu-id="3a69c-110">You can gather network statistics and properties on an interface or protocol basis.</span></span> <span data-ttu-id="3a69c-111"><xref:System.Net.NetworkInformation.NetworkInterface>Klasy, <xref:System.Net.NetworkInformation.NetworkInterfaceType> i <xref:System.Net.NetworkInformation.PhysicalAddress> zawierają informacje o konkretnym interfejsie sieciowym, natomiast <xref:System.Net.NetworkInformation.IPInterfaceProperties> klasy,, <xref:System.Net.NetworkInformation.IPGlobalProperties> <xref:System.Net.NetworkInformation.IPGlobalStatistics> , <xref:System.Net.NetworkInformation.TcpStatistics> i <xref:System.Net.NetworkInformation.UdpStatistics> zawierają informacje o pakietach warstwy 3 i 4.</span><span class="sxs-lookup"><span data-stu-id="3a69c-111">The <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType>, and <xref:System.Net.NetworkInformation.PhysicalAddress> classes give information about a particular network interface, while the <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics>, and <xref:System.Net.NetworkInformation.UdpStatistics> classes give information about layer 3 and layer 4 packets.</span></span> <span data-ttu-id="3a69c-112">Aby uzyskać więcej informacji, zobacz [jak: pobrać informacje o interfejsie i protokole](how-to-get-interface-and-protocol-information.md).</span><span class="sxs-lookup"><span data-stu-id="3a69c-112">For more information, see [How to: Get Interface and Protocol Information](how-to-get-interface-and-protocol-information.md).</span></span>  
  
## <a name="determine-if-a-remote-host-is-reachable"></a><span data-ttu-id="3a69c-113">Określanie, czy host zdalny jest osiągalny</span><span class="sxs-lookup"><span data-stu-id="3a69c-113">Determine if a Remote Host is Reachable</span></span>  

 <span data-ttu-id="3a69c-114">Klasy można użyć <xref:System.Net.NetworkInformation.Ping> do określenia, czy host zdalny jest w sieci i osiągalny.</span><span class="sxs-lookup"><span data-stu-id="3a69c-114">You can use the <xref:System.Net.NetworkInformation.Ping> class to determine whether a Remote Host is up, on the network, and reachable.</span></span> <span data-ttu-id="3a69c-115">Aby uzyskać więcej informacji, zobacz [How to: ping a host](how-to-ping-a-host.md).</span><span class="sxs-lookup"><span data-stu-id="3a69c-115">For more information, see [How to: Ping a Host](how-to-ping-a-host.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a69c-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3a69c-116">See also</span></span>

- [<span data-ttu-id="3a69c-117">Przykłady programowania sieciowego</span><span class="sxs-lookup"><span data-stu-id="3a69c-117">Network Programming Samples</span></span>](network-programming-samples.md)

<!-- to-do: review sample links
- [Network Information Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Network%20Information)
- [NetStat Tool Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=NetStat%20Tool)
- [Ping Client Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Ping%20Client)
-->
