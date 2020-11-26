---
description: -platform (opcje kompilatora C#)
title: -platform (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /platform
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
ms.openlocfilehash: 3fdb030dfc141b011f5faa827a4e4bb45ae38d19
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "89466017"
---
# <a name="-platform-c-compiler-options"></a><span data-ttu-id="93adf-103">-platform (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="93adf-103">-platform (C# Compiler Options)</span></span>

<span data-ttu-id="93adf-104">Określa, która wersja środowiska uruchomieniowego języka wspólnego (CLR) może uruchomić zestaw.</span><span class="sxs-lookup"><span data-stu-id="93adf-104">Specifies which version of the Common Language Runtime (CLR) can run the assembly.</span></span>

## <a name="syntax"></a><span data-ttu-id="93adf-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="93adf-105">Syntax</span></span>

```console
-platform:string
```

## <a name="parameters"></a><span data-ttu-id="93adf-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="93adf-106">Parameters</span></span>

`string` \
<span data-ttu-id="93adf-107">AnyCPU (domyślnie), anycpu32bitpreferred, ARM, x64, x86 lub Itanium.</span><span class="sxs-lookup"><span data-stu-id="93adf-107">anycpu (default), anycpu32bitpreferred, ARM, x64, x86, or Itanium.</span></span>

## <a name="remarks"></a><span data-ttu-id="93adf-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="93adf-108">Remarks</span></span>

- <span data-ttu-id="93adf-109">**AnyCPU** (domyślnie) kompiluje zestaw do uruchomienia na dowolnej platformie.</span><span class="sxs-lookup"><span data-stu-id="93adf-109">**anycpu** (default) compiles your assembly to run on any platform.</span></span> <span data-ttu-id="93adf-110">Aplikacja działa jako proces 64-bitowy, gdy jest to możliwe, i wraca do 32-bitowej, gdy dostępny jest tylko ten tryb.</span><span class="sxs-lookup"><span data-stu-id="93adf-110">Your application runs as a 64-bit process whenever possible and falls back to 32-bit when only that mode is available.</span></span>

- <span data-ttu-id="93adf-111">**anycpu32bitpreferred** kompiluje zestaw do uruchamiania na dowolnej platformie.</span><span class="sxs-lookup"><span data-stu-id="93adf-111">**anycpu32bitpreferred** compiles your assembly to run on any platform.</span></span> <span data-ttu-id="93adf-112">Aplikacja działa w trybie 32-bitowym w systemach, które obsługują zarówno aplikacje 64-bitowe, jak i 32-bitowe.</span><span class="sxs-lookup"><span data-stu-id="93adf-112">Your application runs in 32-bit mode on systems that support both 64-bit and 32-bit applications.</span></span> <span data-ttu-id="93adf-113">Tę opcję można określić tylko dla projektów przeznaczonych dla .NET Framework 4,5 lub nowszych.</span><span class="sxs-lookup"><span data-stu-id="93adf-113">You can specify this option only for projects that target .NET Framework 4.5 or later.</span></span>

- <span data-ttu-id="93adf-114">**ARM** kompiluje zestaw do uruchomienia na komputerze z procesorem Advanced RISC Machine (ARM).</span><span class="sxs-lookup"><span data-stu-id="93adf-114">**ARM** compiles your assembly to run on a computer that has an Advanced RISC Machine (ARM) processor.</span></span>

- <span data-ttu-id="93adf-115">**Arm64** kompiluje zestaw do uruchomienia przez 64-bitowe środowisko CLR na komputerze z procesorem Advanced RISC Machine (ARM), który obsługuje zestaw instrukcji A64.</span><span class="sxs-lookup"><span data-stu-id="93adf-115">**ARM64** compiles your assembly to run by the 64-bit CLR on a computer that has an Advanced RISC Machine (ARM) processor that supports the A64 instruction set.</span></span>

- <span data-ttu-id="93adf-116">**x64** kompiluje zestaw do uruchomienia przez 64-bitowe środowisko CLR na komputerze, który obsługuje zestaw instrukcji AMD64 lub EM64T.</span><span class="sxs-lookup"><span data-stu-id="93adf-116">**x64** compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>

- <span data-ttu-id="93adf-117">**x86** kompiluje zestaw do uruchomienia przez 32-bitowe środowisko CLR zgodne z architekturą x86.</span><span class="sxs-lookup"><span data-stu-id="93adf-117">**x86** compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>

- <span data-ttu-id="93adf-118">**Procesor Itanium** kompiluje zestaw do uruchomienia przez 64-bitowe środowisko CLR na komputerze z procesorem Itanium.</span><span class="sxs-lookup"><span data-stu-id="93adf-118">**Itanium** compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>

<span data-ttu-id="93adf-119">W 64-bitowym systemie operacyjnym Windows:</span><span class="sxs-lookup"><span data-stu-id="93adf-119">On a 64-bit Windows operating system:</span></span>

- <span data-ttu-id="93adf-120">Zestawy skompilowane przy użyciu **-platform: x86** wykonaj na 32-bitowym CLR uruchomionym w emulatorze WOW64.</span><span class="sxs-lookup"><span data-stu-id="93adf-120">Assemblies compiled with **-platform:x86** execute on the 32-bit CLR running under WOW64.</span></span>

- <span data-ttu-id="93adf-121">Biblioteka DLL skompilowana z użyciem **platformy: anycpu** jest wykonywana w tym samym środowisku CLR co proces, w którym jest załadowana.</span><span class="sxs-lookup"><span data-stu-id="93adf-121">A DLL compiled with the **-platform:anycpu** executes on the same CLR as the process into which it is loaded.</span></span>

- <span data-ttu-id="93adf-122">Pliki wykonywalne, które są kompilowane z **-platformą: anycpu** execute na 64-bitowym CLR.</span><span class="sxs-lookup"><span data-stu-id="93adf-122">Executables that are compiled with the **-platform:anycpu** execute on the 64-bit CLR.</span></span>

- <span data-ttu-id="93adf-123">Pliki wykonywalne skompilowane z **-platformą: anycpu32bitpreferred** execute na 32-bitowym CLR.</span><span class="sxs-lookup"><span data-stu-id="93adf-123">Executables compiled with **-platform:anycpu32bitpreferred** execute on the 32-bit CLR.</span></span>

<span data-ttu-id="93adf-124">Ustawienie **anycpu32bitpreferred** jest prawidłowe tylko dla pliku wykonywalnego (. EXE) i wymaga .NET Framework 4,5 lub nowszego.</span><span class="sxs-lookup"><span data-stu-id="93adf-124">The **anycpu32bitpreferred** setting is valid only for executable (.EXE) files, and it requires .NET Framework 4.5 or later.</span></span>

<span data-ttu-id="93adf-125">Aby uzyskać więcej informacji na temat tworzenia aplikacji do uruchamiania w systemie operacyjnym Windows 64-bitowym, zobacz [64-bitowe aplikacje](../../../framework/64-bit-apps.md).</span><span class="sxs-lookup"><span data-stu-id="93adf-125">For more information about developing an application to run on a Windows 64-bit operating system, see [64-bit Applications](../../../framework/64-bit-apps.md).</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="93adf-126">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="93adf-126">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="93adf-127">Otwórz stronę **Właściwości** dla projektu.</span><span class="sxs-lookup"><span data-stu-id="93adf-127">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="93adf-128">Kliknij stronę właściwości **kompilacja** .</span><span class="sxs-lookup"><span data-stu-id="93adf-128">Click the **Build** property page.</span></span>

3. <span data-ttu-id="93adf-129">Zmodyfikuj właściwość **Target platformy** i dla projektów, które są przeznaczone dla .NET Framework 4,5 lub nowszych, zaznacz lub wyczyść pole wyboru **Preferuj 32-bitowe** .</span><span class="sxs-lookup"><span data-stu-id="93adf-129">Modify the **Platform target** property and, for projects that target .NET Framework 4.5 or later, select or clear the **Prefer 32-bit** check box.</span></span>

> [!NOTE]
> <span data-ttu-id="93adf-130">`-platform` nie jest dostępny w środowisku programistycznym w programie Visual C# Express.</span><span class="sxs-lookup"><span data-stu-id="93adf-130">`-platform` is not available in the development environment in Visual C# Express.</span></span>

<span data-ttu-id="93adf-131">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A> .</span><span class="sxs-lookup"><span data-stu-id="93adf-131">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span></span>

## <a name="example"></a><span data-ttu-id="93adf-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="93adf-132">Example</span></span>

<span data-ttu-id="93adf-133">Poniższy przykład pokazuje, jak używać opcji **-platform** , aby określić, że aplikacja powinna być uruchamiana przez 64-bitowe środowisko CLR w 64-bitowym systemie operacyjnym Windows.</span><span class="sxs-lookup"><span data-stu-id="93adf-133">The following example shows how to use the **-platform** option to specify that the application should be run by the 64-bit CLR on a 64-bit Windows operating system.</span></span>

```console
csc -platform:anycpu filename.cs
```

## <a name="see-also"></a><span data-ttu-id="93adf-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="93adf-134">See also</span></span>

- [<span data-ttu-id="93adf-135">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="93adf-135">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="93adf-136">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="93adf-136">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
