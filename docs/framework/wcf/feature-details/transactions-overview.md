---
title: Omówienie transakcji WCF (Windows Communication Foundation)
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF]
- WCF, transactions
- Windows Communication Foundation, transactions
ms.assetid: c7757854-1207-4019-8b31-552578b7d570
ms.openlocfilehash: 1486290241fdb40d415278c4a01738aa711e2182
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261478"
---
# <a name="windows-communication-foundation-transactions-overview"></a>Omówienie transakcji WCF (Windows Communication Foundation)

Transakcje umożliwiają grupowanie zestawu akcji lub operacji w pojedynczą niepodzielną jednostkę wykonania. Transakcja jest kolekcją operacji o następujących właściwościach:  
  
- Niepodzielność. Pozwala to zagwarantować, że wszystkie aktualizacje ukończone w ramach określonej transakcji zostaną zatwierdzone i wykonane w sposób trwały lub wszystkie są przerywane i wycofywane do poprzedniego stanu.  
  
- Spójność. Gwarantuje to, że zmiany wprowadzone w ramach transakcji reprezentują transformację z jednego stanu spójnego na inny. Na przykład transakcja, która przenosi pieniądze z konta kontroli na konto oszczędnościowe, nie zmienia kwoty pieniędzy w ogólnym koncie bankowym.  
  
- Izolacja. Zapobiega to obserwowanie niezatwierdzonych zmian należących do innych współbieżnych transakcji. Izolacja zapewnia abstrakcję współbieżności, przy jednoczesnym zapewnieniu, że jedna transakcja nie może mieć nieoczekiwanego wpływu na wykonywanie innej transakcji.  
  
- Wytrzymałości. Oznacza to, że po zatwierdzeniu aktualizacje zasobów zarządzanych (takich jak rekord bazy danych) będą trwałe w wyniku awarii.  
  
 Windows Communication Foundation (WCF) oferuje bogaty zestaw funkcji, które umożliwiają tworzenie transakcji rozproszonych w aplikacji usługi sieci Web.  
  
 WCF implementuje obsługę protokołu WS-AtomicTransaction (WS-AT), który umożliwia aplikacjom WCF przepływ transakcji do aplikacji międzyoperacyjnych, takich jak współdziałające usługi sieci Web stworzone przy użyciu technologii innych firm. Funkcja WCF implementuje również obsługę protokołu transakcji OLE, który może być używany w scenariuszach, w których nie ma potrzeby włączania przepływu transakcji.  
  
 Możesz użyć pliku konfiguracji aplikacji, aby skonfigurować powiązania do włączania lub wyłączania przepływu transakcji, a także ustawić żądany protokół transakcyjny dla powiązania. Ponadto można ustawić limity czasu transakcji na poziomie usługi przy użyciu pliku konfiguracji. Aby uzyskać więcej informacji, zobacz [Włączanie przepływu transakcji](enabling-transaction-flow.md).  
  
 Atrybuty transakcji w <xref:System.ServiceModel> przestrzeni nazw umożliwiają wykonywanie następujących czynności:  
  
- Skonfiguruj limity czasu transakcji i filtrowanie na poziomie izolacji przy użyciu <xref:System.ServiceModel.ServiceBehaviorAttribute> atrybutu.  
  
- Włącz funkcje transakcji i skonfiguruj zachowanie realizacji transakcji przy użyciu <xref:System.ServiceModel.OperationBehaviorAttribute> atrybutu.  
  
- Użyj <xref:System.ServiceModel.ServiceContractAttribute> atrybutów i <xref:System.ServiceModel.OperationContractAttribute> dla metody Contract, aby wymagać, zezwalać lub odmawiać przepływu transakcji.  
  
 Aby uzyskać więcej informacji, zobacz [atrybuty transakcji ServiceModel](servicemodel-transaction-attributes.md).  
  
## <a name="see-also"></a>Zobacz też

- [Atrybuty transakcji elementu ServiceModel](servicemodel-transaction-attributes.md)
- [Włączanie przepływu transakcji](enabling-transaction-flow.md)
