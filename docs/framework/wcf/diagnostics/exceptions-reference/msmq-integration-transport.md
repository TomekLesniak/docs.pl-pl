---
title: Transport integracji usługi MSMQ
ms.date: 03/30/2017
ms.assetid: 2bf9893a-fbd1-41fc-b6de-a41a44279936
ms.openlocfilehash: 032b6886152fb73c382fed1572e8c184a822b44f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248750"
---
# <a name="msmq-integration-transport"></a>Transport integracji usługi MSMQ

W tym temacie wymieniono wszystkie wyjątki wygenerowane przez Transport integracji usługi MSMQ.  
  
## <a name="exception-list"></a>Lista wyjątków  
  
|Kod zasobu|Ciąg zasobu|  
|-------------------|---------------------|  
|MessageSizeMustBeInIntegerRange|Ta fabryka buforuje wiadomości, więc rozmiary wiadomości muszą być wartościami z zakresu liczb całkowitych.|  
|MsmqByteArrayBodyExpected|Wystąpił niezgodność między określonym formatem serializacji i treścią komunikatu MSMQ. Nie można wysłać ani odebrać komunikatu. Format serializacji ByteArray wymaga, aby treść komunikatu MSMQ była typu Byte [].|  
|MsmqCannotDeserializeActiveXMessage|Wystąpił błąd serializacji ActiveX. Nie można wysłać ani odebrać komunikatu. Określony typ Variant dla treści nie jest zgodny z rzeczywistą treścią wiadomości MSMQ.|  
|MsmqCannotUseBodyTypeWithActiveXSerialization|Właściwości komunikatu są niezgodne. Nie można wysłać ani odebrać komunikatu. Nie można określić właściwości MessageType, jeśli jest używany format serializacji ActiveX.|  
|MsmqInvalidServiceOperationForMsmqIntegrationBinding|Weryfikacja MsmqIntegrationBinding nie powiodła się. Nie można uruchomić punktu końcowego usługi. Określone powiązanie nie obsługuje podpisu metody dla określonej operacji usługi w określonym kontrakcie. Popraw operację usługi, aby użyć MsmqIntegrationBinding.|  
|MsmqInvalidTypeDeserialization|Serializacja ActiveX nie powiodła się, ponieważ nie można rozpoznać formatu serializacji. Nie można wysłać ani odebrać komunikatu.|  
|MsmqInvalidTypeSerialization|Typ Variant nie został rozpoznany. Serializacja ActiveX nie powiodła się. Nie można wysłać ani odebrać komunikatu. Określony typ Variant nie jest obsługiwany.|  
|MsmqStreamBodyExpected|Niezgodność między formatem serializacji i zawartością treści. Nie można wysłać ani odebrać komunikatu. Tylko treść typu Stream można wysłać lub odebrać przy użyciu trybu serializacji strumienia.|
