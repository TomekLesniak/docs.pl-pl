---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: c63e1b3de464b306f46e2f0935b1208d7262925a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274195"
---
# <a name="clientcredentials"></a>ClientCredentials

ClientCredentials  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa ClientCredentials nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa ClientCredentials ma następujące właściwości:  
  
### <a name="clientcertificate"></a>Kolekcja  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Certyfikat X. 509, którego klient używa do uwierzytelniania w usłudze.  
  
### <a name="httpdigest"></a>HttpDigest  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Bieżące poświadczenie HTTP digest.  
  
### <a name="issuedtoken"></a>IssuedToken  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Adres punktu końcowego i powiązanie używane do kontaktowania się z usługą tokenu zabezpieczeń lokalnych.  
  
### <a name="peer"></a>Element równorzędny  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Poświadczenia używane przez węzeł równorzędny do samodzielnego uwierzytelnienia w innych węzłach w sieci.  
  
### <a name="servicecertificate"></a>ServiceCertificate  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Certyfikat X. 509 usługi.  
  
### <a name="supportinteractive"></a>SupportInteractive  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość logiczna określająca, czy poświadczenie obsługuje interaktywne negocjowanie.  
  
### <a name="username"></a>Nazwa użytkownika  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Nazwa użytkownika i hasło, których klient używa do samodzielnego uwierzytelnienia w usłudze.  
  
### <a name="windows"></a>Windows  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Poświadczenia systemu Windows, których klient używa do samodzielnego uwierzytelnienia w usłudze.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Description.ClientCredentials>
