---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 9da8f77ee8ea5dc8b22ac5c0cb5113e906c5dc78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262271"
---
# <a name="servicesecurityauditbehavior"></a>ServiceSecurityAuditBehavior

ServiceSecurityAuditBehavior  
  
## <a name="syntax"></a>Składnia  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa ServiceSecurityAuditBehavior nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa ServiceSecurityAuditBehavior ma następujące właściwości:  
  
### <a name="auditloglocation"></a>AuditLogLocation  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Lokalizacja dziennika inspekcji.  
  
### <a name="messageauthenticationauditlevel"></a>MessageAuthenticationAuditLevel  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Typ poziomu uwierzytelniania wiadomości, który jest używany do rejestrowania zdarzeń inspekcji.  
  
### <a name="serviceauthorizationauditlevel"></a>ServiceAuthorizationAuditLevel  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Typy zdarzeń autoryzacji, które są rejestrowane w dzienniku inspekcji.  
  
### <a name="suppressauditfailure"></a>SuppressAuditFailure  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość logiczna określająca zachowanie w przypadku pomijania błędów zapisu do dziennika inspekcji.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
