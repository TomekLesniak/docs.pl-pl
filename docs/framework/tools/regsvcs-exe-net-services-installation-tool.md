---
title: Regsvcs.exe (Narzędzie instalacji usług .NET)
description: Użyj Regsvcs.exe, narzędzia instalacji usługi .NET Services. Załaduj i zarejestruj zestaw, Skonfiguruj usługi, które zostały dodane programowo do klasy i nie tylko.
ms.date: 03/30/2017
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
ms.openlocfilehash: 6d0090eda764113407e35a3bcec139f1c7cfb050
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517246"
---
# <a name="regsvcsexe-net-services-installation-tool"></a><span data-ttu-id="67414-104">Regsvcs.exe (Narzędzie instalacji usług .NET)</span><span class="sxs-lookup"><span data-stu-id="67414-104">Regsvcs.exe (.NET Services Installation Tool)</span></span>
<span data-ttu-id="67414-105">Narzędzie instalacji usług platformy .NET wykonuje następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="67414-105">The .NET Services Installation tool performs the following actions:</span></span>  
  
- <span data-ttu-id="67414-106">Ładuje i rejestruje zestawy.</span><span class="sxs-lookup"><span data-stu-id="67414-106">Loads and registers an assembly.</span></span>  
  
- <span data-ttu-id="67414-107">Generuje, rejestruje i instaluje biblioteki typów w określonej aplikacji COM+.</span><span class="sxs-lookup"><span data-stu-id="67414-107">Generates, registers, and installs a type library into a specified COM+ application.</span></span>  
  
