---
title: Dodawanie stanu online i offline
ms.date: 03/30/2017
ms.assetid: 05e5f51d-81b6-4c17-b364-9dda447a5fce
ms.openlocfilehash: 08ae4a20ced9626504c9fd2045416460e0878c5b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96292925"
---
# <a name="adding-online-and-offline-status"></a>Dodawanie stanu online i offline

W wielu przypadkach ważne jest, aby aplikacja monitorowała szczegółowe informacje o stanie połączenia kanału równorzędnego. Te informacje można uzyskać, wywołując `GetProperty` metodę dla implementacji <xref:System.ServiceModel.IOnlineStatus> interfejsu. Obiekt z implementacją tego interfejsu może monitorować stan połączenia lub rejestr dla programów obsługi zdarzeń, takich jak i i `OnOnline` `OnOffline` reagować natychmiast po wystąpieniu zmian stanu online.  
  
 W infrastrukturze kanału równorzędnego klient jest traktowany jako w trybie online, jeśli jest połączony z co najmniej jednym innym węzłem równorzędnym i w przeciwnym razie w trybie offline. Może to być szczególnie przydatne w przypadku debugowania aplikacji tworzących lub wyświetlania szczegółowych informacji dla użytkownika końcowego.  
  
> [!NOTE]
> Procedura obsługi zdarzeń online powinna najpierw upewnić się, że węzeł jest otwarty przed wysłaniem jakichkolwiek komunikatów.  
  
## <a name="see-also"></a>Zobacz też

- [Tworzenie aplikacji kanału równorzędnego](building-a-peer-channel-application.md)
