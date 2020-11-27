---
title: 3551 — BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 5e6a5f9d21435fee8309bd222443407e50ec2cee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263610"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a>3551 — BufferOutOfOrderMessageNoBookmark

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|3551|  
|Słowa kluczowe|WFServices|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 Wskazuje, że wznowienie zakładki zakończyło się niepowodzeniem. Buforowana operacja odbierania zostanie ponowiona, gdy wystąpienie usługi będzie gotowe do przetworzenia tej konkretnej operacji.  
  
## <a name="message"></a>Wiadomość  

 W tej chwili nie można wykonać operacji "%2" w wystąpieniu usługi "%1". Kolejna próba zostanie podjęta, gdy wystąpienie usługi będzie gotowe do przetworzenia tej konkretnej operacji.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|OperationName|XS: ciąg|Nazwa operacji.|  
|Właściwość ServiceInstanceId|XS: ciąg|Identyfikator wystąpienia usługi.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
