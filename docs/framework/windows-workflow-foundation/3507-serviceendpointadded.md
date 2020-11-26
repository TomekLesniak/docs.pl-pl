---
title: 3507 — ServiceEndpointAdded
ms.date: 03/30/2017
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
ms.openlocfilehash: 903071e7b1f89dc3489b8d3ac05427d699a33a7e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240761"
---
# <a name="3507---serviceendpointadded"></a>3507 — ServiceEndpointAdded

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|3507|  
|Słowa kluczowe|WFServices|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 Wskazuje, że punkt końcowy usługi został dodany.  
  
## <a name="message"></a>Wiadomość  

 Dodano punkt końcowy usługi dla adresu "%1", powiązania "%2" i kontraktu "%3".  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Adres|XS: ciąg|Adres punktu końcowego.|  
|Wiązanie|XS: ciąg|Powiązanie punktu końcowego.|  
|Kontrakt|XS: ciąg|Kontrakt punktu końcowego.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
