---
description: 'Porada: ustawianie zmiennych środowiskowych dla wiersza polecenia programu Visual Studio'
title: 'Porada: ustawianie zmiennych środowiskowych dla wiersza polecenia programu Visual Studio'
ms.date: 12/20/2019
f1_keywords:
- cs.build.commandline
helpviewer_keywords:
- csc.exe, command-line builds
- Visual C#, command-line builds
- command-line compilers, Visual C#
- Vsvars32.bat
- builds [C#], command-line
- compilers, invoking from command line
- Vcvars32.bat file
- command line [C#], building from
- Visual C# compiler, enabling
- compiling source code, from command line
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
ms.openlocfilehash: b985c85e2fddce459ed68b3d07ba7d54a8b2d0a7
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "89125608"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="f945a-103">Porada: ustawianie zmiennych środowiskowych dla wiersza polecenia programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f945a-103">How to set environment variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="f945a-104">Plik VsDevCmd.bat ustawia odpowiednie zmienne środowiskowe, aby włączyć kompilacje w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="f945a-104">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span>

> [!NOTE]
> <span data-ttu-id="f945a-105">Program Visual Studio 2015 i wcześniejsze wersje używane VSVARS32.bat, a nie VsDevCmd.bat do tego samego celu.</span><span class="sxs-lookup"><span data-stu-id="f945a-105">Visual Studio 2015 and earlier versions used VSVARS32.bat, not VsDevCmd.bat for the same purpose.</span></span> <span data-ttu-id="f945a-106">Ten plik był przechowywany w folderze \Program Files\Microsoft Visual Studio w \\ *wersji*\Common7\Tools lub Program Files (x86) \Microsoft Visual Studio w \\ *wersji*\Common7\Tools.</span><span class="sxs-lookup"><span data-stu-id="f945a-106">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>

<span data-ttu-id="f945a-107">Jeśli bieżąca wersja programu Visual Studio jest zainstalowana na komputerze, który ma również starszą wersję programu Visual Studio, nie należy uruchamiać VsDevCmd.bat i VSVARS32.BAT z różnych wersji w tym samym oknie wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="f945a-107">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="f945a-108">Zamiast tego należy uruchomić polecenie dla każdej wersji w osobnym oknie.</span><span class="sxs-lookup"><span data-stu-id="f945a-108">Instead, you should run the command for each version in its own window.</span></span>

### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="f945a-109">Aby uruchomić VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="f945a-109">To run VsDevCmd.BAT</span></span>

1. <span data-ttu-id="f945a-110">Z menu **Start** Otwórz **wiersz polecenia dla deweloperów dla programu vs 2019**.</span><span class="sxs-lookup"><span data-stu-id="f945a-110">From the **Start** menu, open the **Developer Command Prompt for VS 2019**.</span></span>  <span data-ttu-id="f945a-111">Znajduje się w folderze **programu Visual Studio 2019** .</span><span class="sxs-lookup"><span data-stu-id="f945a-111">It's in the **Visual Studio 2019** folder.</span></span>

2. <span data-ttu-id="f945a-112">Przejdź do folderu \Program Files\Microsoft Visual Studio \\ *Version* \\ *Offer*\Common7\Tools lub \Program Files (x86) \Microsoft Visual Studio \\ *Version* \\ *Offer*\Common7\Tools subdirectory instalacji.</span><span class="sxs-lookup"><span data-stu-id="f945a-112">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="f945a-113">(*Wersja* *2019* dla bieżącej wersji.</span><span class="sxs-lookup"><span data-stu-id="f945a-113">(*Version* is *2019* for the current version.</span></span> <span data-ttu-id="f945a-114">*Oferta* jest jedną z *przedsiębiorstw*, *profesjonalistów* lub *społeczności*.)</span><span class="sxs-lookup"><span data-stu-id="f945a-114">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>

3. <span data-ttu-id="f945a-115">Uruchom VsDevCmd.bat, wpisując **VsDevCmd**.</span><span class="sxs-lookup"><span data-stu-id="f945a-115">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="f945a-116">VsDevCmd.bat może się różnić od komputera do komputera.</span><span class="sxs-lookup"><span data-stu-id="f945a-116">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="f945a-117">Nie zamieniaj brakującego lub uszkodzonego pliku VsDevCmd.bat na VsDevCmd.bat z innego komputera.</span><span class="sxs-lookup"><span data-stu-id="f945a-117">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="f945a-118">Zamiast tego ponownie uruchom Instalatora, aby zastąpić brakujący plik.</span><span class="sxs-lookup"><span data-stu-id="f945a-118">Instead, rerun setup to replace the missing file.</span></span>

### <a name="available-options-for-vsdevcmdbat"></a><span data-ttu-id="f945a-119">Dostępne opcje dla VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="f945a-119">Available options for VsDevCmd.BAT</span></span>

<span data-ttu-id="f945a-120">Aby wyświetlić dostępne opcje VsDevCmd.BAT, uruchom polecenie z `-help` opcją:</span><span class="sxs-lookup"><span data-stu-id="f945a-120">To see the available options for VsDevCmd.BAT, run the command with the `-help` option:</span></span>

```console
VsDevCmd.bat -help
```

## <a name="see-also"></a><span data-ttu-id="f945a-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f945a-121">See also</span></span>

- [<span data-ttu-id="f945a-122">Kompilacja za pomocą wiersza polecenia przy użyciu csc.exe</span><span class="sxs-lookup"><span data-stu-id="f945a-122">Command-line Building With csc.exe</span></span>](./command-line-building-with-csc-exe.md)
