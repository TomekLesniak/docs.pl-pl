---
title: Opcja kodowania wystąpienia
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: 416394eb346a7c82385da32a89bd54179b255cd4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279899"
---
# <a name="instance-encoding-option"></a>Opcja kodowania wystąpienia

Właściwość **opcji kodowania wystąpienia** przepływu pracy SQL umożliwia określenie, czy dostawca trwałości SQL powinien kompresować informacje o stanie wystąpienia przepływu pracy przy użyciu algorytmu GZip przed zapisaniem informacji w bazie danych trwałości. Dozwolone wartości tej właściwości to: GZip i none. Wartość domyślna to Brak. Na poniższej liście opisano te opcje.  
  
1. **Gzip**. Dostawca trwałości koduje informacje o stanie przy użyciu algorytmu GZip przed utrwaleniem informacji o stanie w bazie danych trwałości.  
  
2. **Brak**. Dostawca trwałości nie koduje informacji o stanie przed zapisaniem informacji w bazie danych trwałości.  
  
 Kodowanie informacji o stanie wystąpienia przepływu pracy przy użyciu strumienia GZip zmniejsza zużycie pamięci w bazie danych SQL, a także zmniejsza zużycie sieci, jeśli baza danych znajduje się na innym komputerze w sieci z komputera, na którym jest uruchomiony Host usługi przepływu pracy. Ogólną wskazówką jest ustawienie dla właściwości **opcji kodowanie wystąpienia** wartości **Brak** , jeśli stan wystąpienia przepływu pracy jest niewielki.
