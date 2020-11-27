---
title: 1126 — InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 7caaebe42f49a62fec61ba17a4d3fe3a538e2ab4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262843"
---
# <a name="1126---invokedmethodthrewexception"></a>1126 — InvokedMethodThrewException

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1126|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że wyjątek został zgłoszony przez metodę wywoływaną przez działanie InvokeMethod.  
  
## <a name="message"></a>Wiadomość  

 Zgłoszono wyjątek w metodzie wywoływanej przez działanie "%1". %2  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|XS: ciąg|Nazwa wyświetlana działania InvokeMethod.|  
|Wyjątek|XS: ciąg|Szczegóły wyjątku dla wyjątku|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
