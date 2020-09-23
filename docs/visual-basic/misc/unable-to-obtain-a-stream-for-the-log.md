---
title: Nie można uzyskać strumienia dziennika
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
ms.openlocfilehash: 887356fac3abe5c9d28751f7c4d3b1908ed35acb
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078388"
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a><span data-ttu-id="7304f-102">Nie można uzyskać strumienia dziennika</span><span class="sxs-lookup"><span data-stu-id="7304f-102">Unable to obtain a stream for the log</span></span>

<span data-ttu-id="7304f-103">Nie można uzyskać strumienia dla dziennika.</span><span class="sxs-lookup"><span data-stu-id="7304f-103">Unable to obtain a stream for the log.</span></span> <span data-ttu-id="7304f-104">Potencjalne nazwy plików na podstawie \<name> są już używane.</span><span class="sxs-lookup"><span data-stu-id="7304f-104">Potential file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="7304f-105"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>Klasa nie może utworzyć nowego pliku dziennika, ponieważ wszystkie potencjalne nazwy plików dziennika na podstawie \<name> są już używane.</span><span class="sxs-lookup"><span data-stu-id="7304f-105">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not create a new log file because all potential log file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="7304f-106">Zbyt wiele plików dziennika może wskazywać na problem z architekturą aplikacji.</span><span class="sxs-lookup"><span data-stu-id="7304f-106">Having too many log files may indicate an architectural problem with the application.</span></span> <span data-ttu-id="7304f-107">Aby uzyskać więcej informacji, zobacz dokumentację <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> klasy.</span><span class="sxs-lookup"><span data-stu-id="7304f-107">See the documentation for the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class for more information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7304f-108">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="7304f-108">To correct this error</span></span>  
  
1. <span data-ttu-id="7304f-109">Ustaw <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> Właściwość na <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> lub, <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> Aby dołączać sygnaturę daty do nazwy pliku dziennika.</span><span class="sxs-lookup"><span data-stu-id="7304f-109">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> property to <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> or <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> to include a date-stamp in the log file name.</span></span>  
  
2. <span data-ttu-id="7304f-110">Archiwizuj istniejące dzienniki i usuwaj je z komputera, aby umożliwić <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> obiektowi tworzenie nowych dzienników.</span><span class="sxs-lookup"><span data-stu-id="7304f-110">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7304f-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7304f-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>
- [<span data-ttu-id="7304f-112">My. Application. log</span><span class="sxs-lookup"><span data-stu-id="7304f-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="7304f-113">My. Application. info. DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="7304f-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
