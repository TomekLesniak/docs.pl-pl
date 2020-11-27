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
# <a name="networkinformation"></a>NetworkInformation

<xref:System.Net.NetworkInformation>Przestrzeń nazw umożliwia gromadzenie informacji o zdarzeniach, zmianach, statystykach i właściwościach sieci. Można również określić, czy host zdalny jest osiągalny za pomocą <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> klasy.  
  
## <a name="network-availability-and-events"></a>Dostępność i zdarzenia sieci  

 <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType>Klasa umożliwia określenie, czy adres sieciowy lub dostępność uległy zmianie. Aby użyć tej klasy, należy utworzyć procedurę obsługi zdarzeń w celu przetworzenia zmiany i skojarzyć ją z <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> lub <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler> . Aby uzyskać więcej informacji, zobacz [How to: Detecting Network Availability and address Changes](how-to-detect-network-availability-and-address-changes.md).  
  
## <a name="network-statistics-and-properties"></a>Statystyka i właściwości sieci  

 Można zbierać dane statystyczne i właściwości sieci w interfejsie lub protokole. <xref:System.Net.NetworkInformation.NetworkInterface>Klasy, <xref:System.Net.NetworkInformation.NetworkInterfaceType> i <xref:System.Net.NetworkInformation.PhysicalAddress> zawierają informacje o konkretnym interfejsie sieciowym, natomiast <xref:System.Net.NetworkInformation.IPInterfaceProperties> klasy,, <xref:System.Net.NetworkInformation.IPGlobalProperties> <xref:System.Net.NetworkInformation.IPGlobalStatistics> , <xref:System.Net.NetworkInformation.TcpStatistics> i <xref:System.Net.NetworkInformation.UdpStatistics> zawierają informacje o pakietach warstwy 3 i 4. Aby uzyskać więcej informacji, zobacz [jak: pobrać informacje o interfejsie i protokole](how-to-get-interface-and-protocol-information.md).  
  
## <a name="determine-if-a-remote-host-is-reachable"></a>Określanie, czy host zdalny jest osiągalny  

 Klasy można użyć <xref:System.Net.NetworkInformation.Ping> do określenia, czy host zdalny jest w sieci i osiągalny. Aby uzyskać więcej informacji, zobacz [How to: ping a host](how-to-ping-a-host.md).  
  
## <a name="see-also"></a>Zobacz też

- [Przykłady programowania sieciowego](network-programming-samples.md)

<!-- to-do: review sample links
- [Network Information Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Network%20Information)
- [NetStat Tool Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=NetStat%20Tool)
- [Ping Client Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Ping%20Client)
-->
