---
title: Rozszerzanie systemu metadanych
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: 7113120a3cde6b4e6a7eb1d329da625e25996952
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272986"
---
# <a name="extending-the-metadata-system"></a>Rozszerzanie systemu metadanych

System metadanych programu Windows Communication Foundation (WCF) to grupa klas i interfejsów, które reprezentują metadane wymagane do implementowania aplikacji opartych na usługach. Modyfikuj lub rozszerzaj klasy albo Implementuj i Konfiguruj interfejsy, aby wyeksportować i zaimportować niestandardowe metadane, takie jak rozszerzenia Web Services Description Language (WSDL) lub niestandardowe potwierdzenia WS-PolicyAttachments.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Eksportowanie niestandardowych metadanych na potrzeby rozszerzenia programu WCF](exporting-custom-metadata-for-a-wcf-extension.md)  
 Opisuje sposób wdrażania i używania <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interfejsu do osadzania niestandardowych potwierdzeń zasad w dokumentach WSDL.  
  
 [Importowanie niestandardowych metadanych dla rozszerzenia WCF](importing-custom-metadata-for-a-wcf-extension.md)  
 Opisuje sposób wdrażania i używania <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interfejsu w celu odczytu i reagowania na niestandardowe potwierdzenia zasad w dokumentach WSDL.  
  
 [Publikowanie i pobieranie metadanych za pośrednictwem powiązania niestandardowego](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 Opisuje sposób wymiany metadanych za pośrednictwem powiązań niestandardowych.
