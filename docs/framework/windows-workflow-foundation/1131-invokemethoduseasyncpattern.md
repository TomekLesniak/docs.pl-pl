---
title: 1131 — InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 2192b63b8a08657b69f6e3984f898bd6baddbc5f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294186"
---
# <a name="1131---invokemethoduseasyncpattern"></a>1131 — InvokeMethodUseAsyncPattern

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1131|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Podczas wykonywania kroku wywołaniem metody CacheMetadata działanie InvokeMethod wskazuje, że jest używany wzorzec asynchroniczny podczas wywoływania metody.  
  
## <a name="message"></a>Wiadomość  

 InvokeMethod "%1" — Metoda używa wzorca asynchronicznego dla "%2" i "%3".  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|XS: ciąg|Nazwa wyświetlana działania InvokeMethod.|  
|BeginMethod|XS: ciąg|Nazwa metody BEGIN.|  
|EndMethod|XS: ciąg|Nazwa metody end.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