- <span data-ttu-id="67414-108">Konfiguruje usługi, które zostały programowo dodane do klasy użytkownika.</span><span class="sxs-lookup"><span data-stu-id="67414-108">Configures services that you have added programmatically to your class.</span></span>  
  
 <span data-ttu-id="67414-109">Aby uruchomić narzędzie, użyj wiersz polecenia dla deweloperów dla programu Visual Studio (lub wiersza polecenia programu Visual Studio w systemie Windows 7).</span><span class="sxs-lookup"><span data-stu-id="67414-109">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="67414-110">Aby uzyskać więcej informacji, zobacz [wiersza polecenia](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="67414-110">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="67414-111">W wierszu polecenia wpisz następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="67414-111">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67414-112">Składnia</span><span class="sxs-lookup"><span data-stu-id="67414-112">Syntax</span></span>  
  
```console  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll
```  
  
## <a name="parameters"></a><span data-ttu-id="67414-113">Parametry</span><span class="sxs-lookup"><span data-stu-id="67414-113">Parameters</span></span>  
  
|<span data-ttu-id="67414-114">Argument</span><span class="sxs-lookup"><span data-stu-id="67414-114">Argument</span></span>|<span data-ttu-id="67414-115">Opis</span><span class="sxs-lookup"><span data-stu-id="67414-115">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="67414-116">*assemblyFile.dll*</span><span class="sxs-lookup"><span data-stu-id="67414-116">*assemblyFile.dll*</span></span>|<span data-ttu-id="67414-117">Plik zestawu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="67414-117">The source assembly file.</span></span> <span data-ttu-id="67414-118">Zestaw musi być podpisany za pomocą silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="67414-118">The assembly must be signed with a strong name.</span></span> <span data-ttu-id="67414-119">Aby uzyskać więcej informacji, zobacz [podpisywanie zestawu za pomocą silnej nazwy](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="67414-119">For more information, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span>|  
  
|<span data-ttu-id="67414-120">Opcja</span><span class="sxs-lookup"><span data-stu-id="67414-120">Option</span></span>|<span data-ttu-id="67414-121">Opis</span><span class="sxs-lookup"><span data-stu-id="67414-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="67414-122">**/Appdir:** *ścieżka*</span><span class="sxs-lookup"><span data-stu-id="67414-122">**/appdir:** *path*</span></span>|<span data-ttu-id="67414-123">Określa katalog główny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="67414-123">Specifies the root directory of the application.</span></span>|  
|<span data-ttu-id="67414-124">**/APPNAME:** *ApplicationName*</span><span class="sxs-lookup"><span data-stu-id="67414-124">**/appname:** *applicationName*</span></span>|<span data-ttu-id="67414-125">Określa nazwę aplikacji COM+, która ma zostać znaleziona lub utworzona.</span><span class="sxs-lookup"><span data-stu-id="67414-125">Specifies the name of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="67414-126">**/c**</span><span class="sxs-lookup"><span data-stu-id="67414-126">**/c**</span></span>|<span data-ttu-id="67414-127">Tworzy aplikację docelową.</span><span class="sxs-lookup"><span data-stu-id="67414-127">Creates the target application.</span></span>|  
|<span data-ttu-id="67414-128">**/componly**</span><span class="sxs-lookup"><span data-stu-id="67414-128">**/componly**</span></span>|<span data-ttu-id="67414-129">Konfiguruje tylko składniki; ignoruje metody i interfejsy.</span><span class="sxs-lookup"><span data-stu-id="67414-129">Configures components only; ignores methods and interfaces.</span></span>|  
|<span data-ttu-id="67414-130">**/exapp**</span><span class="sxs-lookup"><span data-stu-id="67414-130">**/exapp**</span></span>|<span data-ttu-id="67414-131">Określa, że narzędzie ma oczekiwać istniejącej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="67414-131">Specifies to the tool to expect an existing application.</span></span>|  
|<span data-ttu-id="67414-132">**/extlb**</span><span class="sxs-lookup"><span data-stu-id="67414-132">**/extlb**</span></span>|<span data-ttu-id="67414-133">Używa istniejącej biblioteki typów.</span><span class="sxs-lookup"><span data-stu-id="67414-133">Uses an existing type library.</span></span>|  
|<span data-ttu-id="67414-134">**/FC**</span><span class="sxs-lookup"><span data-stu-id="67414-134">**/fc**</span></span>|<span data-ttu-id="67414-135">Znajduje lub tworzy aplikację docelową.</span><span class="sxs-lookup"><span data-stu-id="67414-135">Finds or creates the target application.</span></span>|  
|<span data-ttu-id="67414-136">**/Help**</span><span class="sxs-lookup"><span data-stu-id="67414-136">**/help**</span></span>|<span data-ttu-id="67414-137">Wyświetla składnię polecenia i opcje narzędzia.</span><span class="sxs-lookup"><span data-stu-id="67414-137">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="67414-138">**/noreconfig**</span><span class="sxs-lookup"><span data-stu-id="67414-138">**/noreconfig**</span></span>|<span data-ttu-id="67414-139">Nie konfiguruje ponownie istniejącej aplikacji docelowej.</span><span class="sxs-lookup"><span data-stu-id="67414-139">Does not reconfigure an existing target application.</span></span>|  
|<span data-ttu-id="67414-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="67414-140">**/nologo**</span></span>|<span data-ttu-id="67414-141">Pomija wyświetlanie transparentu startowego firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="67414-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="67414-142">**/parName:** *Nazwa*</span><span class="sxs-lookup"><span data-stu-id="67414-142">**/parname:** *name*</span></span>|<span data-ttu-id="67414-143">Określa nazwę lub identyfikator aplikacji COM+, która ma zostać znaleziona lub utworzona.</span><span class="sxs-lookup"><span data-stu-id="67414-143">Specifies the name or id of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="67414-144">**/reconfig**</span><span class="sxs-lookup"><span data-stu-id="67414-144">**/reconfig**</span></span>|<span data-ttu-id="67414-145">Konfiguruje ponownie istniejącą aplikację docelową.</span><span class="sxs-lookup"><span data-stu-id="67414-145">Reconfigures an existing target application.</span></span> <span data-ttu-id="67414-146">Jest to opcja domyślna.</span><span class="sxs-lookup"><span data-stu-id="67414-146">This is the default.</span></span>|  
|<span data-ttu-id="67414-147">**/tlb:** *TypeLibraryFile*</span><span class="sxs-lookup"><span data-stu-id="67414-147">**/tlb:** *typelibraryfile*</span></span>|<span data-ttu-id="67414-148">Określa plik biblioteki typów do zainstalowania.</span><span class="sxs-lookup"><span data-stu-id="67414-148">Specifies the type library file to install.</span></span>|  
|<span data-ttu-id="67414-149">**Określ**</span><span class="sxs-lookup"><span data-stu-id="67414-149">**/u**</span></span>|<span data-ttu-id="67414-150">Odinstalowuje aplikację docelową.</span><span class="sxs-lookup"><span data-stu-id="67414-150">Uninstalls the target application.</span></span>|  
|<span data-ttu-id="67414-151">**spowoduje**</span><span class="sxs-lookup"><span data-stu-id="67414-151">**/quiet**</span></span>|<span data-ttu-id="67414-152">Określa tryb cichy; pomija wyświetlanie logo i komunikatów o sukcesie.</span><span class="sxs-lookup"><span data-stu-id="67414-152">Specifies quiet mode; suppresses the logo and success message display.</span></span>|  
|<span data-ttu-id="67414-153">**/?**</span><span class="sxs-lookup"><span data-stu-id="67414-153">**/?**</span></span>|<span data-ttu-id="67414-154">Wyświetla składnię polecenia i opcje narzędzia.</span><span class="sxs-lookup"><span data-stu-id="67414-154">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67414-155">Uwagi</span><span class="sxs-lookup"><span data-stu-id="67414-155">Remarks</span></span>  
 <span data-ttu-id="67414-156">Regsvcs.exe wymaga pliku zestawu źródłowego określonego przez *assemblyFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="67414-156">Regsvcs.exe requires a source assembly file specified by *assemblyFile.dll*.</span></span> <span data-ttu-id="67414-157">Ten zestaw musi być podpisany za pomocą silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="67414-157">This assembly must be signed with a strong name.</span></span> <span data-ttu-id="67414-158">Aby uzyskać więcej informacji na temat podpisywania silnej nazwy, zobacz [podpisywanie zestawu za pomocą silnej nazwy](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="67414-158">For more information on strong name signing, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span> <span data-ttu-id="67414-159">Nazwy aplikacji docelowej i pliku biblioteki typów są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="67414-159">The names of the target application and the type library file are optional.</span></span> <span data-ttu-id="67414-160">Argument *ApplicationName* można wygenerować z pliku zestawu źródłowego i zostanie utworzony przez Regsvcs.exe, jeśli jeszcze nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="67414-160">The *applicationName* argument can be generated from the source assembly file and will be created by Regsvcs.exe, if it does not already exist.</span></span> <span data-ttu-id="67414-161">Argument *TypeLibraryFile* może określać nazwę biblioteki typów.</span><span class="sxs-lookup"><span data-stu-id="67414-161">The *typelibraryfile* argument can specify a type library name.</span></span> <span data-ttu-id="67414-162">Jeśli nie zostanie określona nazwa biblioteki typów, program Regsvcs.exe użyje nazwy zestawu jako wartości domyślnej.</span><span class="sxs-lookup"><span data-stu-id="67414-162">If you do not specify a type library name, Regsvcs.exe uses the assembly name as the default.</span></span>  
  
 <span data-ttu-id="67414-163">Gdy Regsvcs.exe rejestruje metody składnika, podlegają [wymaganiom](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) i [łącznym potrzebom](../misc/link-demands.md) dotyczącym tych metod.</span><span class="sxs-lookup"><span data-stu-id="67414-163">When Regsvcs.exe registers a component's methods, it is subject to the [demands](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) and [link demands](../misc/link-demands.md) on those methods.</span></span> <span data-ttu-id="67414-164">To narzędzie działa we w pełni zaufanym środowisku, więc większość żądań uprawnienia kończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="67414-164">Because the tool executes in a fully-trusted environment, most demands for a permission succeed.</span></span> <span data-ttu-id="67414-165">Jednak Regsvcs.exe nie może zarejestrować składników przy użyciu metod chronionych przez zapotrzebowanie lub żądanie linku dla <xref:System.Security.Permissions.StrongNameIdentityPermission> lub <xref:System.Security.Permissions.PublisherIdentityPermission> .</span><span class="sxs-lookup"><span data-stu-id="67414-165">However, Regsvcs.exe cannot register components with methods protected by a demand or link demand for the <xref:System.Security.Permissions.StrongNameIdentityPermission> or the <xref:System.Security.Permissions.PublisherIdentityPermission>.</span></span>  
  
 <span data-ttu-id="67414-166">Aby używać programu Regsvcs.exe, trzeba mieć uprawnienia administracyjne na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="67414-166">You must have administrative privileges on the local computer to use Regsvcs.exe.</span></span>  
  
 <span data-ttu-id="67414-167">Jeśli podczas wykonywania dowolnej z tych akcji w programie Regsvcs.exe wystąpi błąd, zostaną wyświetlone odpowiednie komunikaty o błędach.</span><span class="sxs-lookup"><span data-stu-id="67414-167">If Regsvcs.exe fails while performing any of these actions, it displays corresponding error messages.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="67414-168">Przykłady</span><span class="sxs-lookup"><span data-stu-id="67414-168">Examples</span></span>  
 <span data-ttu-id="67414-169">Następujące polecenie dodaje wszystkie klasy publiczne zawarte w `myTest.dll` do `myTargetApp` (istniejąca aplikacja com+) i tworzy `myTest.tlb` bibliotekę typów.</span><span class="sxs-lookup"><span data-stu-id="67414-169">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `myTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 <span data-ttu-id="67414-170">Następujące polecenie dodaje wszystkie klasy publiczne zawarte w `myTest.dll` do `myTargetApp` (istniejąca aplikacja com+) i tworzy `newTest.tlb` bibliotekę typów.</span><span class="sxs-lookup"><span data-stu-id="67414-170">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `newTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="67414-171">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="67414-171">See also</span></span>

- [<span data-ttu-id="67414-172">Narzędzia</span><span class="sxs-lookup"><span data-stu-id="67414-172">Tools</span></span>](index.md)
- [<span data-ttu-id="67414-173">Instrukcje: podpisywanie zestawu silną nazwą</span><span class="sxs-lookup"><span data-stu-id="67414-173">How to: Sign an Assembly with a Strong Name</span></span>](../../standard/assembly/sign-strong-name.md)
- [<span data-ttu-id="67414-174">Wiersze poleceń</span><span class="sxs-lookup"><span data-stu-id="67414-174">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
