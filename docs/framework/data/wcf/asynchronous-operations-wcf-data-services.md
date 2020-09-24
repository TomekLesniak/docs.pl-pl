---
title: Operacje asynchroniczne (Usługi danych programu WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
- WCF Data Services, client library
ms.assetid: 679644c7-e3fc-422c-b14a-b44b683900d0
ms.openlocfilehash: cf3a81914d78e8f08c06602600ce5dcef4f4d35b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191648"
---
# <a name="asynchronous-operations-wcf-data-services"></a>Operacje asynchroniczne (Usługi danych programu WCF)

Aplikacje sieci Web muszą obsługiwać wyższe opóźnienia między klientem a serwerem niż aplikacje, które działają w sieciach wewnętrznych. Aby zoptymalizować wydajność i środowisko użytkownika aplikacji, zalecamy użycie asynchronicznych metod <xref:System.Data.Services.Client.DataServiceContext> <xref:System.Data.Services.Client.DataServiceQuery%601> klas i podczas uzyskiwania dostępu do usługi danych programu WCF serwerów za pośrednictwem sieci Web.  
  
 Mimo że serwery Usługi danych programu WCF przetwarzają żądania HTTP asynchronicznie, niektóre metody bibliotek klienckich Usługi danych programu WCF są synchroniczne i oczekują na ukończenie całego wymiany odpowiedzi na żądanie przed kontynuowaniem wykonywania. Metody asynchroniczne bibliotek klienta Usługi danych programu WCF nie czekają na ukończenie tej wymiany i mogą umożliwić aplikacji obsługę interfejsu użytkownika w międzyczasie.  
  
 Operacje asynchroniczne można wykonywać przy użyciu pary metod w <xref:System.Data.Services.Client.DataServiceContext> i <xref:System.Data.Services.Client.DataServiceQuery%601> klas, które zaczynają *się odpowiednio od początku* i *końca* . Metody *BEGIN* rejestrują delegata, który wywołuje Usługa po zakończeniu operacji. Metody *End* powinny być wywoływane w delegatze, który jest zarejestrowany do obsługi wywołania zwrotnego z ukończonych operacji. Gdy wywoływana jest metoda *End* w celu ukończenia operacji asynchronicznej, należy to zrobić z tego samego <xref:System.Data.Services.Client.DataServiceQuery%601> lub <xref:System.Data.Services.Client.DataServiceContext> wystąpienia, które zostało użyte do rozpoczęcia operacji. Każda metoda *BEGIN* przyjmuje `state` parametr, który może przekazać obiekt stanu do wywołania zwrotnego. Ten obiekt stanu jest pobierany z <xref:System.IAsyncResult> , który jest dostarczany z wywołaniem zwrotnym i jest używany do wywołania odpowiedniej metody *End* w celu ukończenia operacji asynchronicznej. Na przykład, gdy podasz <xref:System.Data.Services.Client.DataServiceQuery%601> wystąpienie jako `state` parametr po wywołaniu <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> metody w wystąpieniu, to to samo <xref:System.Data.Services.Client.DataServiceQuery%601> wystąpienie jest zwracane przez <xref:System.IAsyncResult> . To wystąpienie <xref:System.Data.Services.Client.DataServiceQuery%601> jest następnie używane do wywołania <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> metody w celu ukończenia operacji zapytania. Aby uzyskać więcej informacji, zobacz [jak: wykonywanie zapytań asynchronicznych usługi danych](how-to-execute-asynchronous-data-service-queries-wcf-data-services.md).  
  
> [!NOTE]
> Tylko operacje asynchroniczne są obsługiwane przez biblioteki klienckie udostępniane w .NET Framework dla programu Silverlight. Aby uzyskać więcej informacji, zobacz [usługi danych programu WCF (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95)).  
  
 Biblioteki klienta .NET Framework obsługują następujące operacje asynchroniczne:  
  
|Operacja|Metody|  
|---------------|-------------|  
|Wykonywanie <xref:System.Data.Services.Client.DataServiceQuery%601> .|-   <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>|  
|Wykonywanie zapytania z <xref:System.Data.Services.Client.DataServiceContext> .|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>|  
|Wykonywanie zapytania wsadowego z <xref:System.Data.Services.Client.DataServiceContext> .|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecuteBatch%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecuteBatch%2A>|  
|Ładowanie jednostki powiązanej do <xref:System.Data.Services.Client.DataServiceContext> .|-   <xref:System.Data.Services.Client.DataServiceContext.BeginLoadProperty%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndLoadProperty%2A>|  
|Zapisywanie zmian w obiektach w <xref:System.Data.Services.Client.DataServiceContext>|-   <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>|  
  
## <a name="threading-considerations-for-asynchronous-operations"></a>Zagadnienia dotyczące wątkowania operacji asynchronicznych  

 W aplikacji wielowątkowej delegat, który jest zarejestrowany jako wywołanie zwrotne dla operacji asynchronicznej, nie jest koniecznie wywoływany w tym samym wątku, który został użyty do wywołania metody *BEGIN* , co powoduje utworzenie początkowego żądania. W aplikacji, w której wywołanie zwrotne musi być wywoływane w określonym wątku, należy jawnie zorganizować wykonywanie metody *End* , która obsługuje odpowiedź, do żądanego wątku. Na przykład w przypadku aplikacji opartych na Windows Presentation Foundation (WPF) i aplikacji opartych na technologii Silverlight odpowiedź musi być organizowana z powrotem do wątku interfejsu użytkownika przy użyciu <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> metody dla <xref:System.Windows.Threading.Dispatcher> obiektu. Aby uzyskać więcej informacji, zobacz [wykonywanie zapytań dotyczących usługi danych (usługi danych programu WCF/Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc903932(v=vs.95)).  
  
## <a name="see-also"></a>Zobacz też

- [Biblioteka klienta usług danych WCF](wcf-data-services-client-library.md)
