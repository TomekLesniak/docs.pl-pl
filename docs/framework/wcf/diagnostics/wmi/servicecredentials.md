---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d7e89acedc8fc1004b0198172e58813944df85f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262310"
---
# <a name="servicecredentials"></a>ServiceCredentials

ServiceCredentials  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa ServiceCredentials nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa ServiceCredentials ma następujące właściwości:  
  
### <a name="clientcertificate"></a>Kolekcja  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Ustawienia uwierzytelniania certyfikatu klienta i aprowizacji dla tej usługi.  
  
### <a name="issuedtokenauthentication"></a>IssuedTokenAuthentication  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Bieżące ustawienia uwierzytelniania wystawionego tokenu dla tej usługi.  
  
### <a name="peer"></a>Element równorzędny  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Bieżące ustawienia uwierzytelniania i inicjowania obsługi poświadczeń, które będą używane przez punkty końcowe transportu elementu równorzędnego.  
  
### <a name="secureconversationauthentication"></a>SecureConversationAuthentication  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Określa bieżące ustawienia bezpiecznej konwersacji.  
  
### <a name="servicecertificate"></a>ServiceCertificate  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Certyfikat skojarzony z tą usługą.  
  
### <a name="usernameauthentication"></a>UserNameAuthentication  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Ustawienia nazwy użytkownika/hasła dla tej usługi.  
  
### <a name="windowsauthentication"></a>WindowsAuthentication  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Ustawienia uwierzytelniania systemu Windows dla tej usługi.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Description.ServiceCredentials>
