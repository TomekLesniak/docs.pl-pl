---
title: 'Komunikacja podstawowa: Kanały transportu TCP'
ms.date: 03/30/2017
ms.assetid: d5cd057f-faec-4e21-ae0e-18bbc22bcfb1
ms.openlocfilehash: c9b2b31aaffccaae442f4444f69538245a813570
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96277338"
---
# <a name="core-communications-tcp-transport-channels"></a>Komunikacja podstawowa: Kanały transportu TCP

W tym temacie wymieniono wszystkie wyjątki wygenerowane przez kanały transportu TCP.  
  
## <a name="exception-list"></a>Lista wyjątków  
  
|Kod zasobu|Ciąg zasobu|  
|-------------------|---------------------|  
|SocketCloseReadTimeout|Zdalny punkt końcowy określonego gniazda nie odpowiedział na żądanie zamknięcia w określonym wyznaczonym limicie czasu. Istnieje możliwość, że zdalny punkt końcowy nie wywołuje metody Close po odebraniu sygnału EOF (null) z operacji Receive. Czas przydzielony na tę operację mógł być częścią dłuższego limitu czasu.|
