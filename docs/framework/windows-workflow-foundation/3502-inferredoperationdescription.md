---
title: 3502 — InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 05278067e3f86612ee4aafbe7d5eb66dc934cb85
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242113"
---
# <a name="3502---inferredoperationdescription"></a>3502 — InferredOperationDescription

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|3502|  
|Słowa kluczowe|WFServices|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 Wskazuje, że obiekt OperationDescription został wywnioskowany z obiektu WorkflowService.  
  
## <a name="message"></a>Wiadomość  

 Obiekt OperationDescription o nazwie "%1" w kontrakcie "%2" został wywnioskowany z obiektu WorkflowService. IsOneWay = %3.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|OperationName|XS: ciąg|Nazwa operacji.|  
|Nr kontraktu|XS: ciąg|Nazwa kontraktu.|  
|IsOneWay|XS: ciąg|Prawda lub FAŁSZ wskazujący, czy kontrakt jest jednokierunkowe.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
