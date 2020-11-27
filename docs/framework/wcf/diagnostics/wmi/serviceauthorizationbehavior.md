---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: d3625865484568746888ef0638d9a8501e610bef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273207"
---
# <a name="serviceauthorizationbehavior"></a>ServiceAuthorizationBehavior

ServiceAuthorizationBehavior  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa ServiceAuthorizationBehavior nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa ServiceAuthorizationBehavior ma następujące właściwości:  
  
### <a name="impersonatecallerforalloperations"></a>ImpersonateCallerForAllOperations  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość, która kontroluje, czy usługa próbuje dokonać personifikacji przy użyciu poświadczeń dostarczonych przez komunikat przychodzący.  
  
### <a name="principalpermissionmode"></a>PrincipalPermissionMode  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Podmiot zabezpieczeń używany do wykonywania operacji na serwerze.  
  
### <a name="roleprovider"></a>RoleProvider  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Nazwa dostawcy roli ASP.NET.  
  
### <a name="serviceauthorizationmanager"></a>ServiceAuthorizationManager  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Menedżer autoryzacji używany do autoryzacji niestandardowej.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
