---
title: Nie można utworzyć niezbędnego pliku tymczasowego
ms.date: 07/20/2015
f1_keywords:
- vbrID322
ms.assetid: 53617b5b-eb06-4188-b4c2-8607cb9fbc79
ms.openlocfilehash: c6d8e471796a0fb745289df8b3d1b156265949ca
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874662"
---
# <a name="cant-create-necessary-temporary-file"></a><span data-ttu-id="ed126-102">Nie można utworzyć niezbędnego pliku tymczasowego</span><span class="sxs-lookup"><span data-stu-id="ed126-102">Can't create necessary temporary file</span></span>

<span data-ttu-id="ed126-103">Dysk jest zapełniony, który zawiera katalog określony przez zmienną środowiskową TEMP, lub zmienna środowiskowa TEMP określa nieprawidłowy dysk lub katalog tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="ed126-103">Either the drive is full that contains the directory specified by the TEMP environment variable, or the TEMP environment variable specifies an invalid or read-only drive or directory.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ed126-104">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="ed126-104">To correct this error</span></span>  
  
1. <span data-ttu-id="ed126-105">Usuń pliki z dysku, jeśli są pełne.</span><span class="sxs-lookup"><span data-stu-id="ed126-105">Delete files from the drive, if full.</span></span>  
  
2. <span data-ttu-id="ed126-106">Określ inny dysk w zmiennej środowiskowej TEMP.</span><span class="sxs-lookup"><span data-stu-id="ed126-106">Specify a different drive in the TEMP environment variable.</span></span>  
  
3. <span data-ttu-id="ed126-107">Określ prawidłowy dysk dla zmiennej środowiskowej TEMP.</span><span class="sxs-lookup"><span data-stu-id="ed126-107">Specify a valid drive for the TEMP environment variable.</span></span>  
  
4. <span data-ttu-id="ed126-108">Usuń ograniczenie tylko do odczytu z aktualnie określonego dysku lub katalogu.</span><span class="sxs-lookup"><span data-stu-id="ed126-108">Remove the read-only restriction from the currently specified drive or directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed126-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ed126-109">See also</span></span>

- [<span data-ttu-id="ed126-110">Typy błędów</span><span class="sxs-lookup"><span data-stu-id="ed126-110">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
