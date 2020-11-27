---
title: Wywołania zabezpieczeń bez autoryzacji
ms.date: 03/30/2017
ms.assetid: cb6acdcd-7336-42e1-9ae8-ac891336cd58
ms.openlocfilehash: 5575b108353e9c434ff01e76edc127e8691f0bf4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276129"
---
# <a name="security-calls-not-authorized"></a>Wywołania zabezpieczeń bez autoryzacji

Nazwa licznika: wywołania zabezpieczeń nie są autoryzowane.  
  
## <a name="description"></a>Opis  

 Licznik jest zwiększany, gdy <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> Metoda zwraca `false` . Wskazuje on, że komunikat przychodzący jest prawidłowym użytkownikiem i chroniony prawidłowo, ale użytkownik nie ma uprawnień do wykonywania określonych zadań.
