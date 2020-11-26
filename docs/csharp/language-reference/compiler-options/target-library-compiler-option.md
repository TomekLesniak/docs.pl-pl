---
description: '-target: Library (opcje kompilatora C#)'
title: '-target: Library (opcje kompilatora C#)'
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: 0f5b1e1bec8fd601bf111e1c2c64adf22d0a064e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193728"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="87261-103">-target: Library (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="87261-103">-target:library (C# Compiler Options)</span></span>

<span data-ttu-id="87261-104">Opcja **-target: Library** powoduje, że kompilator tworzy bibliotekę dołączaną dynamicznie (dll), a nie plik wykonywalny (exe).</span><span class="sxs-lookup"><span data-stu-id="87261-104">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87261-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="87261-105">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="87261-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="87261-106">Remarks</span></span>  

 <span data-ttu-id="87261-107">Biblioteka DLL zostanie utworzona z rozszerzeniem dll.</span><span class="sxs-lookup"><span data-stu-id="87261-107">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="87261-108">O ile nie określono inaczej z opcją [-out](./out-compiler-option.md) , nazwa pliku wyjściowego przyjmuje nazwę pierwszego pliku wejściowego.</span><span class="sxs-lookup"><span data-stu-id="87261-108">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="87261-109">W przypadku określenia w wierszu polecenia wszystkie pliki **do następnej lub** **docelowej opcji modułu** są używane do tworzenia pliku dll.</span><span class="sxs-lookup"><span data-stu-id="87261-109">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="87261-110">Podczas kompilowania pliku DLL Metoda [Main](../../programming-guide/main-and-command-args/index.md) nie jest wymagana.</span><span class="sxs-lookup"><span data-stu-id="87261-110">When building a .dll file, a [Main](../../programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="87261-111">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="87261-111">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="87261-112">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="87261-112">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="87261-113">Kliknij stronę właściwości **aplikacji** .</span><span class="sxs-lookup"><span data-stu-id="87261-113">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="87261-114">Zmodyfikuj właściwość **typu danych wyjściowych** .</span><span class="sxs-lookup"><span data-stu-id="87261-114">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="87261-115">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A> .</span><span class="sxs-lookup"><span data-stu-id="87261-115">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87261-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="87261-116">Example</span></span>  

 <span data-ttu-id="87261-117">Kompiluj `in.cs` , Utwórz `in.dll` :</span><span class="sxs-lookup"><span data-stu-id="87261-117">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="87261-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="87261-118">See also</span></span>

- [<span data-ttu-id="87261-119">-Target (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="87261-119">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="87261-120">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="87261-120">C# Compiler Options</span></span>](./index.md)
