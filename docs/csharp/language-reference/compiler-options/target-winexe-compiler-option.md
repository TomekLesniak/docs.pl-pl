---
description: '-target: winexe (opcje kompilatora C#)'
title: '-target: winexe (opcje kompilatora C#)'
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 5f8717115464ec3d9798228d7d50a8f08b2db300
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89466095"
---
# <a name="-targetwinexe-c-compiler-options"></a><span data-ttu-id="c18e8-103">-target: winexe (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="c18e8-103">-target:winexe (C# Compiler Options)</span></span>
<span data-ttu-id="c18e8-104">Opcja **-target: winexe** powoduje, że kompilator tworzy plik wykonywalny (exe), program systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="c18e8-104">The **-target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c18e8-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="c18e8-105">Syntax</span></span>  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="c18e8-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c18e8-106">Remarks</span></span>  
 <span data-ttu-id="c18e8-107">Plik wykonywalny zostanie utworzony z rozszerzeniem. exe.</span><span class="sxs-lookup"><span data-stu-id="c18e8-107">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="c18e8-108">Program systemu Windows to taki, który udostępnia interfejs użytkownika z biblioteki .NET lub interfejsów API systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="c18e8-108">A Windows program is one that provides a user interface from either the .NET library or with the Windows APIs.</span></span>  
  
 <span data-ttu-id="c18e8-109">Użyj [-target: exe](./target-exe-compiler-option.md) , aby utworzyć aplikację konsolową.</span><span class="sxs-lookup"><span data-stu-id="c18e8-109">Use [-target:exe](./target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="c18e8-110">O ile nie określono inaczej z opcją [-out](./out-compiler-option.md) , nazwa pliku wyjściowego przyjmuje nazwę pliku wejściowego, który zawiera metodę [Main](../../programming-guide/main-and-command-args/index.md) .</span><span class="sxs-lookup"><span data-stu-id="c18e8-110">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="c18e8-111">Gdy jest określony w wierszu polecenia, wszystkie pliki do momentu użycia **opcji Dalej lub** [-Target](./target-compiler-option.md) są używane do tworzenia programu systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="c18e8-111">When specified at the command line, all files until the next **-out** or [-target](./target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="c18e8-112">Jedna i tylko jedna metoda **Main** jest wymagana w plikach kodu źródłowego, które są kompilowane w pliku. exe.</span><span class="sxs-lookup"><span data-stu-id="c18e8-112">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="c18e8-113">Opcja [-Main](./main-compiler-option.md) pozwala określić, która Klasa zawiera metodę **Main** , w przypadkach, gdy kod zawiera więcej niż jedną klasę przy użyciu metody **Main** .</span><span class="sxs-lookup"><span data-stu-id="c18e8-113">The [-main](./main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="c18e8-114">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c18e8-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="c18e8-115">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="c18e8-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="c18e8-116">Kliknij stronę właściwości **aplikacji** .</span><span class="sxs-lookup"><span data-stu-id="c18e8-116">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="c18e8-117">Zmodyfikuj właściwość **typu danych wyjściowych** .</span><span class="sxs-lookup"><span data-stu-id="c18e8-117">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="c18e8-118">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A> .</span><span class="sxs-lookup"><span data-stu-id="c18e8-118">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c18e8-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="c18e8-119">Example</span></span>  
 <span data-ttu-id="c18e8-120">Kompiluj `in.cs` do programu Windows:</span><span class="sxs-lookup"><span data-stu-id="c18e8-120">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="c18e8-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c18e8-121">See also</span></span>

- [<span data-ttu-id="c18e8-122">-Target (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="c18e8-122">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="c18e8-123">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="c18e8-123">C# Compiler Options</span></span>](./index.md)
