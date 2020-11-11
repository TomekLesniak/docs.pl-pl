---
ms.openlocfilehash: 8c05af045d2d9666b20f36e36c68cc853f906eae
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506878"
---

<span data-ttu-id="d13c9-101">Podczas instalowania pakietu .NET może zostać wyświetlony komunikat o błędzie podobny do `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'` .</span><span class="sxs-lookup"><span data-stu-id="d13c9-101">While installing the .NET package, you may see an error similar to `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`.</span></span> <span data-ttu-id="d13c9-102">Ogólnie mówiąc, ten błąd oznacza, że źródło danych pakietu dla platformy .NET jest uaktualniane z nowszymi wersjami pakietów i należy spróbować ponownie później.</span><span class="sxs-lookup"><span data-stu-id="d13c9-102">Generally speaking, this error means that the package feed for .NET is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="d13c9-103">Podczas uaktualniania kanał informacyjny pakietu nie powinien być dostępny przez więcej niż 2 godziny.</span><span class="sxs-lookup"><span data-stu-id="d13c9-103">During an upgrade, the package feed should not be unavailable for more than 2 hours.</span></span> <span data-ttu-id="d13c9-104">Jeśli ten błąd będzie ciągle wyświetlany przez ponad 2 godziny, należy rozwiązać problem o <https://github.com/dotnet/core/issues> .</span><span class="sxs-lookup"><span data-stu-id="d13c9-104">If you continually receive this error for more than 2 hours, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
