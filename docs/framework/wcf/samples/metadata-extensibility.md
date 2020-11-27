---
title: Rozszerzalność metadanych
ms.date: 03/30/2017
ms.assetid: f92fcc76-0806-4c84-9d63-7aae0d3899de
ms.openlocfilehash: fb37e33026a5f99bfa033f04eea0bb85fbbe65c7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294329"
---
# <a name="metadata-extensibility"></a>Rozszerzalność metadanych

Ta sekcja zawiera przykłady demonstrujące niestandardowe metadane.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Niestandardowy bezpieczny punkt końcowy metadanych](custom-secure-metadata-endpoint.md)  
 Demonstruje sposób implementacji usługi z bezpiecznym punktem końcowym metadanych, który używa jednego z powiązań wymiany niebędących metadanymi i jak skonfigurować [Narzędzie do obsługi metadanych ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) lub klientów, aby pobrać metadane z takiego punktu końcowego metadanych.  
  
 [Niestandardowa publikacja WSDL](custom-wsdl-publication.md)  
 Pokazuje, jak zaimplementować <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> w atrybucie niestandardowym <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> , aby eksportować właściwości atrybutów jako adnotacje WSDL, między innymi.
