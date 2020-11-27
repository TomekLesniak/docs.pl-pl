---
title: Storeadm.exe (Narzędzie wydzielonej pamięci masowej)
description: Przeczytaj informacje o Storeadm.exe, narzędziu do magazynowania izolowanego. To narzędzie wyświetla lub usuwa wszystkie istniejące magazyny dla bieżącego użytkownika.
ms.date: 03/30/2017
helpviewer_keywords:
- Storeadm.exe
- listing stores for current user
- Isolated Storage tool
- stores, current user
- removing stores
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
ms.openlocfilehash: 974f3c464ff686a486657d08e77c97299cc94732
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283838"
---
# <a name="storeadmexe-isolated-storage-tool"></a><span data-ttu-id="69693-104">Storeadm.exe (Narzędzie wydzielonej pamięci masowej)</span><span class="sxs-lookup"><span data-stu-id="69693-104">Storeadm.exe (Isolated Storage Tool)</span></span>

<span data-ttu-id="69693-105">Narzędzie Isolated Storage obsługujące izolowane magazyny wyświetla lub usuwa wszystkie istniejące magazyny bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="69693-105">The Isolated Storage tool lists or removes all existing stores for the current user.</span></span>  
  
 <span data-ttu-id="69693-106">To narzędzie jest instalowane automatycznie z programem Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="69693-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="69693-107">Aby uruchomić narzędzie, użyj wiersz polecenia dla deweloperów dla programu Visual Studio (lub wiersza polecenia programu Visual Studio w systemie Windows 7).</span><span class="sxs-lookup"><span data-stu-id="69693-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="69693-108">Aby uzyskać więcej informacji, zobacz [wiersza polecenia](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="69693-108">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="69693-109">W wierszu polecenia wpisz następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="69693-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69693-110">Składnia</span><span class="sxs-lookup"><span data-stu-id="69693-110">Syntax</span></span>  
  
```console  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
## <a name="parameters"></a><span data-ttu-id="69693-111">Parametry</span><span class="sxs-lookup"><span data-stu-id="69693-111">Parameters</span></span>  
  
|<span data-ttu-id="69693-112">Opcja</span><span class="sxs-lookup"><span data-stu-id="69693-112">Option</span></span>|<span data-ttu-id="69693-113">Opis</span><span class="sxs-lookup"><span data-stu-id="69693-113">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="69693-114">**/h**[**ELP**]</span><span class="sxs-lookup"><span data-stu-id="69693-114">**/h**[**elp**]</span></span>|<span data-ttu-id="69693-115">Wyświetla składnię polecenia i opcje narzędzia.</span><span class="sxs-lookup"><span data-stu-id="69693-115">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="69693-116">**/list**</span><span class="sxs-lookup"><span data-stu-id="69693-116">**/list**</span></span>|<span data-ttu-id="69693-117">Wyświetla wszystkie istniejące magazyny bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="69693-117">Displays all existing stores for the current user.</span></span> <span data-ttu-id="69693-118">W tym magazyny dla wszystkich aplikacji lub zespołów wykonanych przez tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="69693-118">This includes the stores for all applications or assemblies executed by this user.</span></span>|  
|<span data-ttu-id="69693-119">**/Machine**</span><span class="sxs-lookup"><span data-stu-id="69693-119">**/machine**</span></span>|<span data-ttu-id="69693-120">Wybiera magazyn komputera.</span><span class="sxs-lookup"><span data-stu-id="69693-120">Selects the machine store.</span></span> <span data-ttu-id="69693-121">Użyj tej opcji z opcją **/list** lub **/Remove** , aby określić, że akcja ma być stosowana do magazynu komputera.</span><span class="sxs-lookup"><span data-stu-id="69693-121">Use this option with the **/list** or **/remove** option to specify that the action should apply to the machine store.</span></span><br /><br /> <span data-ttu-id="69693-122">Nowość w programie .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="69693-122">New in the .NET Framework 2.0</span></span>|  
|<span data-ttu-id="69693-123">**spowoduje**</span><span class="sxs-lookup"><span data-stu-id="69693-123">**/quiet**</span></span>|<span data-ttu-id="69693-124">Określa tryb cichy; pomija informacyjne dane wyjściowe, tak aby były wyświetlane tylko komunikaty o błędach.</span><span class="sxs-lookup"><span data-stu-id="69693-124">Specifies quiet mode; suppresses informational output so that only error messages appear.</span></span>|  
|<span data-ttu-id="69693-125">**/Remove**</span><span class="sxs-lookup"><span data-stu-id="69693-125">**/remove**</span></span>|<span data-ttu-id="69693-126">Trwale usuwa wszystkie istniejące magazyny bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="69693-126">Permanently removes all existing stores for the current user.</span></span>|  
|<span data-ttu-id="69693-127">**/roaming**</span><span class="sxs-lookup"><span data-stu-id="69693-127">**/roaming**</span></span>|<span data-ttu-id="69693-128">Wybiera mobilny magazyn.</span><span class="sxs-lookup"><span data-stu-id="69693-128">Selects the roaming store.</span></span> <span data-ttu-id="69693-129">Użyj tej opcji z opcjami **/list** lub **/Remove** , aby określić, że akcja ma być stosowana do magazynu mobilnego.</span><span class="sxs-lookup"><span data-stu-id="69693-129">Use this option with the **/list** or **/remove** options to specify that the action should apply to the roaming store.</span></span>|  
|<span data-ttu-id="69693-130">**/?**</span><span class="sxs-lookup"><span data-stu-id="69693-130">**/?**</span></span>|<span data-ttu-id="69693-131">Wyświetla składnię polecenia i opcje narzędzia.</span><span class="sxs-lookup"><span data-stu-id="69693-131">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69693-132">Uwagi</span><span class="sxs-lookup"><span data-stu-id="69693-132">Remarks</span></span>  

 <span data-ttu-id="69693-133">Uruchamianie Storeadm.exe z wiersza polecenia bez określenia opcji wyświetla składnię i opcje narzędzia.</span><span class="sxs-lookup"><span data-stu-id="69693-133">Running Storeadm.exe from the command line without specifying any options displays the syntax and options for the tool.</span></span>  
  
 <span data-ttu-id="69693-134">Opcje **/list** i **/Remove** są zwykle używane pojedynczo. Jednak jeśli określono dwie lub więcej opcji, zostaną one wykonane w kolejności, w jakiej występują w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="69693-134">The **/list** and **/remove** options are typically used one at a time; however, if two or more options are specified they will be performed in the order in which they appear on the command line.</span></span>  
  
 <span data-ttu-id="69693-135">Aplikacje można zapisać do jednego z dwóch magazynów użytkownika lub do magazynu komputera:</span><span class="sxs-lookup"><span data-stu-id="69693-135">Applications have a choice of saving to one of two stores for a user or to the machine store:</span></span>  
  
- <span data-ttu-id="69693-136">Magazyn lokalny istnieje w lokalizacji, która nie jest przenoszona (w systemie Windows 2000 i nowszych) nawet wtedy, gdy dla użytkownika włączono funkcję mobilnego dostępu do danych użytkownika.</span><span class="sxs-lookup"><span data-stu-id="69693-136">The local store exists in a location that is guaranteed not to roam (on Windows 2000 and later) even if user data roaming is enabled for the user.</span></span>  
  
- <span data-ttu-id="69693-137">Magazyn mobilny istnieje w lokalizacji, która może przechować, ale tylko wtedy, gdy roaming jest włączony dla użytkownika za pośrednictwem administracji systemu Windows NT.</span><span class="sxs-lookup"><span data-stu-id="69693-137">The roaming store exists in a location that is able to roam, but can only do so if roaming is enabled for the user via Windows NT administration.</span></span>  
  
- <span data-ttu-id="69693-138">Magazyn komputera jest wspólny dla wszystkich użytkowników komputera i jest przechowywany we wspólnym katalogu na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="69693-138">The machine store is common to all users on a machine and is stored under a common directory on that machine.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="69693-139">Magazyn komputera jest nowy w programie .NET Framework w wersji 2.0.</span><span class="sxs-lookup"><span data-stu-id="69693-139">The machine store is new in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="69693-140">To, czy roaming jest faktycznie włączony dla użytkownika, nie wpływa na administrację Storeadm.exe.</span><span class="sxs-lookup"><span data-stu-id="69693-140">Whether roaming is actually enabled for the user does not affect the administration of Storeadm.exe.</span></span> <span data-ttu-id="69693-141">Uruchomienie narzędzia bez żadnych opcji zastosuje wszystkie akcje do magazynu lokalnego.</span><span class="sxs-lookup"><span data-stu-id="69693-141">Running the tool without any options applies all actions to the local store.</span></span> <span data-ttu-id="69693-142">Uruchomienie narzędzia z opcją **/roaming** dotyczy wszystkich akcji w sklepie, który ma możliwość przeroamingu.</span><span class="sxs-lookup"><span data-stu-id="69693-142">Running the tool with the **/roaming** option applies all actions to the store that is able to roam.</span></span> <span data-ttu-id="69693-143">Uruchomienie narzędzia z opcją **/Machine** powoduje zastosowanie wszystkich akcji do magazynu komputera.</span><span class="sxs-lookup"><span data-stu-id="69693-143">Running the tool with the **/machine** option applies all actions to the machine store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69693-144">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="69693-144">See also</span></span>

- [<span data-ttu-id="69693-145">Narzędzia</span><span class="sxs-lookup"><span data-stu-id="69693-145">Tools</span></span>](index.md)
- [<span data-ttu-id="69693-146">Magazyn izolowany</span><span class="sxs-lookup"><span data-stu-id="69693-146">Isolated Storage</span></span>](../../standard/io/isolated-storage.md)
- [<span data-ttu-id="69693-147">Wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="69693-147">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
