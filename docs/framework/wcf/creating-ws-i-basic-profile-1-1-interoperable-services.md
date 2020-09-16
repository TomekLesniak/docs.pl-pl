---
title: Tworzenie usług międzyoperacyjnych 1.1 profilu podstawowego WS-I
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: 5fc29432bdd55daff2d60d641a4cea4925278032
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543020"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a>Tworzenie usług międzyoperacyjnych 1.1 profilu podstawowego WS-I
Aby skonfigurować punkt końcowy usługi WCF do współdziałania z klientami usługi sieci Web ASP.NET:  
  
- Użyj <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> typu jako typu powiązania dla punktu końcowego usługi.  
  
- Nie używaj funkcji wywołania zwrotnego i kontraktu sesji ani zachowań transakcji w punkcie końcowym usługi  
  
Opcjonalnie można włączyć obsługę uwierzytelniania przy użyciu protokołu HTTPS i klienta na poziomie transportu.  
  
Następujące funkcje <xref:System.ServiceModel.BasicHttpBinding> klasy wymagają funkcjonalności poza WS-I Basic Profile 1,1:  
  
- Kodowanie komunikatów mechanizmu optymalizacji transmisji wiadomości (MTOM) kontrolowane przez <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> Właściwość. Pozostaw tę właściwość jako wartość domyślną, która <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> nie używa mechanizmu MTOM.  
  
- Zabezpieczenia komunikatów kontrolowane przez <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> wartość zapewniają obsługę protokołu WS-Security zgodną z profilem zabezpieczeń WS-I Basic 1,0. Pozostaw tę właściwość domyślną wartością, która <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> nie jest używana w usłudze WS-Security.  
  
Aby uzyskać dostęp do metadanych usługi WCF ASP.NET, użyj narzędzia do generowania klienta usługi sieci Web: narzędzia do [Web Services Description Language (Wsdl.exe)](/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100)), [Narzędzia odnajdywania usług sieci Web (Disco.exe)](/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))i funkcji **Dodaj odwołanie sieci Web** w programie Visual Studio. Włącz publikację metadanych. Aby uzyskać więcej informacji, zobacz [Publikowanie punktów końcowych metadanych](publishing-metadata-endpoints.md).  
  
## <a name="example"></a>Przykład  
  
### <a name="description"></a>Opis  
 Poniższy przykładowy kod pokazuje, jak dodać punkt końcowy WCF, który jest zgodny z klientami usługi sieci Web ASP.NET w kodzie i, Alternatywnie, w pliku konfiguracji.  
  
### <a name="code"></a>Kod  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a>Zobacz także

- [Współdziałanie z usługami ASP.NET w sieci Web](./feature-details/interop-with-aspnet-web-services.md)
