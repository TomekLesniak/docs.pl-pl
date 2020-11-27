---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: 61eae75de04f75b6ad6e78d16569595732b3d28f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273311"
---
# <a name="securitybindingelement"></a>SecurityBindingElement

SecurityBindingElement  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa elementu SecurityBindingElement nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa elementu SecurityBindingElement ma następujące właściwości:  
  
### <a name="defaultalgorithmsuite"></a>DefaultAlgorithmSuite  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Określa algorytmy, które mają być używane z powiązaniem.  
  
### <a name="includetimestamp"></a>IncludeTimestamp  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość logiczna określająca, czy każdy komunikat zawiera sygnaturę czasową.  
  
### <a name="keyentropymode"></a>Entropia  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Źródło entropii używanej do tworzenia kluczy.  
  
### <a name="localservicesecuritysettings"></a>LocalServiceSecuritySettings  

 Typ danych: LocalServiceSecuritySettings  
  
 Typ dostępu: tylko do odczytu  
  
 Specyficzne dla powiązania właściwości zabezpieczeń dla usługi lokalnej.  
  
### <a name="messagesecurityversion"></a>MessageSecurityVersion  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Wersja używana do zabezpieczenia komunikatów.  
  
### <a name="securityheaderlayout"></a>SecurityHeaderLayout  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Kolejność elementów w nagłówku zabezpieczeń dla tego powiązania.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
