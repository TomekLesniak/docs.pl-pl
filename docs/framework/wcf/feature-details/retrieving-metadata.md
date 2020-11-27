---
title: Pobieranie metadanych
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WCF], retrieving
ms.assetid: 18d8ba4c-af0f-4827-a50b-4202d767bacc
ms.openlocfilehash: 212ea49418d5e33d79a1b6cf881e2828388c657e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295512"
---
# <a name="retrieving-metadata"></a>Pobieranie metadanych

Pobieranie metadanych to proces żądania i pobierania metadanych z punktu końcowego metadanych, takiego jak punkt końcowy metadanych WS-MetadataExchange (MEX) lub punkt końcowy metadanych HTTP/GET.  
  
## <a name="retrieving-metadata-from-the-command-line-using-svcutilexe"></a>Pobieranie metadanych z wiersza polecenia przy użyciu Svcutil.exe  

 Metadane usługi można pobrać przy użyciu WS-MetadataExchange lub protokołu HTTP/GET przy użyciu narzędzia do obsługi [metadanych modelu ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) i przekazywać `/target:metadata` przełącznik i adres. Svcutil.exe pobiera metadane pod określonym adresem i zapisuje plik na dysku. Svcutil.exe używa <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> wystąpienia wewnętrznie i ładuje <xref:System.ServiceModel.Description.IMetadataExchange> konfigurację punktu końcowego, którego nazwa pasuje do schematu adresu przenoszonego do Svcutil.exe jako dane wejściowe.  
  
## <a name="retrieving-metadata-programmatically-using-the-metadataexchangeclient"></a>Programistyczne Pobieranie metadanych przy użyciu klasy MetadataExchangeClient  

 Windows Communication Foundation (WCF) może pobrać metadane usługi przy użyciu standardowych protokołów, takich jak WS-MetadataExchange i HTTP/GET. Oba te protokoły są obsługiwane przez <xref:System.ServiceModel.Description.MetadataExchangeClient> Typ. Pobieranie metadanych usługi przy użyciu <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> typu przez podanie adresu dla punktu końcowego metadanych i opcjonalnego powiązania. Powiązanie używane przez <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> wystąpienie może być jednym z domyślnych powiązań z <xref:System.ServiceModel.Description.MetadataExchangeBindings> klasy statycznej, powiązanie dostarczone przez użytkownika lub powiązanie załadowane z konfiguracji punktu końcowego dla `IMetadataExchange` kontraktu. <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>Może również rozpoznać odwołania do adresów URL protokołu HTTP w celu uzyskania metadanych przy użyciu <xref:System.Net.HttpWebRequest> typu.  
  
 Domyślnie <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> wystąpienie jest powiązane z pojedynczym <xref:System.ServiceModel.ChannelFactory> wystąpieniem. Można zmienić lub zastąpić <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> wystąpienie używane przez <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> zastąpienie <xref:System.ServiceModel.Description.MetadataExchangeClient.GetChannelFactory%2A> metody wirtualnej. Podobnie można zmienić lub zastąpić <xref:System.Net.HttpWebRequest> wystąpienie używane przez element, <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> Aby wykonać żądania HTTP/GET przez zastąpienie <xref:System.ServiceModel.Description.MetadataExchangeClient.GetWebRequest%2A?displayProperty=nameWithType> metody wirtualnej.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Instrukcje: używanie programu Svcutil.exe do pobierania dokumentów metadanych](how-to-use-svcutil-exe-to-download-metadata-documents.md)  
 Pokazuje, jak używać Svcutil.exe do pobierania dokumentów metadanych.  
  
 [Instrukcje: dynamiczne uzyskiwanie metadanych wiązania przy użyciu klasy MetadataResolver](how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md)  
 Pokazuje, jak używać programu <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType> do dynamicznego uzyskiwania powiązań metadanych w czasie wykonywania.  
  
 [Instrukcje: używanie elementu MetadataExchangeClient do pobierania metadanych](how-to-use-metadataexchangeclient-to-retrieve-metadata.md)  
 Pokazuje, jak używać <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> klasy do pobierania plików metadanych do <xref:System.ServiceModel.Description.MetadataSet?displayProperty=nameWithType> obiektu, który zawiera <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType> obiekty do zapisu w plikach lub do innych celów.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Description.MetadataExchangeClient>
