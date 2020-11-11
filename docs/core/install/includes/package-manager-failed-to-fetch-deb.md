---
ms.openlocfilehash: 3bb59ba23214f67100d3a78bb689c941b2d187e6
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506989"
---

<span data-ttu-id="7cfd9-101">Podczas instalowania pakietu .NET może zostać wyświetlony komunikat o błędzie podobny do `Failed to fetch ... File has unexpected size ... Mirror sync in progress?` .</span><span class="sxs-lookup"><span data-stu-id="7cfd9-101">While installing the .NET package, you may see an error similar to `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`.</span></span> <span data-ttu-id="7cfd9-102">Ten błąd może oznaczać, że źródło danych pakietu dla platformy .NET jest uaktualniane z nowszymi wersjami pakietu i należy spróbować ponownie później.</span><span class="sxs-lookup"><span data-stu-id="7cfd9-102">This error could mean that the package feed for .NET is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="7cfd9-103">Podczas uaktualniania kanał informacyjny pakietu nie powinien być dostępny przez ponad 30 minut.</span><span class="sxs-lookup"><span data-stu-id="7cfd9-103">During an upgrade, the package feed shouldn't be unavailable for more than 30 minutes.</span></span> <span data-ttu-id="7cfd9-104">Jeśli ten błąd będzie ciągle wyświetlany przez ponad 30 minut, należy rozwiązać problem o <https://github.com/dotnet/core/issues> .</span><span class="sxs-lookup"><span data-stu-id="7cfd9-104">If you continually receive this error for more than 30 minutes, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
