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
# <a name="unable-to-obtain-a-stream-for-the-log"></a>Nie można uzyskać strumienia dziennika

Nie można uzyskać strumienia dla dziennika. Potencjalne nazwy plików na podstawie \<name> są już używane.  
  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>Klasa nie może utworzyć nowego pliku dziennika, ponieważ wszystkie potencjalne nazwy plików dziennika na podstawie \<name> są już używane.  
  
 Zbyt wiele plików dziennika może wskazywać na problem z architekturą aplikacji. Aby uzyskać więcej informacji, zobacz dokumentację <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> klasy.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Ustaw <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> Właściwość na <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> lub, <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> Aby dołączać sygnaturę daty do nazwy pliku dziennika.  
  
2. Archiwizuj istniejące dzienniki i usuwaj je z komputera, aby umożliwić <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> obiektowi tworzenie nowych dzienników.  
  
## <a name="see-also"></a>Zobacz także

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>
- [My. Application. log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [My. Application. info. DirectoryPath](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
