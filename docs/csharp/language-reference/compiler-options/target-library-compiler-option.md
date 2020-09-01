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
ms.openlocfilehash: 953249c4d0168ed3d279d03a0b2fb63d8ff6d5f5
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128481"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="4423e-103">-target: Library (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="4423e-103">-target:library (C# Compiler Options)</span></span>
<span data-ttu-id="4423e-104">Opcja **-target: Library** powoduje, że kompilator tworzy bibliotekę dołączaną dynamicznie (dll), a nie plik wykonywalny (exe).</span><span class="sxs-lookup"><span data-stu-id="4423e-104">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4423e-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="4423e-105">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="4423e-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4423e-106">Remarks</span></span>  
 <span data-ttu-id="4423e-107">Biblioteka DLL zostanie utworzona z rozszerzeniem dll.</span><span class="sxs-lookup"><span data-stu-id="4423e-107">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="4423e-108">O ile nie określono inaczej z opcją [-out](./out-compiler-option.md) , nazwa pliku wyjściowego przyjmuje nazwę pierwszego pliku wejściowego.</span><span class="sxs-lookup"><span data-stu-id="4423e-108">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="4423e-109">W przypadku określenia w wierszu polecenia wszystkie pliki **do następnej lub** **docelowej opcji modułu** są używane do tworzenia pliku dll.</span><span class="sxs-lookup"><span data-stu-id="4423e-109">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="4423e-110">Podczas kompilowania pliku DLL Metoda [Main](../../programming-guide/main-and-command-args/index.md) nie jest wymagana.</span><span class="sxs-lookup"><span data-stu-id="4423e-110">When building a .dll file, a [Main](../../programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="4423e-111">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4423e-111">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="4423e-112">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="4423e-112">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="4423e-113">Kliknij stronę właściwości **aplikacji** .</span><span class="sxs-lookup"><span data-stu-id="4423e-113">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="4423e-114">Zmodyfikuj właściwość **typu danych wyjściowych** .</span><span class="sxs-lookup"><span data-stu-id="4423e-114">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="4423e-115">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A> .</span><span class="sxs-lookup"><span data-stu-id="4423e-115">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4423e-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="4423e-116">Example</span></span>  
 <span data-ttu-id="4423e-117">Kompiluj `in.cs` , Utwórz `in.dll` :</span><span class="sxs-lookup"><span data-stu-id="4423e-117">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="4423e-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4423e-118">See also</span></span>

- [<span data-ttu-id="4423e-119">-Target (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="4423e-119">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="4423e-120">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="4423e-120">C# Compiler Options</span></span>](./index.md)
