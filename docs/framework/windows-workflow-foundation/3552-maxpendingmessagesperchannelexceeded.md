---
title: 3552 — MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: bd3e7539922e6c430c4ffe5bd96ef1ac7dbd098f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261166"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a>3552 — MaxPendingMessagesPerChannelExceeded

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|3552|  
|Słowa kluczowe|Przydział, WFServices|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 Wskazuje, że osiągnięto limit ograniczania przepustowości "MaxPendingMessagesPerChannel".  
  
## <a name="message"></a>Wiadomość  

 Osiągnięto limit "%1" dławienia "MaxPendingMessagesPerChannel". Aby zwiększyć ten limit, Dostosuj Właściwość MaxPendingMessagesPerChannel w BufferedReceiveServiceBehavior.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Limit|XS: ciąg|Limit ograniczenia MaxPendingMessagesPerChannel.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
