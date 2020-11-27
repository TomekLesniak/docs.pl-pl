---
title: Przestrzeń nazw System.Net.PeerToPeer.Collaboration — informacje
ms.date: 03/30/2017
ms.assetid: b5d8c1c1-6844-4947-9759-c7f1b564bded
ms.openlocfilehash: 54eaf1a99aab8b1db61f4b46237d57104c9d1a44
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250713"
---
# <a name="about-the-systemnetpeertopeercollaboration-namespace"></a>Przestrzeń nazw System.Net.PeerToPeer.Collaboration — informacje

<xref:System.Net.PeerToPeer.Collaboration>Przestrzeń nazw zawiera klasy i interfejsy API, które są używane do implementowania działań współpracy równorzędnej przy użyciu infrastruktury współpracy równorzędnej.  
  
## <a name="classes"></a>Klasy  

 Główne klasy używane w implementacji działania dotyczącego współpracy równorzędnej są następujące:  
  
- <xref:System.Net.PeerToPeer.Collaboration.ContactManager>, Który może być używany do przechowywania kontaktów równorzędnych.  
  
- , <xref:System.Net.PeerToPeer.Collaboration.PeerApplication> W którym można współpracować, takich jak rozwiązanie do gier, klienta czatu lub konferencji.  
  
- Elementy równorzędne, które będą współpracować w działaniu.  Te elementy równorzędne mogą być reprezentowane <xref:System.Net.PeerToPeer.Collaboration.PeerContact> jako <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe> obiekty, lub <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint> .  
  
- <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration>Sama klasa statyczna, która określa, które aplikacje są dostępne i które z nich uczestniczą.  
  
 <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A>Metody są używane do zapraszania elementów równorzędnych do sesji współpracy.  Wywołujący element równorzędny może subskrybować innego elementu równorzędnego dla zdarzeń, które sygnalizują aktualizacje aplikacji, obiektów lub informacji o obecności powiązane z sesją współpracy. Klasy obecności określają, czy <xref:System.Net.PeerToPeer.Collaboration.Peer> jest dostępna do współpracy, a <xref:System.Net.PeerToPeer.Collaboration.PeerScope> Klasa jest używana do określenia, jak dużo udziału jest dozwolony dla elementu równorzędnego:  <xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet> (globalna), <xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe> , (Subnet) lub <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None> .  
  
 Sesja współpracy obejmuje cztery kroki:  
  
- Odnajdowa. Odnajdywanie lub publikowanie aplikacji, elementów równorzędnych i informacji o obecności.  Na przykład Znajdź inne osoby w podsieci lokalnej, na których zainstalowano te same gry.  
  
- Zaproszenie. Wyślij i zaakceptuj bezpieczne zaproszenia dla zdalnych elementów równorzędnych w celu uruchomienia lub dołączenia <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> sesji.  
  
- Zarządzanie kontaktami. Dodawanie odnalezionych elementów równorzędnych jako kontaktów do <xref:System.Net.PeerToPeer.Collaboration.ContactManager> .  
  
- Zawiadomienia. Podczas ustanawiania komunikacji należy używać <xref:System.Net> interfejsów API, <xref:System.Net.PeerToPeer> interfejsu api lub Windows Communication Foundation klas kanałów równorzędnych w przypadku komunikacji wieloczęściowej.  
  
 Na przykład element równorzędny hosta uruchamia sesję współpracy i wykorzystuje <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> metodę dodawania zdalnego elementu równorzędnego i jednego z jego lokalnych elementów równorzędnych do Menedżera kontaktów elementu równorzędnego hosta.  Trze użytkownicy będą następnie uczestniczyć we własnej prywatnej sesji współpracy.  
  
 Typowe aplikacje P2P to: wywołania konferencji do współpracy z notatkami i tworzenia notatek, aplikacji do rozmów bezserwerowych, reklam interaktywnych i sesji gier online.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Net.PeerToPeer.Collaboration>
