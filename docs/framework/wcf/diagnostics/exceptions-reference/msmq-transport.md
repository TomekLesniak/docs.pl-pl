---
title: Transport MSMQ
ms.date: 03/30/2017
ms.assetid: 3f29a2fe-24df-4614-b64c-b0c084fb7003
ms.openlocfilehash: 407512cbb129dd2e5497de92c32b0641dd21080b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238031"
---
# <a name="msmq-transport"></a>Transport MSMQ

W tym temacie wymieniono wszystkie wyjątki wygenerowane przez transport usługi MSMQ.  
  
## <a name="exception-list"></a>Lista wyjątków  
  
|Kod zasobu|Ciąg zasobu|  
|-------------------|---------------------|  
|MsmqActiveDirectoryRequiresNativeTransfer|Sprawdzanie poprawności powiązania dla wiadomości nie powiodło się. Klient nie może wysyłać komunikatów. Wystąpił konflikt we właściwościach powiązania z powodu tego błędu. UseActiveDirectory jest ustawiona na true, a QueueTransferProtocol jest ustawiona na natywny. Aby rozwiązać konflikt, Popraw jedną z właściwości.|  
|MsmqAuthNoneRequiresProtectionNone|Weryfikacja powiązania usługi nie powiodła się. Nie można uruchomić punktu końcowego usługi lub klienta. Wystąpił konflikt we właściwościach powiązania z powodu tego błędu. MsmqAuthenticationMode jest ustawiona na None, a MsmqProtectionLevel nie jest ustawiona na none. Aby rozwiązać konflikt, Popraw jedną z właściwości.|  
|MsmqCustomRequiresPerAddDLQ|Sprawdzanie poprawności powiązania dla wiadomości nie powiodło się. Klient nie może wysłać komunikatu. DeadLetterQueue jest ustawiona na Custom, ale nie określono CustomDeadLetterQueue. Określ identyfikator URI kolejki utraconych wiadomości dla każdej aplikacji we właściwości CustomDeadLetterQueue.|  
|MsmqDeserializationError|Wystąpił błąd podczas deserializacji komunikatu XML. Nie można odebrać wiadomości i został on porzucony.|  
|MsmqDLQNotWriteable|Weryfikacja powiązania dla klienta nie powiodła się. Klient nie może wysłać komunikatu. Określona kolejka utraconych wiadomości nie istnieje lub nie można jej zapisać. Upewnij się, że kolejka istnieje z odpowiednią autoryzacją do zapisu.|  
|MsmqGetPrivateComputerInformationError|Sprawdzenie wersji nie powiodło się z powodu określonego błędu. Nie można wykryć wersji usługi MSMQ, wszystkie operacje, które znajdują się w tym kanale w kolejce, zakończą się niepowodzeniem. Upewnij się, że usługa MSMQ jest zainstalowana i jest dostępna.|  
|MsmqNoAssurancesForVolatile|Weryfikacja powiązania usługi nie powiodła się. Nie można uruchomić punktu końcowego usługi lub klienta. Właściwość ExactlyOnce ma wartość true, a właściwość trwała ma wartość false. To nie jest obsługiwane. Aby rozwiązać konflikt, Popraw jedną z tych właściwości.|  
|MsmqNonTransactionalQueueNeeded|Wykryto niezgodność między konfiguracją powiązania i kolejki MSMQ. Nie można uruchomić punktu końcowego usługi. Właściwość ExactlyOnce ma wartość false, a kolejka, z której mają zostać odczytane wiadomości, jest kolejką transakcyjną. Popraw błąd, ustawiając właściwość ExactlyOnce na true lub utwórz powiązanie nietransakcyjne.|  
|MsmqOpenError|Wystąpił błąd podczas otwierania określonej kolejki. Nie można wysłać ani odebrać komunikatu z kolejki. Upewnij się, że usługa MSMQ jest zainstalowana i uruchomiona. Upewnij się również, że kolejka jest dostępna do otwarcia z wymaganym trybem dostępu i autoryzacją.|  
|MsmqPathLookupError|Wystąpił błąd podczas konwertowania określonej nazwy ścieżki kolejki na nazwę formatu. Wszystkie operacje w kanale umieszczonym w kolejce nie powiodły się. Upewnij się, że adres kolejki jest prawidłowy. Usługa MSMQ musi być zainstalowana z włączoną integracją Active Directory, a dostęp do niej jest dostępny.|  
|MsmqPerAppDLQRequiresCustom|Sprawdzanie poprawności powiązania na kliencie nie powiodło się. Klient nie może wysyłać komunikatów. Właściwość CustomDeadLetterQueue jest ustawiona, ale Właściwość DeadLetterQueue nie jest ustawiona na wartość Custom. Ustaw właściwość DeadLetterQueue na wartość Custom.|  
|MsmqPerAppDLQRequiresExactlyOnce|Weryfikacja powiązania dla klienta nie powiodła się. Klient nie może wysyłać komunikatów. Konflikt we właściwościach powiązania jest spowodowany błędem. Aby można było użyć niestandardowej kolejki utraconych wiadomości, należy ustawić wartość true, aby rozwiązać konflikt.|  
|MsmqPerAppDLQRequiresMsmq4|Wykryto niezgodność między powiązaniem i konfiguracją usługi MSMQ. Klient nie może wysyłać komunikatów. Aby można było użyć niestandardowej kolejki utraconych wiadomości, musi być zainstalowany program MSMQ w wersji 4,0 lub nowszej. Jeśli nie masz usługi MSMQ w wersji 4,0 lub nowszej, ustaw właściwość DeadLetterQueue na system lub None.|  
|MsmqReceiveError|Wystąpił błąd podczas otrzymywania komunikatu z kolejki. Upewnij się, że usługa MSMQ jest zainstalowana i uruchomiona. Upewnij się, że kolejka jest dostępna do odbierania z.|  
|MsmqSameTransactionExpected|Wystąpił błąd transakcji dla tej sesji. Wystąpił błąd kanału sesji. Wiadomości w sesji nie mogą być wysyłane ani odbierane. Nie można skojarzyć kolejkowanej sesji z więcej niż jedną transakcją. Upewnij się, że wszystkie komunikaty w sesji są wysyłane lub odbierane przy użyciu jednej transakcji.|  
|MsmqSendError|Wystąpił błąd podczas wysyłania do określonej kolejki. Upewnij się, że usługa MSMQ jest zainstalowana i uruchomiona. W przypadku wysyłania do kolejki lokalnej upewnij się, że kolejka istnieje z wymaganym trybem dostępu i autoryzacją.|  
|MsmqTimeSpanTooLarge|Czas wygaśnięcia komunikatu jest zbyt duży. Nie można wysłać komunikatu. Czas wygaśnięcia komunikatu (TTL) nie może przekroczyć maksymalnej wartości Int32.|  
|MsmqTokenProviderNeededForCertificates|Nie można znaleźć elementu X509SecurityTokenProvider. Nie można wysłać komunikatu. Tryb uwierzytelniania certyfikatu wymaga dostawcy tokenów X. 509. Upewnij się, że dostawca tokenów zabezpieczających jest dostępny dla zainstalowanego certyfikatu.|  
|MsmqTransactedDLQExpected|Wystąpił niezgodność między powiązaniem i konfiguracją usługi MSMQ. Nie można wysyłać komunikatów. Niestandardowa Kolejka utraconych wiadomości określona w powiązaniu musi być kolejką transakcji. Upewnij się, że niestandardowy adres kolejki utraconych wiadomości jest prawidłowy, a kolejka jest kolejką transakcyjną.|  
|MsmqTransactionalQueueNeeded|Wystąpił niezgodność między powiązaniem i konfiguracją kolejki MSMQ. Nie można uruchomić punktu końcowego usługi. Właściwość ExactlyOnce ma wartość true, a kolejka odczytana z wiadomości nie jest kolejką transakcyjną. Aby poprawić błąd, ustaw dla właściwości ExactlyOnce wartość false lub Utwórz kolejkę transakcyjną dla tego powiązania.|  
|MsmqTransactionCurrentRequired|Żadna transakcja nie jest dostępna do wysyłania wiadomości w sesji. W celu wysłania komunikatu w kolejce sesja wymaga transakcji. Upewnij się, że określono zakres transakcji w celu wysłania wiadomości w sesji.|  
|MsmqTransactionRequired|Transakcja jest wymagana, ale jest niedostępna. Nie można wysyłać ani odbierać wiadomości. Upewnij się, że zakres transakcji jest określony do wysyłania lub odbierania wiadomości.|  
|MsmqUnsupportedSerializationFormat|Wystąpił błąd deserializacji. Nie można odebrać wiadomości i został on porzucony. Określony format serializacji nie jest obsługiwany.|  
|MsmqWrongPrivateQueueSyntax|Adres URL jest nieprawidłowy. Adres URL kolejki nie może zawierać znaku "$". Użyj składni w usłudze net. MSMQ://machine/private/queueName, aby rozwiązać kolejkę prywatną.|
