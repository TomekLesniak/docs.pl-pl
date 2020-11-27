---
title: 1125 — InvokeMethodIsNotStatic
ms.date: 03/30/2017
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
ms.openlocfilehash: 0405b4e1207db5c056fbd478b98c408258daf0c3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294212"
---
# <a name="1125---invokemethodisnotstatic"></a>1125 — InvokeMethodIsNotStatic

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1125|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Podczas kroku wywołaniem metody CacheMetadata działanie InvokeMethod wskazuje, że metoda wywoływana nie jest statyczna.  
  
## <a name="message"></a>Wiadomość  

 InvokeMethod "%1" — Metoda nie jest statyczna.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|XS: ciąg|Nazwa wyświetlana działania InvokeMethod.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
