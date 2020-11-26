---
title: Określanie zachowania klienta w czasie wykonywania
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- behaviors [WCF], system-provided client
ms.assetid: d16d3405-be70-4edb-8f62-b5f614ddeca5
ms.openlocfilehash: 17031f2100c6760cd14aae57cd4efab7428eb362
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235899"
---
# <a name="specifying-client-run-time-behavior"></a>Określanie zachowania klienta w czasie wykonywania

Klienci programu Windows Communication Foundation (WCF), np. usługi Windows Communication Foundation (WCF), można skonfigurować w celu zmodyfikowania zachowania w czasie wykonywania w celu dostosowania go do aplikacji klienckiej. Trzy atrybuty są dostępne do określenia zachowania klienta w czasie wykonywania. Obiekty wywołania zwrotnego klienta dupleksu mogą używać <xref:System.ServiceModel.CallbackBehaviorAttribute> atrybutów i, <xref:System.ServiceModel.Description.CallbackDebugBehavior> Aby zmodyfikować zachowanie w czasie wykonywania. Innym atrybutem, <xref:System.ServiceModel.Description.ClientViaBehavior> ,,, można użyć do oddzielenia logicznego miejsca docelowego od bezpośredniej lokalizacji docelowej. Ponadto typy wywołania zwrotnego klienta dupleksowego mogą używać niektórych zachowań po stronie usług. Aby uzyskać więcej informacji, zobacz [Określanie zachowania Run-Time usługi](specifying-service-run-time-behavior.md).  
  
## <a name="using-the-callbackbehaviorattribute"></a>Korzystanie z CallbackBehaviorAttribute  

 Można skonfigurować lub zwiększyć zachowanie wykonywania implementacji kontraktu wywołania zwrotnego w aplikacji klienckiej przy użyciu <xref:System.ServiceModel.CallbackBehaviorAttribute> klasy. Ten atrybut wykonuje podobną funkcję dla klasy wywołania zwrotnego jako <xref:System.ServiceModel.ServiceBehaviorAttribute> Klasa, z wyjątkiem zachowania dotyczącego wystąpień i ustawień transakcji.  
  
 <xref:System.ServiceModel.CallbackBehaviorAttribute>Klasa musi być stosowana do klasy implementującej kontrakt wywołania zwrotnego. W przypadku zastosowania do implementacji kontraktu niedupleksowego <xref:System.InvalidOperationException> w czasie wykonywania jest zgłaszany wyjątek. Poniższy przykład kodu pokazuje <xref:System.ServiceModel.CallbackBehaviorAttribute> klasę na obiekcie wywołania zwrotnego, który używa <xref:System.Threading.SynchronizationContext> obiektu do określenia wątku, do którego należy zorganizować, <xref:System.ServiceModel.CallbackBehaviorAttribute.ValidateMustUnderstand%2A> Właściwość, aby wymusić weryfikację wiadomości, oraz <xref:System.ServiceModel.CallbackBehaviorAttribute.IncludeExceptionDetailInFaults%2A> Właściwość, która zwraca wyjątki jako <xref:System.ServiceModel.FaultException> obiekty do usługi w celach debugowania.  
  
 [!code-csharp[CallbackBehaviorAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/callbackbehaviorattribute/cs/client.cs#3)]
 [!code-vb[CallbackBehaviorAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/callbackbehaviorattribute/vb/client.vb#3)]  
  
## <a name="using-callbackdebugbehavior-to-enable-the-flow-of-managed-exception-information"></a>Włączanie przepływu informacji o zarządzanych wyjątkach przy użyciu CallbackDebugBehavior  

 Można włączyć przepływ informacji o zarządzanym wyjątku w obiekcie wywołania zwrotnego klienta z powrotem do usługi w celu debugowania przez ustawienie <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> właściwości na `true` programowo lub w pliku konfiguracyjnym aplikacji.  
  
 Zwrócenie informacji o wyjątku zarządzanym do usług może stanowić zagrożenie bezpieczeństwa, ponieważ szczegóły wyjątku ujawniają informacje o wewnętrznej implementacji klienta, które mogą być używane przez nieautoryzowane usługi. Ponadto, chociaż <xref:System.ServiceModel.Description.CallbackDebugBehavior> właściwości można także ustawiać programowo, można łatwo zapomnieć o wyłączeniu <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> podczas wdrażania.  
  
 Ze względu na problemy związane z bezpieczeństwem zdecydowanie zaleca się, aby:  
  
- Użyj pliku konfiguracji aplikacji, aby ustawić wartość <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> właściwości na `true` .  
  
- Można to zrobić tylko w scenariuszach z kontrolowanym debugowaniem.  
  
 Poniższy przykład kodu przedstawia plik konfiguracji klienta, który instruuje program WCF, aby zwracał informacje o zarządzanym wyjątku z obiektu wywołania zwrotnego klienta w komunikatach protokołu SOAP.  
  
 [!code-xml[SCA.CallbackContract#4](../../../samples/snippets/csharp/VS_Snippets_CFX/sca.callbackcontract/cs/client.exe.config#4)]  

## <a name="using-the-clientviabehavior-behavior"></a>Korzystanie z zachowania ClientViaBehavior  

 Możesz użyć zachowania, <xref:System.ServiceModel.Description.ClientViaBehavior> Aby określić Uniform Resource Identifier, dla którego należy utworzyć kanał transportu. Użyj tego zachowania, gdy bezpośrednie miejsce docelowe sieci nie jest zamierzonym procesorem komunikatu. Umożliwia to konwersacje z wieloma przeskokami, gdy aplikacja wywołująca nie musi znać ostatecznego miejsca docelowego lub gdy `Via` nagłówek docelowy nie jest adresem.  
  
## <a name="see-also"></a>Zobacz też

- [Określanie zachowania środowiska uruchomieniowego usługi](specifying-service-run-time-behavior.md)
