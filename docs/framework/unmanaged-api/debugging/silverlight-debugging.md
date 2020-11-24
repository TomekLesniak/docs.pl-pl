---
title: Silverlight — debugowanie
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
ms.openlocfilehash: 49f026b8e1a3dd78a62091e77a5aba0c9a2e09d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671840"
---
# <a name="silverlight-debugging"></a><span data-ttu-id="f2258-102">Silverlight — debugowanie</span><span class="sxs-lookup"><span data-stu-id="f2258-102">Silverlight Debugging</span></span>

<span data-ttu-id="f2258-103">Tematy w tej sekcji opisują środowisko i interfejsy, które zapewnia środowisko uruchomieniowe języka wspólnego (CLR) do obsługi debugowania aplikacji opartych na technologii Silverlight, które są uruchomione w systemie operacyjnym Windows lub na platformie Macintosh.</span><span class="sxs-lookup"><span data-stu-id="f2258-103">The topics in this section describe the environment and interfaces that the common language runtime (CLR) provides to support debugging Silverlight-based applications that are running on the Windows operating system, or on the Macintosh platform.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f2258-104">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="f2258-104">In This Section</span></span>  

 [<span data-ttu-id="f2258-105">EnumerateCLRs — Funkcja</span><span class="sxs-lookup"><span data-stu-id="f2258-105">EnumerateCLRs Function</span></span>](enumerateclrs-function.md)  
 <span data-ttu-id="f2258-106">Zapewnia mechanizm wyliczania CLRs w procesie.</span><span class="sxs-lookup"><span data-stu-id="f2258-106">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
 [<span data-ttu-id="f2258-107">CloseCLREnumeration — Funkcja</span><span class="sxs-lookup"><span data-stu-id="f2258-107">CloseCLREnumeration Function</span></span>](closeclrenumeration-function.md)  
 <span data-ttu-id="f2258-108">Zamyka wszystkie prawidłowe zdarzenia Kontynuuj środowiska CLR znajdujące się w tablicy dojść zwracanych przez [funkcję EnumerateCLRs —](enumerateclrs-function.md)i zwalnia pamięć dla tablic uchwytów i ścieżek ciągów.</span><span class="sxs-lookup"><span data-stu-id="f2258-108">Closes any valid CLR continue-startup events located in an array of handles returned by the [EnumerateCLRs Function](enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
 [<span data-ttu-id="f2258-109">CreateCoreClrDebugTarget — Funkcja</span><span class="sxs-lookup"><span data-stu-id="f2258-109">CreateCoreClrDebugTarget Function</span></span>](createcoreclrdebugtarget-function.md)  
 <span data-ttu-id="f2258-110">Tworzy połączenie ze zdalnym elementem docelowym na potrzeby wyliczenia procesu i środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="f2258-110">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="f2258-111">CreateCordbObject — Funkcja</span><span class="sxs-lookup"><span data-stu-id="f2258-111">CreateCordbObject Function</span></span>](createcordbobject-function.md)  
 <span data-ttu-id="f2258-112">Tworzy interfejs debugera, który zapewnia funkcję tworzenia wystąpienia zarządzanej sesji debugowania w procesie zdalnym.</span><span class="sxs-lookup"><span data-stu-id="f2258-112">Creates a debugger interface that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
 [<span data-ttu-id="f2258-113">CreateVersionStringFromModule — Funkcja</span><span class="sxs-lookup"><span data-stu-id="f2258-113">CreateVersionStringFromModule Function</span></span>](createversionstringfrommodule-function.md)  
 <span data-ttu-id="f2258-114">Tworzy ciąg wersji ze ścieżki CLR w procesie docelowym.</span><span class="sxs-lookup"><span data-stu-id="f2258-114">Creates a version string from a CLR path in a target process.</span></span>  
  
 [<span data-ttu-id="f2258-115">CreateDebuggingInterfaceFromVersion — Funkcja</span><span class="sxs-lookup"><span data-stu-id="f2258-115">CreateDebuggingInterfaceFromVersion Function</span></span>](createdebugginginterfacefromversion-function-for-silverlight.md)  
 <span data-ttu-id="f2258-116">Akceptuje ciąg wersji środowiska CLR zwrócony z funkcji [funkcji CreateVersionStringFromModule —](createversionstringfrommodule-function.md)i zwraca odpowiedni interfejs debugera.</span><span class="sxs-lookup"><span data-stu-id="f2258-116">Accepts a CLR version string returned from [CreateVersionStringFromModule Function](createversionstringfrommodule-function.md)function, and returns a corresponding debugger interface.</span></span>  
  
 [<span data-ttu-id="f2258-117">CoreClrDebugProcInfo — Struktura</span><span class="sxs-lookup"><span data-stu-id="f2258-117">CoreClrDebugProcInfo Structure</span></span>](coreclrdebugprocinfo-structure.md)  
 <span data-ttu-id="f2258-118">Reprezentuje proces, który jest uruchomiony na komputerze zdalnym.</span><span class="sxs-lookup"><span data-stu-id="f2258-118">Represents a process that is running on a remote machine.</span></span>  
  
 [<span data-ttu-id="f2258-119">CoreClrDebugRuntimeInfo — Struktura</span><span class="sxs-lookup"><span data-stu-id="f2258-119">CoreClrDebugRuntimeInfo Structure</span></span>](coreclrdebugruntimeinfo-structure.md)  
 <span data-ttu-id="f2258-120">Reprezentuje wystąpienie CLR, które jest ładowane w procesie na maszynie zdalnej.</span><span class="sxs-lookup"><span data-stu-id="f2258-120">Represents a CLR instance that is loaded in a process on a remote machine.</span></span>  
  
 [<span data-ttu-id="f2258-121">GetStartupNotificationEvent — Funkcja</span><span class="sxs-lookup"><span data-stu-id="f2258-121">GetStartupNotificationEvent Function</span></span>](getstartupnotificationevent-function.md)  
 <span data-ttu-id="f2258-122">Tworzy lub otwiera dojście zdarzenia, które będzie sygnalizowane przez środowisko uruchomieniowe języka wspólnego (CLR) ładowane w określonym procesie docelowym.</span><span class="sxs-lookup"><span data-stu-id="f2258-122">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
 [<span data-ttu-id="f2258-123">ICoreClrDebugTarget — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f2258-123">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)  
 <span data-ttu-id="f2258-124">Tworzy połączenie ze zdalnym elementem docelowym na potrzeby wyliczenia procesu i środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="f2258-124">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="f2258-125">InitDbgTransportManager — Funkcja</span><span class="sxs-lookup"><span data-stu-id="f2258-125">InitDbgTransportManager Function</span></span>](initdbgtransportmanager-function.md)  
 <span data-ttu-id="f2258-126">Inicjuje menedżera transportu, aby połączyć się ze zdalnym elementem docelowym na potrzeby wyliczenia procesu i środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="f2258-126">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="f2258-127">ShutdownDbgTransportManager — Funkcja</span><span class="sxs-lookup"><span data-stu-id="f2258-127">ShutdownDbgTransportManager Function</span></span>](shutdowndbgtransportmanager-function.md)  
 <span data-ttu-id="f2258-128">Zamyka menedżera transportu dla połączenia ze zdalnym komputerem docelowym.</span><span class="sxs-lookup"><span data-stu-id="f2258-128">Shuts down the transport manager for a connection to a remote target machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2258-129">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f2258-129">See also</span></span>

- [<span data-ttu-id="f2258-130">Klasy coclass debugowania</span><span class="sxs-lookup"><span data-stu-id="f2258-130">Debugging Coclasses</span></span>](debugging-coclasses.md)
- [<span data-ttu-id="f2258-131">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="f2258-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f2258-132">Debugowanie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="f2258-132">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
- [<span data-ttu-id="f2258-133">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="f2258-133">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="f2258-134">Struktury debugowania</span><span class="sxs-lookup"><span data-stu-id="f2258-134">Debugging Structures</span></span>](debugging-structures.md)
