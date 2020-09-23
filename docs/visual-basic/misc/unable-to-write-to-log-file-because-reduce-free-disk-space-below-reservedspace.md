---
title: Nie można zapisać w pliku dziennika, ponieważ zapisanie w nim spowodowałoby zmniejszenie ilości wolnego miejsca na dysku poniżej wartości ReservedSpace
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ReservedSpaceEncroached
ms.assetid: 95832e70-4ecc-47aa-90c1-f35c4d468151
ms.openlocfilehash: e5247876c683812edf0eb73ab5f1a5e607b48102
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075606"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-reduce-free-disk-space-below-reservedspace-value"></a><span data-ttu-id="d9ae7-102">Nie można zapisać w pliku dziennika, ponieważ zapisanie w nim spowodowałoby zmniejszenie ilości wolnego miejsca na dysku poniżej wartości ReservedSpace</span><span class="sxs-lookup"><span data-stu-id="d9ae7-102">Unable to write to log file because writing to it would reduce free disk space below ReservedSpace value</span></span>

<span data-ttu-id="d9ae7-103"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>Klasa nie może zapisać w pliku dziennika, ponieważ:</span><span class="sxs-lookup"><span data-stu-id="d9ae7-103">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not write to the log file because:</span></span>  
  
- <span data-ttu-id="d9ae7-104">Ilość wolnego miejsca na dysku (w bajtach) jest mniejsza niż wartość <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="d9ae7-104">The amount of free disk space (in bytes) is less than the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> property</span></span>  
  
     <span data-ttu-id="d9ae7-105">lub</span><span class="sxs-lookup"><span data-stu-id="d9ae7-105">—and—</span></span>  
  
- <span data-ttu-id="d9ae7-106">Wartość <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> Właściwości była <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException> .</span><span class="sxs-lookup"><span data-stu-id="d9ae7-106">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property was <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d9ae7-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="d9ae7-107">To correct this error</span></span>  
  
1. <span data-ttu-id="d9ae7-108">Archiwizuj istniejące dzienniki i usuwaj je z komputera, aby umożliwić <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> obiektowi tworzenie nowych dzienników.</span><span class="sxs-lookup"><span data-stu-id="d9ae7-108">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
2. <span data-ttu-id="d9ae7-109">Zmień wartość <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> właściwości na mniejszą liczbę, aby zarezerwować mniej miejsca na dysku.</span><span class="sxs-lookup"><span data-stu-id="d9ae7-109">Change the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> property to a smaller number to reserve less disk space.</span></span>  
  
3. <span data-ttu-id="d9ae7-110">Ustaw <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> Właściwość na <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> , aby odrzucać komunikaty bez ostrzeżenia, jeśli ilość wolnego miejsca na dysku jest niewystarczająca.</span><span class="sxs-lookup"><span data-stu-id="d9ae7-110">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property to <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> to discard messages without warning if there is not enough free disk space.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ae7-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d9ae7-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [<span data-ttu-id="d9ae7-112">My. Application. log</span><span class="sxs-lookup"><span data-stu-id="d9ae7-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="d9ae7-113">My. Application. info. DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="d9ae7-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
