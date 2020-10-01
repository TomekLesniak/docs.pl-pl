---
title: 'Instrukcje: Instalowanie i odinstalowywanie usług systemu Windows'
description: Zobacz Instalowanie i odinstalowywanie usług systemu Windows. Jeśli tworzysz usługę systemu Windows przy użyciu platformy .NET, możesz użyć InstallUtil.exe lub programu PowerShell.
ms.date: 02/05/2019
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, apps, Windows services
- installation, Windows services
- uninstalling Windows services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
ms.openlocfilehash: 6b7cfd8b241df4fe01c9c2a08888c88a1c749d13
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609684"
---
# <a name="how-to-install-and-uninstall-windows-services"></a><span data-ttu-id="538ca-104">Instrukcje: Instalowanie i odinstalowywanie usług systemu Windows</span><span class="sxs-lookup"><span data-stu-id="538ca-104">How to: Install and uninstall Windows services</span></span>

<span data-ttu-id="538ca-105">Jeśli tworzysz usługę systemu Windows przy użyciu .NET Framework, możesz szybko zainstalować swoją aplikację usługi przy użyciu narzędzia wiersza polecenia [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) lub [programu PowerShell](/powershell/scripting/overview).</span><span class="sxs-lookup"><span data-stu-id="538ca-105">If you’re developing a Windows service with the .NET Framework, you can quickly install your service app by using the [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) command-line utility or [PowerShell](/powershell/scripting/overview).</span></span> <span data-ttu-id="538ca-106">Deweloperzy, którzy chcą zwolnić usługę systemu Windows, którą użytkownicy mogą instalować i odinstalowywać, mogą korzystać z bezpłatnego zestawu narzędzi [WIX](https://wixtoolset.org/) lub komercyjnego narzędzia, takiego jak [Advanced Installer](https://www.advancedinstaller.com/), [InstallShield](https://www.revenera.com/install/products/installshield.html)lub innych.</span><span class="sxs-lookup"><span data-stu-id="538ca-106">Developers who want to release a Windows service that users can install and uninstall can use the free [WiX Toolset](https://wixtoolset.org/) or commercial tools like [Advanced Installer](https://www.advancedinstaller.com/), [InstallShield](https://www.revenera.com/install/products/installshield.html), or others.</span></span> <span data-ttu-id="538ca-107">Aby uzyskać więcej informacji, zobacz [Tworzenie pakietu Instalatora (Windows Desktop)](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span><span class="sxs-lookup"><span data-stu-id="538ca-107">For more information, see [Create an installer package (Windows desktop)](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>

> [!WARNING]
> <span data-ttu-id="538ca-108">Jeśli chcesz odinstalować usługę z komputera, nie wykonuj kroków opisanych w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="538ca-108">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="538ca-109">Zamiast tego Sprawdź, który program lub pakiet oprogramowania zainstalował usługę, a następnie wybierz pozycję **aplikacje** w ustawieniach, aby odinstalować ten program.</span><span class="sxs-lookup"><span data-stu-id="538ca-109">Instead, find out which program or software package installed the service, and then choose **Apps** in Settings to uninstall that program.</span></span> <span data-ttu-id="538ca-110">Należy zauważyć, że wiele usług jest integralną częścią systemu Windows; po ich usunięciu może wystąpić niestabilność systemu.</span><span class="sxs-lookup"><span data-stu-id="538ca-110">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>

<span data-ttu-id="538ca-111">Aby wykonać kroki opisane w tym artykule, należy najpierw dodać Instalatora usługi do usługi systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="538ca-111">To use the steps in this article, you first need to add a service installer to your Windows service.</span></span> <span data-ttu-id="538ca-112">Aby uzyskać więcej informacji, zobacz [Przewodnik: Tworzenie aplikacji usługi systemu Windows](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="538ca-112">For more information, see [Walkthrough: Creating a Windows service app](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>

<span data-ttu-id="538ca-113">Nie można uruchamiać projektów usług systemu Windows bezpośrednio ze środowiska programistycznego programu Visual Studio, naciskając klawisz F5.</span><span class="sxs-lookup"><span data-stu-id="538ca-113">You can't run Windows service projects directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="538ca-114">Aby można było uruchomić projekt, należy zainstalować usługę w projekcie.</span><span class="sxs-lookup"><span data-stu-id="538ca-114">Before you can run the project, you must install the service in the project.</span></span>

> [!TIP]
> <span data-ttu-id="538ca-115">Możesz użyć **Eksplorator serwera** , aby sprawdzić, czy usługa została zainstalowana lub odinstalowana.</span><span class="sxs-lookup"><span data-stu-id="538ca-115">You can use **Server Explorer** to verify that you've installed or uninstalled your service.</span></span> <span data-ttu-id="538ca-116">Aby uzyskać więcej informacji, zobacz [jak używać Eksplorator serwera w programie Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="538ca-116">For more information, see [How to use Server Explorer in Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span></span>

### <a name="install-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="538ca-117">Ręczne instalowanie usługi przy użyciu narzędzia InstallUtil.exe</span><span class="sxs-lookup"><span data-stu-id="538ca-117">Install your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="538ca-118">Z menu **Start** wybierz katalog \*\*programu Visual Studio \<*version*> \*\* , a następnie wybierz opcję \*\*wiersz polecenia dla deweloperów dla programu \<*version*> vs \*\*.</span><span class="sxs-lookup"><span data-stu-id="538ca-118">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="538ca-119">Zostanie wyświetlony wiersz polecenia dla deweloperów dla programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="538ca-119">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="538ca-120">Uzyskaj dostęp do katalogu, w którym znajduje się skompilowany plik wykonywalny projektu.</span><span class="sxs-lookup"><span data-stu-id="538ca-120">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="538ca-121">Uruchom *InstallUtil.exe* z wiersza polecenia z plikiem wykonywalnym projektu jako parametrem:</span><span class="sxs-lookup"><span data-stu-id="538ca-121">Run *InstallUtil.exe* from the command prompt with your project's executable as a parameter:</span></span>

    ```console
    installutil <yourproject>.exe
    ```

     <span data-ttu-id="538ca-122">Jeśli używasz wiersz polecenia dla deweloperów dla programu Visual Studio, *InstallUtil.exe* powinna znajdować się na ścieżce systemowej.</span><span class="sxs-lookup"><span data-stu-id="538ca-122">If you’re using the Developer Command Prompt for Visual Studio, *InstallUtil.exe* should be on the system path.</span></span> <span data-ttu-id="538ca-123">W przeciwnym razie możesz dodać go do ścieżki lub użyć w pełni kwalifikowanej ścieżki, aby wywołać ją.</span><span class="sxs-lookup"><span data-stu-id="538ca-123">Otherwise, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="538ca-124">To narzędzie jest instalowane z .NET Framework w \*%windir%\Microsoft.NET\Framework [64] \\<framework_version \> \*.</span><span class="sxs-lookup"><span data-stu-id="538ca-124">This tool is installed with the .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<framework_version\>*.</span></span>

     <span data-ttu-id="538ca-125">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="538ca-125">For example:</span></span>
     - <span data-ttu-id="538ca-126">W przypadku 32-bitowej wersji .NET Framework 4 lub 4,5 lub nowszej, jeśli katalog instalacyjny systemu Windows to *C:\Windows*, domyślną ścieżką jest *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="538ca-126">For the 32-bit version of the .NET Framework 4 or 4.5 and later, if your Windows installation directory is *C:\Windows*, the default path is *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>
     - <span data-ttu-id="538ca-127">W przypadku 64-bitowej wersji .NET Framework 4 lub 4,5 lub nowszej ścieżka domyślna to *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="538ca-127">For the 64-bit version of the .NET Framework 4 or 4.5 and later, the default path is *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>

### <a name="uninstall-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="538ca-128">Ręczne odinstalowywanie usługi przy użyciu narzędzia InstallUtil.exe</span><span class="sxs-lookup"><span data-stu-id="538ca-128">Uninstall your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="538ca-129">Z menu **Start** wybierz katalog \*\*programu Visual Studio \<*version*> \*\* , a następnie wybierz opcję \*\*wiersz polecenia dla deweloperów dla programu \<*version*> vs \*\*.</span><span class="sxs-lookup"><span data-stu-id="538ca-129">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="538ca-130">Zostanie wyświetlony wiersz polecenia dla deweloperów dla programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="538ca-130">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="538ca-131">Uruchom *InstallUtil.exe* z wiersza polecenia z danymi wyjściowymi projektu jako parametr:</span><span class="sxs-lookup"><span data-stu-id="538ca-131">Run *InstallUtil.exe* from the command prompt with your project's output as a parameter:</span></span>

    ```console
    installutil /u <yourproject>.exe
    ```

3. <span data-ttu-id="538ca-132">Po usunięciu pliku wykonywalnego usługi może być on nadal obecny w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="538ca-132">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="538ca-133">W takim przypadku należy użyć polecenia [SC Delete](/windows-server/administration/windows-commands/sc-delete) , aby usunąć wpis usługi z rejestru.</span><span class="sxs-lookup"><span data-stu-id="538ca-133">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

### <a name="install-your-service-manually-using-powershell"></a><span data-ttu-id="538ca-134">Ręczne instalowanie usługi przy użyciu programu PowerShell</span><span class="sxs-lookup"><span data-stu-id="538ca-134">Install your service manually using PowerShell</span></span>

1. <span data-ttu-id="538ca-135">Z menu **Start** wybierz pozycję katalog programu **Windows PowerShell** , a następnie wybierz pozycję **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="538ca-135">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="538ca-136">Uzyskaj dostęp do katalogu, w którym znajduje się skompilowany plik wykonywalny projektu.</span><span class="sxs-lookup"><span data-stu-id="538ca-136">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="538ca-137">Uruchom polecenie cmdlet [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) z danymi wyjściowymi projektu i nazwą usługi jako parametry:</span><span class="sxs-lookup"><span data-stu-id="538ca-137">Run the [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) cmdlet with the with your project's output and a service name as parameters:</span></span>

    ```powershell
    New-Service -Name "YourServiceName" -BinaryPathName <yourproject>.exe
    ```

### <a name="uninstall-your-service-manually-using-powershell"></a><span data-ttu-id="538ca-138">Ręczne odinstalowywanie usługi przy użyciu programu PowerShell</span><span class="sxs-lookup"><span data-stu-id="538ca-138">Uninstall your service manually using PowerShell</span></span>

1. <span data-ttu-id="538ca-139">Z menu **Start** wybierz pozycję katalog programu **Windows PowerShell** , a następnie wybierz pozycję **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="538ca-139">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="538ca-140">Uruchom polecenie cmdlet [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) z nazwą usługi jako parametr:</span><span class="sxs-lookup"><span data-stu-id="538ca-140">Run the [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) cmdlet with the name of your service as parameter:</span></span>

    ```powershell
    Remove-Service -Name "YourServiceName"
    ```

3. <span data-ttu-id="538ca-141">Po usunięciu pliku wykonywalnego usługi może być on nadal obecny w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="538ca-141">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="538ca-142">W takim przypadku należy użyć polecenia [SC Delete](/windows-server/administration/windows-commands/sc-delete) , aby usunąć wpis usługi z rejestru.</span><span class="sxs-lookup"><span data-stu-id="538ca-142">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

    ```powershell
    sc.exe delete "YourServiceName"
    ```

## <a name="see-also"></a><span data-ttu-id="538ca-143">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="538ca-143">See also</span></span>

- [<span data-ttu-id="538ca-144">Wprowadzenie do aplikacji usług systemu Windows</span><span class="sxs-lookup"><span data-stu-id="538ca-144">Introduction to Windows service applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="538ca-145">Instrukcje: tworzenie usług systemu Windows</span><span class="sxs-lookup"><span data-stu-id="538ca-145">How to: Create Windows services</span></span>](how-to-create-windows-services.md)
- [<span data-ttu-id="538ca-146">Instrukcje: Dodawanie instalatorów do aplikacji usługi</span><span class="sxs-lookup"><span data-stu-id="538ca-146">How to: Add installers to your service application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="538ca-147">Installutil.exe (Narzędzie instalatora)</span><span class="sxs-lookup"><span data-stu-id="538ca-147">Installutil.exe (Installer tool)</span></span>](../tools/installutil-exe-installer-tool.md)
