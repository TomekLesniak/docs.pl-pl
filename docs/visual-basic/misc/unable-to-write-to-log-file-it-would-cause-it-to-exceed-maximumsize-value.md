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
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a>Nie można zapisać w pliku dziennika, ponieważ zapisanie go spowodowałoby przekroczenie wartości MaximumSize

<xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>Klasa nie może zapisać w pliku dziennika, ponieważ:  
  
- Rozmiar pliku dziennika (w bajtach) jest większy niż wartość <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> właściwości  
  
     lub  
  
- Wartość <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> Właściwości była <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException> .  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Archiwizuj istniejące dzienniki i usuwaj je z komputera, aby umożliwić <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> obiektowi tworzenie nowych dzienników.  
  
2. Zmień wartość właściwości tak, <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> aby zezwalała na większe dzienniki.  
  
3. Ustaw <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> Właściwość na <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> , aby odrzucać komunikaty bez ostrzeżenia, jeśli dziennik jest zbyt duży.  
  
## <a name="see-also"></a>Zobacz także

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [My. Application. log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [My. Application. info. DirectoryPath](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
