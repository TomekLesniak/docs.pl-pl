---
title: Wybór i sprawdzanie poprawności certyfikatu
description: Dowiedz się więcej o kilku sposobach System.Net klas, które umożliwiają wybieranie i weryfikowanie certyfikatów dla połączeń SSL/TLS.
ms.date: 03/30/2017
ms.assetid: c933aca2-4cd0-4ff1-9df9-267143f25a6f
ms.openlocfilehash: a85b6947c20f7dbced1fb6ad6e79f3134ce1f57b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287517"
---
# <a name="certificate-selection-and-validation"></a>Wybór i sprawdzanie poprawności certyfikatu

<xref:System.Net>Klasy obsługują kilka sposobów wybierania i weryfikowania <xref:System.Security.Cryptography.X509Certificates> połączeń Secure Socket Layer (SSL). Klient może wybrać jeden lub więcej certyfikatów do samodzielnego uwierzytelnienia na serwerze. Serwer może wymagać, aby certyfikat klienta miał jeden lub więcej atrybutów określonych do uwierzytelnienia.  
  
## <a name="definition"></a>Definicja  

 Certyfikat to strumień bajtów ASCII, który zawiera klucz publiczny, atrybuty (takie jak numer wersji, numer seryjny i Data wygaśnięcia) oraz podpis cyfrowy z urzędu certyfikacji. Certyfikaty służą do nawiązywania zaszyfrowanego połączenia lub do uwierzytelniania klienta na serwerze.  
  
## <a name="client-certificate-selection-and-validation"></a>Wybór i walidacja certyfikatu klienta  

 Klient może wybrać co najmniej jeden certyfikat dla określonego połączenia SSL. Certyfikaty klienta można kojarzyć z połączeniem SSL z serwerem sieci Web lub serwerem poczty SMTP. Klient dodaje certyfikaty do kolekcji <xref:System.Security.Cryptography.X509Certificates.X509Certificate> lub <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> obiektów klas. W przypadku używania poczty e-mail jako przykładu kolekcja certyfikatów jest wystąpieniem elementu, który jest <xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection> skojarzony z <xref:System.Net.Mail.SmtpClient.ClientCertificates%2A> właściwością <xref:System.Net.Mail.SmtpClient> klasy. <xref:System.Net.HttpWebRequest>Klasa ma podobną <xref:System.Net.HttpWebRequest.ClientCertificates%2A> Właściwość.  
  
 Podstawowa różnica między <xref:System.Security.Cryptography.X509Certificates.X509Certificate> i <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> klasy polega na tym, że klucz prywatny musi znajdować się w magazynie certyfikatów dla <xref:System.Security.Cryptography.X509Certificates.X509Certificate> klasy.  
  
 Nawet jeśli certyfikaty są dodawane do kolekcji i skojarzone z określonym połączeniem SSL, do serwera nie będą wysyłane żadne certyfikaty, chyba że serwer wyśle żądania. Jeśli w ramach połączenia ustawiono wiele certyfikatów klienta, najlepszym rozwiązaniem będzie użycie algorytmu, który uwzględnia dopasowanie między listą wystawców certyfikatów dostarczonych przez serwer i nazwę wystawcy certyfikatu klienta.  
  
 <xref:System.Net.Security.SslStream>Klasa zapewnia jeszcze większą kontrolę nad uzgadnianiem protokołu SSL. Klient może określić delegata, aby wybrać certyfikat klienta, który ma być używany.  
  
 Serwer zdalny może sprawdzić, czy certyfikat klienta jest prawidłowy, obecny i podpisany przez odpowiedni urząd certyfikacji. Delegat można dodać do, <xref:System.Net.ServicePointManager.ServerCertificateValidationCallback%2A> Aby wymusić weryfikację certyfikatu.  
  
## <a name="client-certificate-selection"></a>Wybór certyfikatu klienta  

 .NET Framework wybiera certyfikat klienta, który ma być obecny na serwerze w następujący sposób:  
  
1. Jeśli certyfikat klienta został wcześniej przedstawiony na serwerze, certyfikat jest buforowany podczas pierwszego prezentowania i jest ponownie używany do kolejnych żądań certyfikatów klienta.  
  
2. Jeśli istnieje delegat, należy zawsze używać wyniku z delegata jako certyfikatu klienta do wybrania. Spróbuj użyć certyfikatu w pamięci podręcznej, jeśli jest to możliwe, ale nie używaj buforowanych poświadczeń anonimowych, jeśli delegat zwrócił wartość null, a kolekcja certyfikatów nie jest pusta.  
  
3. Jeśli jest to pierwsze wyzwanie dla certyfikatu klienta, struktura wylicza certyfikaty w <xref:System.Security.Cryptography.X509Certificates.X509Certificate> lub <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> obiektów klasy skojarzonych z połączeniem, szukając zgodności między listą wystawców certyfikatów dostarczanymi przez serwer i nazwę wystawcy certyfikatu klienta. Pierwszy zgodny certyfikat jest wysyłany na serwer. Jeśli żaden certyfikat nie jest zgodny lub kolekcja certyfikatów nie jest pusta, do serwera zostanie wysłane anonimowe poświadczenie.  
  
## <a name="tools-for-certificate-configuration"></a>Narzędzia do konfiguracji certyfikatów  

 Dostępne są różne narzędzia do konfiguracji certyfikatu klienta i serwera.  
  
 Narzędzia *Winhttpcertcfg.exe* można użyć do skonfigurowania certyfikatów klienta. Narzędzie *Winhttpcertcfg.exe* jest dostępne jako jeden z narzędzi z zestawem Windows Server 2003 Resource Kit. To narzędzie jest również dostępne jako element do pobrania w ramach narzędzi zestawu Windows Server 2003 Resource Kit pod adresem [www.Microsoft.com](https://www.microsoft.com).  
  
Narzędzia *HttpCfg.exe* można użyć do skonfigurowania certyfikatów serwera dla <xref:System.Net.HttpListener> klasy. Narzędzie *HttpCfg.exe* jest dostępne jako jeden z narzędzi pomocy technicznej dla systemów windows Server 2003 i Windows XP z dodatkiem Service Pack 2. *HttpCfg.exe* i inne narzędzia obsługi nie są instalowane domyślnie w systemie windows Server 2003 lub Windows XP. W systemie Windows Server 2003. narzędzia obsługi są instalowane niezależnie od następującego folderu i pliku na dysku CD-ROM z systemem Windows Server 2003:  
  
 \Support\Tools\Suptools.msi  
  
 Do użycia z systemem Windows XP z dodatkiem Service Pack 2 narzędzia obsługi systemu Windows XP są dostępne jako pobieranie z [www.Microsoft.com](https://www.microsoft.com).  
  
 Kod źródłowy do wersji narzędzia *HttpCfg.exe* jest również dostępny jako przykład z zestawem SDK systemu Windows Server. Kod źródłowy do przykładu *HttpCfg.exe* jest instalowany domyślnie z próbkami sieci w ramach Windows SDK w następującym folderze:  
  
 *C:\Program Files\Microsoft SDKs\Windows\v1.0\Samples\NetDS\http\serviceconfig*  
  
 Oprócz tych narzędzi <xref:System.Security.Cryptography.X509Certificates.X509Certificate> <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> klasy i oferują metody ładowania certyfikatu z systemu plików.  
  
## <a name="see-also"></a>Zobacz też

- [Zabezpieczenia w programowaniu sieciowym](security-in-network-programming.md)
- [Programowanie dla sieci w .NET Framework](index.md)
