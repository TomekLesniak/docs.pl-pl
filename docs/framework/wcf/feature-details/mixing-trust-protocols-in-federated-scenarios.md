---
title: Mieszanie protokołów zaufania w scenariuszach obejmujących federację
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
ms.openlocfilehash: 5ce178c0b2c83469a26993ce6db2d6c87815543b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248178"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a>Mieszanie protokołów zaufania w scenariuszach obejmujących federację

Mogą istnieć scenariusze, w których klienci federacyjne komunikują się z usługą i usługą tokenu zabezpieczającego (STS), która nie ma tej samej wersji zaufania. WSDL usługi może zawierać `RequestSecurityTokenTemplate` potwierdzenie z WS-Trust elementami, które różnią się od wersji programu STS. W takich przypadkach klient Windows Communication Foundation (WCF) konwertuje elementy WS-Trust otrzymane z programu `RequestSecurityTokenTemplate` w celu dopasowania do wersji zaufania usługi STS. Usługa WCF obsługuje niezgodne wersje zaufania tylko dla powiązań standardowych. Wszystkie parametry algorytmu standardowego rozpoznawane przez funkcję WCF są częścią standardowego powiązania. W tym temacie opisano zachowanie WCF z różnymi ustawieniami zaufania między usługą i usługą STS.  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a>RP lut 2005 i STS lutego 2005  

 WSDL dla jednostki uzależnionej (RP) zawiera następujące elementy w `RequestSecurityTokenTemplate` sekcji:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 Plik konfiguracji klienta zawiera listę parametrów.  
  
 Funkcja WCF nie może rozróżnić parametrów klienta i usługi; dodaje wszystkie parametry i wysyła je w `RequestSecurityTokenTemplate` (RST).  
  
## <a name="rp-trust-13-and-sts-trust-13"></a>RP Trust 1,3 i usługa STS — zaufanie 1,3  

 WSDL dla RP zawiera następujące elementy w `RequestSecurityTokenTemplate` sekcji:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 Plik konfiguracji klienta zawiera `secondaryParameters` element, który otacza parametry określone przez RP.  
  
 Funkcja WCF usuwa `EncryptionAlgorithm` `CanonicalizationAlgorithm` elementy i `KeyWrapAlgorithm` z elementu najwyższego poziomu w obszarze RST, jeśli są obecne wewnątrz `SecondaryParameters` elementu. Funkcja WCF dołącza `SecondaryParameters` element do wychodzącego RST o niemodyfikowaniu.  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a>RP Trust 2005 i usługa STS — zaufanie 1,3  

 WSDL dla RP zawiera następujące elementy w `RequestSecurityTokenTemplate` sekcji:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 Plik konfiguracji klienta zawiera listę parametrów.  
  
 W pliku konfiguracji klienta WCF nie można rozróżnić między parametrami usługi i klienta. W związku z tym WCF konwertuje wszystkie parametry do przestrzeni nazw zaufania 1,3.  
  
 Usługa WCF obsługuje `KeyType` `KeySize` elementy, i `TokenType` w następujący sposób:  
  
- Pobierz WSDL, utwórz powiązanie i przypisz `KeyType` , `KeySize` i `TokenType` z parametrów RP. Następnie zostanie wygenerowany plik konfiguracji klienta.  
  
- Klient może teraz zmienić dowolny parametr w pliku konfiguracji.  
  
- W czasie wykonywania WCF kopiuje wszystkie parametry określone w `AdditionalTokenParameters` sekcji pliku konfiguracji klienta z wyjątkiem `KeyType` , `KeySize` i `TokenType` , ponieważ te parametry są uwzględniane podczas generowania pliku konfiguracji.  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a>RP Trust 1,3 i STS — luty 2005  

 WSDL dla RP zawiera następujące elementy w `RequestSecurityTokenTemplate` sekcji:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 Plik konfiguracji klienta zawiera `secondaryParamters` element, który otacza parametry określone przez RP.  
  
 Program WCF kopiuje wszystkie parametry określone w `SecondaryParameters` sekcji do najwyższego pierwszego poziomu RST elementu, ale nie konwertuje je do przestrzeni nazw 2005 WS-Trust.
