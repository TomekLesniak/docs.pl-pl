---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 00485ff80a0064e700d99203de3aa581d3761f30
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255731"
---
# <a name="asymmetricsecuritybindingelement"></a>AsymmetricSecurityBindingElement

AsymmetricSecurityBindingElement  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa element AsymmetricSecurityBindingElement nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa element AsymmetricSecurityBindingElement ma następujące właściwości:  
  
### <a name="messageprotectionorder"></a>MessageProtectionOrder  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Kolejność szyfrowania i podpisywania wiadomości dla tego powiązania.  
  
### <a name="requiresignatureconfirmation"></a>RequireSignatureConfirmation  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Czy powiązanie wymaga potwierdzenia podpisu.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
