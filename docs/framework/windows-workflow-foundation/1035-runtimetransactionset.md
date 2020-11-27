---
title: 1035 — RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: b8bf8431c4e2b82c6aac95820eb45de2a404e976
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294277"
---
# <a name="1035---runtimetransactionset"></a>1035 — RuntimeTransactionSet

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1035|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że działanie ma ustawioną transakcję środowiska uruchomieniowego.  
  
## <a name="message"></a>Wiadomość  

 Transakcja środowiska uruchomieniowego została ustawiona przez działanie %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.  Wykonanie odizolowane dla działania "%4", nazwa wyświetlana: "%5", identyfikator wystąpienia: "%6".  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Działanie|XS: ciąg|Nazwa typu działania.|  
|Nazwa wyświetlana|XS: ciąg|Nazwa wyświetlana działania.|  
|InstanceId|XS: ciąg|Identyfikator wystąpienia działania.|  
|Wyizolowane|XS: ciąg|Nazwa typu działania, z którym jest izolowana transakcja.|  
|IsolatedActivityDisplayName|XS: ciąg|Nazwa wyświetlana działania, z którym jest izolowana transakcja.|  
|IsolatedActivityInstanceId|XS: ciąg|Identyfikator wystąpienia działania, z którym jest izolowana transakcja.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
