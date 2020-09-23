---
title: Nie można uzyskać pełnej nazwy systemu operacyjnego z powodu błędu wewnętrznego
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 744d549b9313727af2feb82e45c24b729cae7262
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91079090"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="8d2c5-102">Nie można uzyskać pełnej nazwy systemu operacyjnego z powodu błędu wewnętrznego</span><span class="sxs-lookup"><span data-stu-id="8d2c5-102">Could not obtain full operation system name due to internal error</span></span>

<span data-ttu-id="8d2c5-103">Nie można uzyskać pełnej nazwy systemu operacyjnego z powodu błędu wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="8d2c5-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="8d2c5-104">Może to być spowodowane tym, że usługa WMI nie jest istniejąca na bieżącym komputerze.</span><span class="sxs-lookup"><span data-stu-id="8d2c5-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="8d2c5-105">Wywołanie `My.Computer.Info.OSFullName` właściwości nie powiodło się.</span><span class="sxs-lookup"><span data-stu-id="8d2c5-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="8d2c5-106">Możliwą przyczyną tego błędu jest to, że Instrumentacja zarządzania Windows (WMI) nie jest zainstalowana na bieżącym komputerze.</span><span class="sxs-lookup"><span data-stu-id="8d2c5-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8d2c5-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="8d2c5-107">To correct this error</span></span>  
  
1. <span data-ttu-id="8d2c5-108">Dodaj `Try...Catch` blok wokół wywołania `My.Computer.Info.OSFullName` właściwości.</span><span class="sxs-lookup"><span data-stu-id="8d2c5-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2. <span data-ttu-id="8d2c5-109">Aby uzyskać więcej informacji na temat usługi WMI i sposobu jej instalowania, przejdź do i wyszukaj ciąg "Instrumentacja zarządzania Windows Core".</span><span class="sxs-lookup"><span data-stu-id="8d2c5-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d2c5-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8d2c5-110">See also</span></span>

- [<span data-ttu-id="8d2c5-111">My. Computer. info. OSFullName</span><span class="sxs-lookup"><span data-stu-id="8d2c5-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [<span data-ttu-id="8d2c5-112">Obsługa i zgłaszanie wyjątków w programie .NET</span><span class="sxs-lookup"><span data-stu-id="8d2c5-112">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="8d2c5-113">Try...Catch...Finally, instrukcja</span><span class="sxs-lookup"><span data-stu-id="8d2c5-113">Try...Catch...Finally Statement</span></span>](../language-reference/statements/try-catch-finally-statement.md)
