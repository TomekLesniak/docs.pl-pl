---
title: Współdziałanie z aplikacjami COM
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
ms.openlocfilehash: bc58e22b64284d66367302d55b5c9554c9ec0d72
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268238"
---
# <a name="integrating-with-com-applications"></a>Współdziałanie z aplikacjami COM

Usługi Windows Communication Foundation (WCF) można zintegrować bezpośrednio z istniejącym kodem przy użyciu monikera usługi WCF. Moniker usługi może być używany z szerokiego zakresu środowisk programistycznych opartych na modelu COM, takich jak pakiet Office VBA, Visual Basic 6,0 lub Visual C++ 6,0.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Przegląd integrowania z aplikacjami modelu COM](integrating-with-com-applications-overview.md)  
 Zawiera omówienie głównych części procesu integracji.  
  
 [Instrukcje: rejestrowanie i konfigurowanie krótkiej nazwy usługi](how-to-register-and-configure-a-service-moniker.md)  
 Aby użyć monikera usługi WCF w aplikacji COM, należy zarejestrować wymagane typy z atrybutami COM i skonfigurować aplikację COM oraz moniker z wymaganą konfiguracją powiązania.  
  
 [Instrukcje: używanie krótkiej nazwy programu Windows Communication Foundation bez rejestracji](use-the-wcf-service-moniker-without-registration.md)  
 Wyjaśnia, jak uzyskać definicję kontraktu w formie dokumentu języka definicji usług sieci Web (WSDL) lub z punktu końcowego WS-MetadataExchange.  
  
 [Instrukcje: używanie krótkiej nazwy usługi z kontraktami WSDL](how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 Opisuje sposób wywoływania przykładu WCF przy użyciu monikera WSDL programu WCF.  
  
 [Instrukcje: używanie krótkiej nazwy usługi z kontraktami wymiany metadanych](how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 Opisuje sposób wywoływania przykładu WCF przy użyciu monikera programu WCF określającego punkt końcowy MEX.  
  
 [Instrukcje: określanie poświadczeń zabezpieczeń kanału](how-to-specify-channel-security-credentials.md)  
 Moniker usługi WCF obsługuje `IChannelCredentials` interfejs, który umożliwia szereg alternatywnych metod określania poświadczeń kanału.  
  
## <a name="reference"></a>Dokumentacja  

 <xref:System.ServiceModel>  
  
## <a name="see-also"></a>Zobacz też

- [Integrowanie z aplikacjami COM+](integrating-with-com-plus-applications.md)
