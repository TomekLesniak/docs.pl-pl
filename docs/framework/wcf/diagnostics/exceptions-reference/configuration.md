---
title: Konfigurowanie
ms.date: 03/30/2017
ms.assetid: 86a6e12f-73b5-450e-8725-f4ca5fe0702c
ms.openlocfilehash: 2b14b9e66db7d3548022a728ec27137a14bf3e55
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96277624"
---
# <a name="configuration"></a>Konfigurowanie

W tym temacie wymieniono wszystkie wyjątki wygenerowane przez konfigurację programu Windows Communication Foundation (WCF).  
  
## <a name="exception-list"></a>Lista wyjątków  
  
|Kod zasobu|Ciąg zasobu|  
|-------------------|---------------------|  
|ConfigBindingCannotBeConfigured|Nie można skonfigurować powiązania w punkcie końcowym usługi.|  
|ConfigElementKeyNull|Określony klucz elementu konfiguracji nie może mieć wartości null.|  
|ConfigExtensionTypeNotRegisteredInCollection|Określony typ rozszerzenia nie jest zarejestrowany w określonej kolekcji rozszerzeń.|  
|ConfigIndexOutOfRange|Wartość określonego atrybutu znajduje się poza zakresem.|  
|ConfigInvalidBindingConfigurationName|Określona konfiguracja nie ma powiązania z określoną nazwą.|  
|ConfigInvalidBindingName|Określona konfiguracja nie ma powiązania z określoną nazwą. To jest nieprawidłowa wartość dla powiązania.|  
|ConfigInvalidCommonEndpointBehaviorType|Nie można dodać rozszerzenia określonego zachowania do wspólnego zachowania punktu końcowego, ponieważ nie implementuje określonego typu.|  
|ConfigInvalidCommonServiceBehaviorType|Nie można dodać rozszerzenia zachowań do typowego zachowania usługi, ponieważ nie implementuje określonego typu.|  
|ConfigInvalidEndpointBehaviorType|Nie można dodać rozszerzenia określonego zachowania do określonego zachowania punktu końcowego, ponieważ podstawowy typ zachowania nie implementuje interfejsu IServiceBehavior.|  
|ConfigInvalidExtensionType|Określony typ musi pochodzić od określonego rozszerzenia, które ma być używane w kolekcji.|  
|ConfigInvalidServiceBehaviorType|Nie można dodać rozszerzenia zachowania do zachowania usługi z określoną nazwą, ponieważ podstawowy typ zachowania nie implementuje interfejsu IServiceBehavior.|  
|ConfigMessageEncodingAlreadyInBinding|Nie można dodać określonego elementu kodowania komunikatów. Inny element kodowania komunikatów już istnieje w określonym powiązaniu. Dla każdego powiązania może istnieć tylko jeden element kodowania komunikatów.|  
|ConfigNoExtensionCollectionAssociatedWithType|Nie można odnaleźć kolekcji rozszerzeń skojarzonej z rozszerzeniem określonego typu.|  
|ConfigSectionNotFound|Nie można utworzyć konkretnej sekcji konfiguracji. Brak informacji w pliku Machine.config. Sprawdź, czy ta sekcja konfiguracji została prawidłowo zarejestrowana i czy nazwa sekcji została prawidłowo poprawna. W przypadku Windows Communication Foundation sekcji Uruchom polecenie ServiceModelReg.exe-i, aby naprawić ten błąd.|  
|ConfigTransportAlreadyInBinding|Nie można dodać określonego elementu transportowego. Inny element transportu już istnieje w określonym powiązaniu. Dla każdego powiązania może istnieć tylko jeden element kodowania komunikatów.|
