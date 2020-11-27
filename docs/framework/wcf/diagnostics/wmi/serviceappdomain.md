---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 243c9112dd9caf5c92ef77aa0f45b4b1e71a4e9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273259"
---
# <a name="serviceappdomain"></a>ServiceAppDomain

Mapuje usługę do domeny aplikacji.  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa serviceappdomain nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa serviceappdomain ma następujące właściwości:  
  
### <a name="ref"></a>ref  

 Typ danych: usługa  
Kwalifikatory: klucz  
  
 Typ dostępu: tylko do odczytu  
  
 Usługa tej domeny aplikacji.  
  
### <a name="ref"></a>ref  

 Typ danych: AppDomainInfo  
Kwalifikatory: klucz  
  
 Typ dostępu: tylko do odczytu  
  
 Zawiera właściwości domeny aplikacji.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|
