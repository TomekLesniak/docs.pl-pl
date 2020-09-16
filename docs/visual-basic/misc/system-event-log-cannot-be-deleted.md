---
title: Nie można usunąć dziennika zdarzeń systemowych
ms.date: 07/20/2015
ms.assetid: 26ca8819-4ce5-49c6-98f3-27fe9e2e8e3d
ms.openlocfilehash: e00527300a77f6bc006555ee688e055e1a351056
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554960"
---
# <a name="system-event-log-cannot-be-deleted"></a><span data-ttu-id="42153-102">Nie można usunąć dziennika zdarzeń systemowych</span><span class="sxs-lookup"><span data-stu-id="42153-102">System event log cannot be deleted</span></span>
<span data-ttu-id="42153-103">Podjęto próbę usunięcia dziennika zdarzeń systemu, którego nie można usunąć.</span><span class="sxs-lookup"><span data-stu-id="42153-103">An attempt has been made to delete the system event log, which cannot be deleted.</span></span> <span data-ttu-id="42153-104">Dziennik systemowy śledzi zdarzenia systemowe, takie jak uruchamianie systemu i awarie sprzętu.</span><span class="sxs-lookup"><span data-stu-id="42153-104">The system log tracks system events such as system startup and hardware failures.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="42153-105">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="42153-105">To correct this error</span></span>  
  
- <span data-ttu-id="42153-106">Rozważ, aby aplikacja była zapisu do aplikacji lub dziennika niestandardowego, a nie dziennika zdarzeń systemu.</span><span class="sxs-lookup"><span data-stu-id="42153-106">Consider having your application write to an application or custom log, rather than the system event log.</span></span>  
  
- <span data-ttu-id="42153-107">Nie należy próbować usunąć dziennika zdarzeń systemu.</span><span class="sxs-lookup"><span data-stu-id="42153-107">Do not attempt to delete the system event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42153-108">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="42153-108">See also</span></span>

- <span data-ttu-id="42153-109">[Administrowanie dziennikami zdarzeń](/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="42153-109">[Administering Event Logs](/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span></span>
- <span data-ttu-id="42153-110">[Instrukcje: Tworzenie i usuwanie niestandardowych dzienników zdarzeń](/previous-versions/visualstudio/visual-studio-2008/49dwckkz(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="42153-110">[How to: Create and Remove Custom Event Logs](/previous-versions/visualstudio/visual-studio-2008/49dwckkz(v=vs.90))</span></span>
