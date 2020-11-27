---
title: 'Punkt końcowy: wywołania zabezpieczeń nie są autoryzowane'
ms.date: 03/30/2017
ms.assetid: d25095ff-9ff0-4c69-a674-4e6a9fe3f4dc
ms.openlocfilehash: 3979eec15759989b638e1cc813cb78a0c008c3a4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256511"
---
# <a name="endpoint-security-calls-not-authorized"></a>Punkt końcowy: wywołania zabezpieczeń nie są autoryzowane

Nazwa licznika: wywołania zabezpieczeń nie są autoryzowane.  
  
## <a name="description"></a>Opis  

 Licznik jest zwiększany, gdy <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> Metoda zwraca `false` . Wskazuje on, że komunikat przychodzący jest prawidłowym użytkownikiem i chroniony prawidłowo, ale użytkownik nie ma uprawnień do wykonywania określonych zadań.
