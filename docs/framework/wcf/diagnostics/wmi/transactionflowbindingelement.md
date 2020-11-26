---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: 577502d1cd3d81784cb9b1eb3b249376b8ffa6b8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234898"
---
# <a name="transactionflowbindingelement"></a>TransactionFlowBindingElement

TransactionFlowBindingElement  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa TransactionFlowBindingElement nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa TransactionFlowBindingElement ma następujące właściwości:  
  
### <a name="issuedtokens"></a>IssuedTokens  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Określa wymagania dotyczące wystawionego nagłówka tokenów zabezpieczeń (IssuedTokens z usługi WS-Trust).  
  
### <a name="transactionprotocol"></a>Element TransactionProtocol  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Protokół transakcji używany przez usługę do przepływu transakcji.  
  
### <a name="transactions"></a>Transakcje  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wskazuje, czy transakcja przychodząca jest obsługiwana.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
