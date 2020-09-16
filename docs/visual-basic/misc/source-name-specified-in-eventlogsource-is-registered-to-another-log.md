---
title: Nazwa źródła określona w EventLogSource jest zarejestrowana w dzienniku innym niż określony w dzienniku zdarzeń
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: da9f1756909d1c37e28f2dde62a7f8a73bb19f37
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555643"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a>Nazwa źródła określona w EventLogSource jest zarejestrowana w dzienniku innym niż określony w dzienniku zdarzeń
`EventLog`Próbuje odwołać się do źródła, które jest zarejestrowane w innym dzienniku. Jeśli zapisujesz wpisy w dzienniku zdarzeń, musisz określić <xref:System.Diagnostics.EventLog.Source%2A> Właściwość. <xref:System.Diagnostics.EventLog.Source%2A>Właściwość rejestruje składnik w dzienniku zdarzeń jako prawidłowe Źródło wpisów. Pojedyncze źródło może być skojarzone z (i w związku z tym zapisem) tylko jednego dziennika zdarzeń naraz.  
  
 Domyślnie, jeśli próbujesz napisać wpis bez wcześniejszego zarejestrowania składnika jako prawidłowego źródła, system automatycznie rejestruje źródło w dzienniku zdarzeń przy użyciu wartości <xref:System.Diagnostics.EventLog.Source%2A> właściwości jako ciągu źródłowego.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Upewnij się, że źródło jest zarejestrowane w prawidłowym dzienniku. Aby to zrobić, użyj <xref:System.Diagnostics.EventLog.CreateEventSource%2A> metody lub jednego z jego przeciążeń, aby określić ciąg, który jednoznacznie identyfikuje składnik w dzienniku zdarzeń.  
  
## <a name="see-also"></a>Zobacz także

- [Administrowanie dziennikami zdarzeń](/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))
- [Odwołania do dziennika zdarzeń](/previous-versions/visualstudio/visual-studio-2008/k43k9z2a(v=vs.90))
- [Instrukcje: Dodawanie aplikacji jako źródła wpisów dziennika zdarzeń](/previous-versions/visualstudio/visual-studio-2008/xz73e171(v=vs.90))
- [Instrukcje: Usuwanie źródła zdarzeń](/previous-versions/visualstudio/visual-studio-2008/k57466fc(v=vs.90))
