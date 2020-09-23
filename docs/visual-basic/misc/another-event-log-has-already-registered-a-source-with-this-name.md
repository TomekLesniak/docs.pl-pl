---
title: Inny dziennik zdarzeń zarejestrował już źródło o tej nazwie
ms.date: 07/20/2015
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
ms.openlocfilehash: 333c28036e2d1b7514c7370b98ff70a6d195a9dd
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058394"
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a>Inny dziennik zdarzeń zarejestrował już źródło o tej nazwie

Podjęto próbę zapisania wpisu w dzienniku zdarzeń, w którym określone źródło jest zarejestrowane w innym dzienniku zdarzeń.  
  
 Należy ustawić <xref:System.Diagnostics.EventLog.Source%2A> Właściwość <xref:System.Diagnostics.EventLog> wystąpienia składnika, zanim składnik zapisze wpis w dzienniku. W takim przypadku system sprawdza, czy określone źródło jest zarejestrowane w dzienniku zdarzeń, do którego składnik jest zapisywany, i wywołuje w <xref:System.Diagnostics.EventLog.CreateEventSource%2A> razie potrzeby.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Usuń skojarzenie źródła z pierwszym dziennikiem przy użyciu <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> metody lub.  
  
2. Zarejestruj źródło w nowym dzienniku.  
  
## <a name="see-also"></a>Zobacz także

- [My. Application. log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
