---
title: 'Instrukcje: konfigurowanie usługi WCF na potrzeby współdziałania z klientami usługi ASP.NET w Internecie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
ms.openlocfilehash: 696e6a08f3f040fcc6f27d101cd6b7c8cc89a0d6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556645"
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Instrukcje: konfigurowanie usługi WCF na potrzeby współdziałania z klientami usługi ASP.NET w Internecie

Aby skonfigurować punkt końcowy usługi Windows Communication Foundation (WCF) do współdziałania z klientami usługi sieci Web ASP.NET, użyj <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> typu jako powiązania dla punktu końcowego usługi.  
  
 Opcjonalnie można włączyć obsługę uwierzytelniania przy użyciu protokołu HTTPS i klienta na poziomie transportu. Klienci usługi sieci Web ASP.NET nie obsługują kodowania komunikatów MTOM, więc <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> Właściwość powinna pozostać jako wartość domyślna, która jest <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> . Klienci usługi sieci Web ASP.NET nie obsługują protokołu WS-Security, dlatego <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> należy ustawić wartość <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> .  
  
 Aby udostępnić metadane usługi WCF ASP.NET narzędzia do generowania serwera proxy usługi sieci Web (czyli [narzędzie Web Services Description Language (Wsdl.exe)](/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100)), [Narzędzie do odnajdywania usług sieci Web (Disco.exe)](/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))i funkcję **Dodaj odwołanie sieci Web** w programie Visual Studio), należy uwidocznić punkt końcowy metadanych HTTP/GET.  
  
## <a name="add-an-endpoint-in-code"></a>Dodawanie punktu końcowego w kodzie  
  
1. Utwórz nowe <xref:System.ServiceModel.BasicHttpBinding> wystąpienie  
  
2. Opcjonalnie Włącz zabezpieczenia transportu dla tego powiązania punktu końcowego usługi przez ustawienie trybu zabezpieczeń dla powiązania <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> . Aby uzyskać szczegółowe informacje, zobacz [Transport Security](transport-security.md).  
  
3. Dodaj nowy punkt końcowy aplikacji do hosta usługi przy użyciu utworzonego wystąpienia powiązania. Aby uzyskać szczegółowe informacje na temat dodawania punktu końcowego usługi w kodzie, zobacz [instrukcje: Tworzenie punktu końcowego usługi w kodzie](how-to-create-a-service-endpoint-in-code.md).  
  
4. Włącz punkt końcowy metadanych HTTP/GET dla usługi. Aby uzyskać szczegółowe informacje [, zobacz jak: Publikowanie metadanych dla usługi przy użyciu kodu](how-to-publish-metadata-for-a-service-using-code.md).  
  
## <a name="add-an-endpoint-in-a-configuration-file"></a>Dodawanie punktu końcowego w pliku konfiguracji  
  
1. Utwórz nową <xref:System.ServiceModel.BasicHttpBinding> konfigurację powiązania. Aby uzyskać szczegółowe informacje, zobacz [instrukcje: Określanie powiązania usługi w konfiguracji](../how-to-specify-a-service-binding-in-configuration.md).  
  
2. Opcjonalnie Włącz zabezpieczenia transportu dla tej konfiguracji powiązania punktu końcowego usługi, ustawiając tryb zabezpieczeń dla powiązania <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> . Aby uzyskać szczegółowe informacje, zobacz [Transport Security](transport-security.md).  
  
3. Skonfiguruj nowy punkt końcowy aplikacji dla usługi przy użyciu konfiguracji powiązania, która została właśnie utworzona. Aby uzyskać szczegółowe informacje na temat dodawania punktu końcowego usługi w pliku konfiguracji, zobacz [temat jak: Tworzenie punktu końcowego usługi w konfiguracji](how-to-create-a-service-endpoint-in-configuration.md).  
  
4. Włącz punkt końcowy metadanych HTTP/GET dla usługi. Aby uzyskać szczegółowe informacje, zobacz [instrukcje: Publikowanie metadanych dla usługi za pomocą pliku konfiguracji](how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykładowy kod demonstruje sposób dodawania punktu końcowego WCF, który jest zgodny z klientami usługi sieci Web ASP.NET w kodzie i Alternatywnie w plikach konfiguracji.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]
  
## <a name="see-also"></a>Zobacz także

- [Instrukcje: tworzenie punktu końcowego w kodzie](how-to-create-a-service-endpoint-in-code.md)
- [Instrukcje: publikowanie metadanych dla usługi przy użyciu kodu](how-to-publish-metadata-for-a-service-using-code.md)
- [Instrukcje: Określanie powiązania usługi w konfiguracji](../how-to-specify-a-service-binding-in-configuration.md)
- [Instrukcje: tworzenie punktu końcowego usługi w konfiguracji](how-to-create-a-service-endpoint-in-configuration.md)
- [Instrukcje: publikowanie metadanych dla usługi za pomocą pliku konfiguracji](how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Zabezpieczenia transportu](transport-security.md)
- [Używanie metadanych](using-metadata.md)
