---
title: Żadna mysz nie jest obecna
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoMouseIsPresent
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
ms.openlocfilehash: ceb850d98d29c232da304fbdfaddf5611714ef1a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078856"
---
# <a name="no-mouse-is-present"></a><span data-ttu-id="ee03b-102">Żadna mysz nie jest obecna</span><span class="sxs-lookup"><span data-stu-id="ee03b-102">No mouse is present</span></span>

<span data-ttu-id="ee03b-103">Jedna z właściwości `My.Computer.Mouse` obiektu została wywołana, ale na komputerze nie jest zainstalowany mysz ani port myszy.</span><span class="sxs-lookup"><span data-stu-id="ee03b-103">One of the properties of the `My.Computer.Mouse` object was called, but the computer has no mouse or mouse port installed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ee03b-104">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="ee03b-104">To correct this error</span></span>  
  
- <span data-ttu-id="ee03b-105">Dodaj `Try...Catch` blok wokół wywołania właściwości `My.Computer.Mouse` obiektu.</span><span class="sxs-lookup"><span data-stu-id="ee03b-105">Add a `Try...Catch` block around the call to the property of the `My.Computer.Mouse` object.</span></span>  
  
     <span data-ttu-id="ee03b-106">oraz</span><span class="sxs-lookup"><span data-stu-id="ee03b-106">— or —</span></span>  
  
- <span data-ttu-id="ee03b-107">Zainstaluj myszą na komputerze.</span><span class="sxs-lookup"><span data-stu-id="ee03b-107">Install a mouse on the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee03b-108">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ee03b-108">See also</span></span>

- [<span data-ttu-id="ee03b-109">My. Computer. Mouse</span><span class="sxs-lookup"><span data-stu-id="ee03b-109">My.Computer.Mouse</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse)
- [<span data-ttu-id="ee03b-110">Obsługa i zgłaszanie wyjątków w programie .NET</span><span class="sxs-lookup"><span data-stu-id="ee03b-110">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="ee03b-111">Try...Catch...Finally, instrukcja</span><span class="sxs-lookup"><span data-stu-id="ee03b-111">Try...Catch...Finally Statement</span></span>](../language-reference/statements/try-catch-finally-statement.md)
