---
title: 39456 — TrackingRecordDropped
ms.date: 03/30/2017
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
ms.openlocfilehash: d958b506e057bc0d59f954debdc9da6015bf5f1f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273103"
---
# <a name="39456---trackingrecorddropped"></a>39456 — TrackingRecordDropped

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|39456|  
|Słowa kluczowe|WFTracking|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że rekord śledzenia został porzucony, ponieważ jego rozmiar przekracza wartość maksymalną dozwoloną przez dostawcę sesji ETW.  
  
## <a name="message"></a>Wiadomość  

 Rozmiar rekordu śledzenia %1 przekracza maksymalną dozwoloną przez sesję ETW dla dostawcy %2  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Wyjątek|XS: ciąg|Szczegóły wyjątku dla wyjątku|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
