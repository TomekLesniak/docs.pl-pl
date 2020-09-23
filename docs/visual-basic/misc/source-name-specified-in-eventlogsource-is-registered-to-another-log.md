---
title: Nazwa źródła określona w EventLogSource jest zarejestrowana w dzienniku innym niż określony w dzienniku zdarzeń
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: 1b577e3b0613001b6241dcfdc59c8c84029197d2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058933"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a><span data-ttu-id="5c8bf-102">Nazwa źródła określona w EventLogSource jest zarejestrowana w dzienniku innym niż określony w dzienniku zdarzeń</span><span class="sxs-lookup"><span data-stu-id="5c8bf-102">Source name specified in EventLogSource is registered to a log other than that specified in EventLogName</span></span>

<span data-ttu-id="5c8bf-103">`EventLog`Próbuje odwołać się do źródła, które jest zarejestrowane w innym dzienniku.</span><span class="sxs-lookup"><span data-stu-id="5c8bf-103">The `EventLog` is attempting to refer to a source that is registered to a different log.</span></span> <span data-ttu-id="5c8bf-104">Jeśli zapisujesz wpisy w dzienniku zdarzeń, musisz określić <xref:System.Diagnostics.EventLog.Source%2A> Właściwość.</span><span class="sxs-lookup"><span data-stu-id="5c8bf-104">If you are writing entries to an event log, you must specify the <xref:System.Diagnostics.EventLog.Source%2A> property.</span></span> <span data-ttu-id="5c8bf-105"><xref:System.Diagnostics.EventLog.Source%2A>Właściwość rejestruje składnik w dzienniku zdarzeń jako prawidłowe Źródło wpisów.</span><span class="sxs-lookup"><span data-stu-id="5c8bf-105">The <xref:System.Diagnostics.EventLog.Source%2A> property registers your component with the event log as a valid source of entries.</span></span> <span data-ttu-id="5c8bf-106">Pojedyncze źródło może być skojarzone z (i w związku z tym zapisem) tylko jednego dziennika zdarzeń naraz.</span><span class="sxs-lookup"><span data-stu-id="5c8bf-106">A single source can be associated with (and therefore write entries to) only one event log at a time.</span></span>  
  
 <span data-ttu-id="5c8bf-107">Domyślnie, jeśli próbujesz napisać wpis bez wcześniejszego zarejestrowania składnika jako prawidłowego źródła, system automatycznie rejestruje źródło w dzienniku zdarzeń przy użyciu wartości <xref:System.Diagnostics.EventLog.Source%2A> właściwości jako ciągu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="5c8bf-107">By default, if you try to write an entry without first having registered your component as a valid source, the system automatically registers the source with the event log, using the value of the <xref:System.Diagnostics.EventLog.Source%2A> property as the source string.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5c8bf-108">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="5c8bf-108">To correct this error</span></span>  
  
- <span data-ttu-id="5c8bf-109">Upewnij się, że źródło jest zarejestrowane w prawidłowym dzienniku.</span><span class="sxs-lookup"><span data-stu-id="5c8bf-109">Make sure the source is registered to the correct log.</span></span> <span data-ttu-id="5c8bf-110">Aby to zrobić, użyj <xref:System.Diagnostics.EventLog.CreateEventSource%2A> metody lub jednego z jego przeciążeń, aby określić ciąg, który jednoznacznie identyfikuje składnik w dzienniku zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="5c8bf-110">To do this, use the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method or one of its overloads to specify a string that uniquely identifies your component to the event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c8bf-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5c8bf-111">See also</span></span>

- <span data-ttu-id="5c8bf-112">[Administrowanie dziennikami zdarzeń](/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5c8bf-112">[Administering Event Logs](/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span></span>
- <span data-ttu-id="5c8bf-113">[Odwołania do dziennika zdarzeń](/previous-versions/visualstudio/visual-studio-2008/k43k9z2a(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5c8bf-113">[Event Log References](/previous-versions/visualstudio/visual-studio-2008/k43k9z2a(v=vs.90))</span></span>
- <span data-ttu-id="5c8bf-114">[Instrukcje: Dodawanie aplikacji jako źródła wpisów dziennika zdarzeń](/previous-versions/visualstudio/visual-studio-2008/xz73e171(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5c8bf-114">[How to: Add Your Application as a Source of Event Log Entries](/previous-versions/visualstudio/visual-studio-2008/xz73e171(v=vs.90))</span></span>
- <span data-ttu-id="5c8bf-115">[Instrukcje: Usuwanie źródła zdarzeń](/previous-versions/visualstudio/visual-studio-2008/k57466fc(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5c8bf-115">[How to: Remove an Event Source](/previous-versions/visualstudio/visual-studio-2008/k57466fc(v=vs.90))</span></span>
