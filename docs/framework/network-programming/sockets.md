---
title: Gniazda
description: Dowiedz się więcej o klasie .NET Framework Socket, która jest wersją kodu zarządzanego usług gniazd dostarczonych przez interfejs API WinSock32.
ms.date: 03/30/2017
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- Windows Sockets
- sockets, about sockets
- Socket class, about Socket class
- sockets
- requesting data from Internet, sockets
- network, sockets
- receiving data, sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
ms.openlocfilehash: e00d04164f7ce5251b7f30b5abd16c14643f6862
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263129"
---
# <a name="sockets"></a>Gniazda

<xref:System.Net.Sockets>Przestrzeń nazw zawiera zarządzaną implementację interfejsu Windows Sockets. Wszystkie inne klasy dostępu do sieci w <xref:System.Net> przestrzeni nazw są zbudowane na podstawie tej implementacji gniazd.  
  
 Klasa .NET Framework <xref:System.Net.Sockets.Socket> jest wersją kodu zarządzanego usługi gniazd udostępnianą przez interfejs API WinSock32. W większości przypadków klasy **gniazda** są po prostu kierowanie danych do ich natywnych odpowiedników Win32 i obsługę wszelkich niezbędnych kontroli zabezpieczeń.  
  
 Klasa **Socket** obsługuje dwa podstawowe tryby, synchroniczne i asynchroniczne. W trybie synchronicznym wywołania funkcji wykonujących operacje sieciowe (takie jak <xref:System.Net.Sockets.Socket.Send%2A> i <xref:System.Net.Sockets.Socket.Receive%2A> ) czekają na zakończenie operacji przed zwróceniem kontroli do wywołującego programu. W trybie asynchronicznym te wywołania zwracają się natychmiast.  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: tworzenie gniazda](how-to-create-a-socket.md)

- [Korzystanie z protokołów aplikacji](using-application-protocols.md)
