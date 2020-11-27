---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: a8aa5e600789df1b64a8a3f1a6355aaae6a6cf4b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294433"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="bdbd4-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="bdbd4-102">System.ServiceModel.MessageClosedAgain</span></span>

<span data-ttu-id="bdbd4-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="bdbd4-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="bdbd4-104">Opis</span><span class="sxs-lookup"><span data-stu-id="bdbd4-104">Description</span></span>  

 <span data-ttu-id="bdbd4-105">Komunikat został zamknięty ponownie.</span><span class="sxs-lookup"><span data-stu-id="bdbd4-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="bdbd4-106">Komunikat powinien być zamknięty tylko raz.</span><span class="sxs-lookup"><span data-stu-id="bdbd4-106">A message should be closed only once.</span></span> <span data-ttu-id="bdbd4-107">Jeśli ślad jest emitowany w kodzie rozszerzenia użytkownika, oznacza to, że kod rozszerzenia użytkownika zamyka komunikat, który został już zamknięty.</span><span class="sxs-lookup"><span data-stu-id="bdbd4-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="bdbd4-108">Jeśli ślad jest emitowany za pomocą kodu produktu, oznacza to, że kod rozszerzenia użytkownika może potencjalnie zamknąć komunikat zbyt wcześnie.</span><span class="sxs-lookup"><span data-stu-id="bdbd4-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdbd4-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bdbd4-109">See also</span></span>

- [<span data-ttu-id="bdbd4-110">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="bdbd4-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="bdbd4-111">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="bdbd4-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="bdbd4-112">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="bdbd4-112">Administration and Diagnostics</span></span>](../index.md)
