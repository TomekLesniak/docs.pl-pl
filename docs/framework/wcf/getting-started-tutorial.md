---
title: 'Samouczek: wprowadzenie do aplikacji Windows Communication Foundation'
description: Te samouczki zawierają wprowadzenie do tworzenia aplikacji WCF.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: 620a83260f01e27a19b19227165695a621c88e5e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238239"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a>Samouczek: wprowadzenie do aplikacji Windows Communication Foundation

Poniższa seria samouczków wprowadza do środowiska programistycznego Windows Communication Foundation (WCF). Praca nad tymi samouczkami zapewnia wprowadzenie do wprowadzenia kroków wymaganych do utworzenia aplikacji WCF. Po zakończeniu będziesz mieć uruchomioną usługę WCF i klienta WCF, który wywoła usługę.

W samouczku założono, że używasz programu Visual Studio jako środowiska deweloperskiego. Jeśli używasz innego środowiska programistycznego, zignoruj instrukcje dotyczące programu Visual Studio.

Aby zapoznać się z przykładowymi aplikacjami WCF, które można pobrać i uruchomić, zobacz [Windows Communication Foundation Samples](samples/index.md). Aby zapoznać się z wprowadzeniem do przykładów, zobacz [wprowadzenie](samples/getting-started-sample.md).

Aby uzyskać bardziej szczegółowe informacje na temat tworzenia usług i klientów, zobacz [podstawowe programowanie WCF](basic-wcf-programming.md).

## <a name="wcf-tutorials"></a>Samouczki WCF

Pierwsze trzy samouczki opisują sposób definiowania kontraktu usługi WCF, sposobu jego wdrożenia oraz sposobu hostowania go. Utworzona usługa jest samodzielna w aplikacji konsolowej. Możesz również hostować usługi w usłudze Microsoft Internet Information Services (IIS). Aby uzyskać więcej informacji, zobacz [jak: Hostowanie usługi WCF w programie IIS](feature-details/how-to-host-a-wcf-service-in-iis.md). Chociaż używasz kodu do skonfigurowania usługi w samouczku, możesz również [skonfigurować usługi w pliku konfiguracji](configuring-services-using-configuration-files.md).

- [Samouczek: Definiowanie kontraktu usługi](how-to-define-a-wcf-service-contract.md)

    Tworzysz kontrakt WCF z interfejsem zdefiniowanym przez użytkownika. Ten kontrakt definiuje funkcje, które uwidacznia usługa.

- [Samouczek: Implementowanie kontraktu usługi](how-to-implement-a-wcf-contract.md)

    Po zdefiniowaniu kontraktu należy go zaimplementować z klasą usługi.

- [Samouczek: Hostowanie i uruchamianie podstawowej usługi](how-to-host-and-run-a-basic-wcf-service.md)

    Skonfiguruj punkt końcowy usługi i hostuje usługę w aplikacji konsolowej. Aby usługa stała się aktywna, należy ją skonfigurować i hostować w środowisku wykonawczym. To środowisko uruchomieniowe tworzy usługę i kontroluje jej kontekst i okres istnienia.

W następnych dwóch samouczkach opisano sposób tworzenia, konfigurowania i używania aplikacji klienckiej w celu wywołania operacji udostępnianych przez usługę. Usługi publikują metadane, które definiują informacje wymagane przez aplikację kliencką do komunikacji z usługą. Program Visual Studio automatyzuje proces uzyskiwania dostępu do tych metadanych i używa go do konstruowania aplikacji klienckiej dla usługi. Jeśli zdecydujesz się nie używać programu Visual Studio, możesz zamiast tego użyć [Narzędzia metadanych ServiceModel (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) .

- [Samouczek: tworzenie klienta](how-to-create-a-wcf-client.md)

    Pobierz metadane tworzenia serwera proxy klienta WCF z usługi WCF. Metadane są pobierane za pomocą programu Visual Studio w celu dodania odwołania do usługi lub narzędzia do obsługi metadanych ServiceModel. Należy określić punkt końcowy, którego klient używa w celu uzyskania dostępu do usługi.

- [Samouczek: korzystanie z klienta](how-to-use-a-wcf-client.md)

    Użyj serwera proxy klienta WCF do wywołania operacji usługi.

## <a name="reference"></a>Dokumentacja

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a>Zobacz też

- [Omówienie pojęć](conceptual-overview.md)
- [Przewodnik po dokumentacji](guide-to-the-documentation.md)
- [Co to jest Windows Communication Foundation](whats-wcf.md)
- [Szczegóły funkcji WCF](feature-details/index.md)
- [Podstawowy cykl życia programowania](basic-programming-lifecycle.md)
- [Kompilowanie klientów](building-clients.md)
- [Podstawowe programowanie WCF](basic-wcf-programming.md)
- [Instrukcje: tworzenie kontraktu dupleksowego](feature-details/how-to-create-a-duplex-contract.md)
- [Instrukcje: uzyskiwanie dostępu do usług za pomocą kontraktu dupleksowego](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [Narzędzie do przesyłania metadanych modelu ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Instrukcje: używanie Svcutil.exe do pobierania dokumentów metadanych](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [Instrukcje: Publikowanie metadanych dla usługi za pomocą pliku konfiguracji](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Konfigurowanie usług i klientów za pomocą powiązań](using-bindings-to-configure-services-and-clients.md)
- [Wprowadzenie — przykład](samples/getting-started-sample.md)
- [Przykłady Windows Communication Foundation](samples/index.md)
- [Host samodzielny](samples/self-host.md)
