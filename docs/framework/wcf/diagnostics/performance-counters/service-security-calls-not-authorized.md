---
title: 'Usługa: Wywołania zabezpieczeń bez autoryzacji'
ms.date: 03/30/2017
ms.assetid: 3024b20a-5250-4bd1-a38c-c6d79f89610b
ms.openlocfilehash: 32b0a62ecf9364270f5580787b7e129af5ac80b2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236913"
---
# <a name="service-security-calls-not-authorized"></a>Usługa: Wywołania zabezpieczeń bez autoryzacji

Nazwa licznika: wywołania zabezpieczeń nie są autoryzowane.  
  
## <a name="description"></a>Opis  

 Licznik jest zwiększany, gdy <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> Metoda zwraca `false` . Wskazuje on, że komunikat przychodzący jest prawidłowym użytkownikiem i chroniony prawidłowo, ale użytkownik nie ma uprawnień do wykonywania określonych zadań.
