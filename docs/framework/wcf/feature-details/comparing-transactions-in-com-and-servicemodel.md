---
title: Porównywanie transakcji w modelach COM+ i ServiceModel
ms.date: 03/30/2017
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
ms.openlocfilehash: 30ecbd374e909141dbc944740f90c1b41ac44ed2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264911"
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>Porównywanie transakcji w modelach COM+ i ServiceModel

W tym temacie omówiono sposób symulowania zachowania transakcyjnej usługi COM+ przy użyciu atrybutów Windows Communication Foundation (WCF), które <xref:System.ServiceModel> zapewnia przestrzeń nazw.  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>Emulacja modelu COM+ przy użyciu atrybutów ServiceModel  

 W poniższej tabeli porównano <xref:System.EnterpriseServices.TransactionOption> Wyliczenie używane do tworzenia `EnterpriseServices` transakcji i sposobu ich skorelowania z atrybutami WCF, które <xref:System.ServiceModel> zapewnia przestrzeń nazw.  
  
|Atrybut modelu COM+|Atrybuty WCF|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|<xref:System.ServiceModel.TransactionFlowAttribute> jest ustawiony na <xref:System.ServiceModel.TransactionFlowOption.NotAllowed> .<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> to `true`.<br /><br /> `TransactionFlow`Atrybut w elemencie Binding ma wartość `false` .|  
|Wymagany|<xref:System.ServiceModel.TransactionFlowAttribute> jest ustawiony na <xref:System.ServiceModel.TransactionFlowOption.Allowed> .<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> to `true`.<br /><br /> `TransactionFlow`Atrybut w elemencie Binding ma wartość `true` .|  
|Obsługiwane|Nie ma bezpośredniego odpowiednika. Ogólnie rzecz biorąc, należy przyjąć zachowanie określone dla `Required` zamiast.|  
|NotSupported|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> to `false`.<br /><br /> `TransactionFlow`Atrybut w elemencie Binding ma wartość `false` .|  
|Disabled|Nie ma bezpośredniego odpowiednika. Ogólnie rzecz biorąc, należy przyjąć zachowanie określone dla `NotSupported` zamiast.|
