---
title: Niestandardowi dostawcy usług danych (Usługi danych programu WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
ms.openlocfilehash: 4c92bf2f4e75b78cd6236c023246cc6c999086fa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186695"
---
# <a name="custom-data-service-providers-wcf-data-services"></a>Niestandardowi dostawcy usług danych (Usługi danych programu WCF)

Usługi danych programu WCF obejmuje zestaw dostawców, który umożliwia zdefiniowanie modelu danych na podstawie późnych typów danych.  
  
|Dostawca|Opis|  
|--------------|-----------------|  
|Dostawca metadanych|Jest to podstawowy dostawca usługi danych niestandardowych, który umożliwia zdefiniowanie niestandardowego modelu danych w środowisku uruchomieniowym przez implementację <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> interfejsu.|  
|Dostawca zapytań|Ten dostawca umożliwia wykonywanie zapytań względem niestandardowego modelu danych, który jest definiowany przy użyciu <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> interfejsu. Dostawca zapytań jest tworzony przez implementację <xref:System.Data.Services.Providers.IDataServiceQueryProvider> interfejsu.|  
|Aktualizuj dostawcę|Ten dostawca umożliwia Dokonywanie aktualizacji typów, które są widoczne w niestandardowym dostawcy usług danych i Zarządzanie współbieżnością. Dostawca aktualizacji jest tworzony przez implementację <xref:System.Data.Services.Providers.IDataServiceUpdateProvider> interfejsu|  
|Dostawca stronicowania|Ten dostawca jest używany z niestandardowym dostawcą usług danych w celu włączenia obsługi stronicowania opartego na serwerze. Dostawca stronicowania dla niestandardowej usługi danych jest tworzony przez implementację <xref:System.Data.Services.Providers.IDataServicePagingProvider> interfejsu.|  
|Dostawca przesyłania strumieniowego|Ten dostawca pozwala udostępnić binarne typy danych typu binary jako strumień. Dostawca przesyłania strumieniowego jest tworzony przez implementację <xref:System.Data.Services.Providers.IDataServiceStreamProvider> interfejsu. Dostawca przesyłania strumieniowego może być również używany z dostawcami źródeł danych Entity Framework i odbicia. Aby uzyskać więcej informacji, zobacz [dostawca przesyłania strumieniowego](streaming-provider-wcf-data-services.md).|  
  
## <a name="see-also"></a>Zobacz też

- [Dostawcy usług danych](data-services-providers-wcf-data-services.md)
- [Dostawca programu Entity Framework](entity-framework-provider-wcf-data-services.md)
- [Dostawca odbicia](reflection-provider-wcf-data-services.md)
