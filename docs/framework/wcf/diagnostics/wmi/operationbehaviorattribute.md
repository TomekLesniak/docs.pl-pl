---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 76cc619aed4ba2b944a8d11dc454a40368a4068c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269083"
---
# <a name="operationbehaviorattribute"></a>OperationBehaviorAttribute

OperationBehaviorAttribute  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa OperationBehaviorAttribute będący nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa OperationBehaviorAttribute będący ma następujące właściwości:  
  
### <a name="autodisposeparameters"></a>AutoDisposeParameters  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Stan funkcji autodispose dla parametrów.  
  
### <a name="impersonation"></a>Personifikacja  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Wskazuje poziom personifikacji wywołującego obsługiwany przez operację.  
  
### <a name="releaseinstancemode"></a>ReleaseInstanceMode  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Wskazuje, kiedy w trakcie wywołania operacji w celu odtworzenia obiektu.  
  
### <a name="transactionautocomplete"></a>Wartość  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wskazuje, czy bieżąca transakcja ma być automatycznie przekazywana, jeśli nie wystąpią żadne Nieobsłużone wyjątki.  
  
### <a name="transactionscoperequired"></a>Ustawione  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wskazuje, czy operacja wymaga transakcji.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.OperationBehaviorAttribute>
