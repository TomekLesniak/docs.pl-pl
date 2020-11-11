---
ms.openlocfilehash: 8c05af045d2d9666b20f36e36c68cc853f906eae
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506878"
---

Podczas instalowania pakietu .NET może zostać wyświetlony komunikat o błędzie podobny do `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'` . Ogólnie mówiąc, ten błąd oznacza, że źródło danych pakietu dla platformy .NET jest uaktualniane z nowszymi wersjami pakietów i należy spróbować ponownie później. Podczas uaktualniania kanał informacyjny pakietu nie powinien być dostępny przez więcej niż 2 godziny. Jeśli ten błąd będzie ciągle wyświetlany przez ponad 2 godziny, należy rozwiązać problem o <https://github.com/dotnet/core/issues> .
