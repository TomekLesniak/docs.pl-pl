---
title: 3550 — BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: 61605d666911cce277bcebbb0a2f803e9a5dcfeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261309"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a>3550 — BufferOutOfOrderMessageNoInstance

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|3550|  
|Słowa kluczowe|WFServices|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 Wskazuje, że zbuforowane odbieranie nie powiodło się. Operacja zostanie podjęta ponownie, gdy wystąpienie usługi będzie gotowe do przetworzenia tej konkretnej operacji.  
  
## <a name="message"></a>Wiadomość  

 Nie można teraz wykonać operacji "%1". Kolejna próba zostanie podjęta, gdy wystąpienie usługi będzie gotowe do przetworzenia tej konkretnej operacji.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|OperationName|XS: ciąg|Nazwa operacji.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
