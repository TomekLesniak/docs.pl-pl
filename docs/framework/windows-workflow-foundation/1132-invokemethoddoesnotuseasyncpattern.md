---
title: 1132 — InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 9249bdd0fe996ee7c1b04783ac8fef2c48063cc0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294160"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a>1132 — InvokeMethodDoesNotUseAsyncPattern

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1132|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Podczas wykonywania kroku wywołaniem metody CacheMetadata działanie InvokeMethod wskazuje, że nie używa wzorca asynchronicznego podczas wywoływania metody.  
  
## <a name="message"></a>Wiadomość  

 InvokeMethod "%1" — Metoda nie korzysta ze wzorca asynchronicznego.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|XS: ciąg|Nazwa wyświetlana działania InvokeMethod.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
