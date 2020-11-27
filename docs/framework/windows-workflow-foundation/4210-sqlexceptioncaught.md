---
title: 4210 — SqlExceptionCaught
ms.date: 03/30/2017
ms.assetid: f0ce8af3-eb4c-48c8-b3d9-dd2f94b5574b
ms.openlocfilehash: 1dab44e3fb97d74a2146f5bf992225222bc93d50
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280380"
---
# <a name="4210---sqlexceptioncaught"></a>4210 — SqlExceptionCaught

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|4210|  
|Słowa kluczowe|WFInstanceStore|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że wyjątek SQL został przechwycony.  
  
## <a name="message"></a>Wiadomość  

 Przechwycono wyjątek SQL o numerze %1 (komunikat %2).  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|ErrorNumber|XS: ciąg|Numer błędu SQL.|  
|ExceptionMessage|XS: ciąg|Komunikat z wyjątku SQL.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
