---
title: Powiązania niestandardowe
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, endpoints
- Windows Communication Foundation, configuration
ms.assetid: 58532b6d-4eea-4a4f-854f-a1c8c842564d
ms.openlocfilehash: 062aba26227fedeea3e5f462ebf5d55cf0cba56c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540000"
---
# <a name="custom-bindings"></a>Powiązania niestandardowe

Klasy można użyć, <xref:System.ServiceModel.Channels.CustomBinding> gdy jedno z powiązań dostarczonych przez system nie spełnia wymagań usługi. Wszystkie powiązania są zbudowane z uporządkowanego zestawu elementów powiązania. Niestandardowe powiązania mogą być kompilowane z zestawu elementów powiązania dostarczonych przez system lub mogą zawierać niestandardowe elementy powiązań zdefiniowane przez użytkownika. Możesz użyć niestandardowych elementów powiązania, na przykład, aby umożliwić korzystanie z nowych transportów lub koderów w punkcie końcowym usługi. Aby zapoznać się z przykładami pracy, zobacz [niestandardowe powiązania przykładów](/previous-versions/dotnet/netframework-3.5/ms751479(v=vs.90)). Aby uzyskać więcej informacji, zobacz [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).

## <a name="construction-of-a-custom-binding"></a>Konstruowanie niestandardowego powiązania

Niestandardowe powiązanie jest konstruowane przy użyciu <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> konstruktora z kolekcji elementów powiązania, które są "ułożone" w określonej kolejności:

- U góry jest <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> klasą opcjonalną, która umożliwia przepływ transakcji.

- Dalej jest <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> klasą opcjonalną, która dostarcza do sesji i mechanizmy porządkowania, zgodnie z definicją w specyfikacji WS-ReliableMessaging. Sesja może przekroczyć pośredników SOAP i transportowych.

- Następnie jest opcjonalną <xref:System.ServiceModel.Channels.SecurityBindingElement> klasą, która zapewnia funkcje zabezpieczeń, takie jak autoryzacja, uwierzytelnianie, ochrona i poufność.

- Dalej jest <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> klasą opcjonalną, która zapewnia możliwość dwukierunkowej komunikacji dwustronnej z protokołem transportu, który nie obsługuje natywnej komunikacji dupleksowej, na przykład http.

- Next to opcjonalna <xref:System.ServiceModel.Channels.OneWayBindingElement> Klasa, która zapewnia komunikację jednokierunkową.

- Następny to opcjonalny element powiązania zabezpieczeń strumienia, który może mieć jedną z następujących wartości:

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- Następnie jest wymagany element powiązania kodowania komunikatów. Możesz użyć własnego kodera komunikatów lub jednego z trzech powiązań kodowania komunikatów:

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

U dołu jest wymagany element transportu. Możesz użyć własnego transportu lub jednego z następujących elementów powiązania transportowego Windows Communication Foundation (WCF) zapewnia:

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>

Poniższa tabela zawiera podsumowanie opcji dla każdej warstwy.

|Warstwa|Opcje|Wymagane|
|-----------|-------------|--------------|
|Transakcje|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|Nie|
|Niezawodność|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|Nie|
|Zabezpieczenia|<xref:System.ServiceModel.Channels.SecurityBindingElement>|Nie|
|Kodowanie|Tekst, binarny, mechanizm optymalizacji transmisji wiadomości (MTOM), niestandardowy|Yes|
|Transport|TCP, HTTP, HTTPS, nazwane potoki (znane również jako IPC), peer-to-peer (P2P), kolejkowanie komunikatów (nazywane także MSMQ), niestandardowe|Yes|

Ponadto można definiować własne elementy powiązania i wstawiać je między wszystkimi wcześniej zdefiniowanymi warstwami.

## <a name="see-also"></a>Zobacz także

- [Przegląd tworzenia punktów końcowych](../endpoint-creation-overview.md)
- [Konfigurowanie usług i klientów za pomocą wiązań](../using-bindings-to-configure-services-and-clients.md)
- [Wiązania dostarczane przez system](../system-provided-bindings.md)
- [Instrukcje: dostosowywanie wiązania udostępnionego przez system](how-to-customize-a-system-provided-binding.md)
- [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)
- [Wiązanie niestandardowe](../samples/custom-binding.md)
