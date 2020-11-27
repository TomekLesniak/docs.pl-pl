---
title: Powiązania elementu WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 94f0ba602cd1f58f5491a44a64e24be8ea52895b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293991"
---
# <a name="ws-metadataexchange-bindings"></a>Powiązania elementu WS-MetadataExchange

W tym temacie opisano, jak domyślne powiązania wymiany metadanych są konstruowane dla różnych transportów.  
  
## <a name="the-default-bindings"></a>Domyślne powiązania  
  
|Domyślna nazwa powiązania|Sposób konstruowania powiązania|  
|--------------------------|------------------------------------|  
|mexHttpBinding|<xref:System.ServiceModel.WSHttpBinding>Z wyłączonym zabezpieczeniami na poziomie transportu.|  
|mexHttpsBinding|A <xref:System.ServiceModel.WSHttpBinding> który obsługuje zabezpieczenia na poziomie transportu.|  
|mexNamedPipeBinding|A przy  <xref:System.ServiceModel.Channels.CustomBinding> <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> użyciu wartości domyślnych.|  
|mexTcpBinding|A <xref:System.ServiceModel.Channels.CustomBinding> z <xref:System.ServiceModel.Channels.TcpTransportBindingElement> wartościami domyślnymi.|
