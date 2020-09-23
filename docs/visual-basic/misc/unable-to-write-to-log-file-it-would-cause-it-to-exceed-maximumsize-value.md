---
title: Nie można zapisać w pliku dziennika, ponieważ zapisanie go spowodowałoby przekroczenie wartości MaximumSize
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
ms.openlocfilehash: 95a7b9036e7c1494cd44c250b0580bab5144417b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059460"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a><span data-ttu-id="35597-102">Nie można zapisać w pliku dziennika, ponieważ zapisanie go spowodowałoby przekroczenie wartości MaximumSize</span><span class="sxs-lookup"><span data-stu-id="35597-102">Unable to write to log file because writing to it would cause it to exceed MaximumSize value</span></span>

<span data-ttu-id="35597-103"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>Klasa nie może zapisać w pliku dziennika, ponieważ:</span><span class="sxs-lookup"><span data-stu-id="35597-103">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not write to the log file because:</span></span>  
  
- <span data-ttu-id="35597-104">Rozmiar pliku dziennika (w bajtach) jest większy niż wartość <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> właściwości</span><span class="sxs-lookup"><span data-stu-id="35597-104">The log file size (in bytes) is greater than the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property</span></span>  
  
     <span data-ttu-id="35597-105">lub</span><span class="sxs-lookup"><span data-stu-id="35597-105">—and—</span></span>  
  
- <span data-ttu-id="35597-106">Wartość <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> Właściwości była <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException> .</span><span class="sxs-lookup"><span data-stu-id="35597-106">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property was <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="35597-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="35597-107">To correct this error</span></span>  
  
1. <span data-ttu-id="35597-108">Archiwizuj istniejące dzienniki i usuwaj je z komputera, aby umożliwić <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> obiektowi tworzenie nowych dzienników.</span><span class="sxs-lookup"><span data-stu-id="35597-108">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
2. <span data-ttu-id="35597-109">Zmień wartość właściwości tak, <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> aby zezwalała na większe dzienniki.</span><span class="sxs-lookup"><span data-stu-id="35597-109">Change the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property to allow for larger logs.</span></span>  
  
3. <span data-ttu-id="35597-110">Ustaw <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> Właściwość na <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> , aby odrzucać komunikaty bez ostrzeżenia, jeśli dziennik jest zbyt duży.</span><span class="sxs-lookup"><span data-stu-id="35597-110">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property to <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> to discard messages without warning if the log is too large.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35597-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="35597-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [<span data-ttu-id="35597-112">My. Application. log</span><span class="sxs-lookup"><span data-stu-id="35597-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="35597-113">My. Application. info. DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="35597-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
