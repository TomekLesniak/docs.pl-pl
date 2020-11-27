---
title: Używanie elementu WS-AtomicTransaction
ms.date: 03/30/2017
helpviewer_keywords:
- WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
ms.openlocfilehash: 22b84dc49ab723953ce36402ac14221f410dda11
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281602"
---
# <a name="using-ws-atomictransaction"></a>Używanie elementu WS-AtomicTransaction

WS-AtomicTransaction (WS-AT) jest protokołem transakcji międzyoperacyjnych. Umożliwia przepływ transakcji rozproszonych przy użyciu komunikatów usługi sieci Web i koordynuje współdziałanie między heterogenicznymi infrastrukturami transakcji. Usługa WS-AT używa dwufazowego protokołu zatwierdzania w celu uzyskania niepodzielnego wyniku między aplikacjami rozproszonymi, menedżerami transakcji i menedżerami zasobów.  
  
 Implementacja WS-AT Windows Communication Foundation (WCF) zawiera usługę protokołu wbudowaną w Menedżera transakcji Microsoft Distributed Transaction Coordinator (MSDTC). Za pomocą usługi WS-AT aplikacje WCF mogą przepływać transakcje do innych aplikacji, w tym współdziałających usług sieci Web utworzonych przy użyciu technologii innych firm.  
  
 Podczas przepływania transakcji między aplikacją kliencką a aplikacją serwerową używany protokół transakcji jest określany przez powiązanie, które serwer ujawnia w punkcie końcowym wybranego przez klienta. Niektóre powiązania dostarczone przez system WCF domyślnie określają `OleTransactions` Protokół jako format propagacji transakcji, podczas gdy inne domyślnie określają usługę WS-AT. Można również programowo modyfikować wybór protokołu transakcji wewnątrz danego powiązania.  
  
 Wybór wpływów na protokoły:  
  
- Format nagłówków wiadomości używanych do przepływu transakcji z klienta do serwera.  
  
- Protokół sieciowy używany do uruchamiania dwufazowego protokołu zatwierdzania między menedżerem transakcji klienta i transakcji serwera, aby można było rozpoznać wynik transakcji.  
  
 Jeśli serwer i klient są zapisywana przy użyciu programu WCF, nie trzeba używać usługi WS-AT. Zamiast tego można użyć domyślnych ustawień `NetTcpBinding` z `TransactionFlow` włączonym atrybutem, który będzie korzystał z `OleTransactions` protokołu. Aby uzyskać więcej informacji, zobacz [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md). W przeciwnym razie, jeśli przepływy są transakcje do usług sieci Web opartych na technologiach innych firm, należy użyć usługi WS-AT.  
  
## <a name="see-also"></a>Zobacz też

- [Konfigurowanie obsługi protokołu WS-Atomic Transaction](configuring-ws-atomic-transaction-support.md)
