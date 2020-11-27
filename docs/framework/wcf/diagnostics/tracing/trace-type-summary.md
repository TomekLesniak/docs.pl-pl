---
title: Podsumowanie typu śledzenia
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: e8d222d6f093f5db3bd620194bfde7edd4b998a8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259248"
---
# <a name="trace-type-summary"></a><span data-ttu-id="db7b8-102">Podsumowanie typu śledzenia</span><span class="sxs-lookup"><span data-stu-id="db7b8-102">Trace Type Summary</span></span>

<span data-ttu-id="db7b8-103">[Poziomy źródła](xref:System.Diagnostics.SourceLevels) definiują różne poziomy śledzenia: krytyczny, błąd, ostrzeżenie, informacje i pełne, a także zawiera opis `ActivityTracing` flagi, która przełącza dane wyjściowe granicy śledzenia i zdarzeń transferu aktywności.</span><span class="sxs-lookup"><span data-stu-id="db7b8-103">[Source Levels](xref:System.Diagnostics.SourceLevels) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides a description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="db7b8-104">Możesz również przejrzeć <xref:System.Diagnostics.TraceEventType> typy śladów, z których mogą być emitowane <xref:System.Diagnostics> .</span><span class="sxs-lookup"><span data-stu-id="db7b8-104">You can also review <xref:System.Diagnostics.TraceEventType> for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="db7b8-105">W poniższej tabeli przedstawiono najważniejsze elementy.</span><span class="sxs-lookup"><span data-stu-id="db7b8-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="db7b8-106">Typ śledzenia</span><span class="sxs-lookup"><span data-stu-id="db7b8-106">Trace Type</span></span>|<span data-ttu-id="db7b8-107">Opis</span><span class="sxs-lookup"><span data-stu-id="db7b8-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="db7b8-108">Krytyczny</span><span class="sxs-lookup"><span data-stu-id="db7b8-108">Critical</span></span>|<span data-ttu-id="db7b8-109">Błąd krytyczny lub awaria aplikacji.</span><span class="sxs-lookup"><span data-stu-id="db7b8-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="db7b8-110">Błąd</span><span class="sxs-lookup"><span data-stu-id="db7b8-110">Error</span></span>|<span data-ttu-id="db7b8-111">Odwracalny błąd.</span><span class="sxs-lookup"><span data-stu-id="db7b8-111">Recoverable error.</span></span>|  
|<span data-ttu-id="db7b8-112">Ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="db7b8-112">Warning</span></span>|<span data-ttu-id="db7b8-113">Komunikat informacyjny.</span><span class="sxs-lookup"><span data-stu-id="db7b8-113">Informational message.</span></span>|  
|<span data-ttu-id="db7b8-114">Informacje</span><span class="sxs-lookup"><span data-stu-id="db7b8-114">Information</span></span>|<span data-ttu-id="db7b8-115">Problem niekrytyczny.</span><span class="sxs-lookup"><span data-stu-id="db7b8-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="db7b8-116">Pełny</span><span class="sxs-lookup"><span data-stu-id="db7b8-116">Verbose</span></span>|<span data-ttu-id="db7b8-117">Śledzenie debugowania.</span><span class="sxs-lookup"><span data-stu-id="db7b8-117">Debugging trace.</span></span>|  
|<span data-ttu-id="db7b8-118">Rozpocznij</span><span class="sxs-lookup"><span data-stu-id="db7b8-118">Start</span></span>|<span data-ttu-id="db7b8-119">Rozpoczynanie logicznej jednostki przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="db7b8-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="db7b8-120">Wstrzymanie</span><span class="sxs-lookup"><span data-stu-id="db7b8-120">Suspend</span></span>|<span data-ttu-id="db7b8-121">Zawieszenie logicznej jednostki przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="db7b8-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="db7b8-122">Wznów</span><span class="sxs-lookup"><span data-stu-id="db7b8-122">Resume</span></span>|<span data-ttu-id="db7b8-123">Wznawianie jednostki logicznej przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="db7b8-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="db7b8-124">Stop</span><span class="sxs-lookup"><span data-stu-id="db7b8-124">Stop</span></span>|<span data-ttu-id="db7b8-125">Zatrzymywanie logicznej jednostki przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="db7b8-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="db7b8-126">Transfer</span><span class="sxs-lookup"><span data-stu-id="db7b8-126">Transfer</span></span>|<span data-ttu-id="db7b8-127">Zmiana tożsamości korelacji.</span><span class="sxs-lookup"><span data-stu-id="db7b8-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="db7b8-128">Działanie jest zdefiniowane jako kombinacja powyższych typów śledzenia.</span><span class="sxs-lookup"><span data-stu-id="db7b8-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="db7b8-129">Poniżej znajduje się wyrażenie regularne, które definiuje idealne działanie w zakresie lokalnym (śledzenie źródła),</span><span class="sxs-lookup"><span data-stu-id="db7b8-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="db7b8-130">Oznacza to, że działanie musi spełniać następujące warunki.</span><span class="sxs-lookup"><span data-stu-id="db7b8-130">This means that an activity must satisfy the following conditions.</span></span>  
  
- <span data-ttu-id="db7b8-131">Musi on być odpowiednio uruchamiany i zatrzymany przez uruchamianie i zatrzymywanie śledzenia</span><span class="sxs-lookup"><span data-stu-id="db7b8-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
- <span data-ttu-id="db7b8-132">Musi mieć ślad transferu bezpośrednio poprzedzający śledzenie wstrzymania lub wznowienia</span><span class="sxs-lookup"><span data-stu-id="db7b8-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
- <span data-ttu-id="db7b8-133">Nie może mieć żadnych śladów między śladami zawieszenia i wznowienia, jeśli istnieją takie ślady</span><span class="sxs-lookup"><span data-stu-id="db7b8-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
- <span data-ttu-id="db7b8-134">Może to być dowolny i wiele ze śladów krytyczne/błąd/ostrzeżenie/informacja/pełny/transfer, o ile zostały spełnione poprzednie warunki</span><span class="sxs-lookup"><span data-stu-id="db7b8-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="db7b8-135">Poniżej znajduje się wyrażenie regularne, które definiuje idealne działanie w zakresie globalnym,</span><span class="sxs-lookup"><span data-stu-id="db7b8-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
`R+`  
  
 <span data-ttu-id="db7b8-136">za pomocą języka R jest wyrażeniem regularnym dla działania w zakresie lokalnym.</span><span class="sxs-lookup"><span data-stu-id="db7b8-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="db7b8-137">Spowoduje to przetłumaczenie na,</span><span class="sxs-lookup"><span data-stu-id="db7b8-137">This translates to,</span></span>  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
