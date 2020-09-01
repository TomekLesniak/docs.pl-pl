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
ms.openlocfilehash: 8a1be07455b54b375106fef1fb480d7abd2f1ca4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124724"
---
# <a name="-targetwinexe-c-compiler-options"></a><span data-ttu-id="2a79a-103">-target: winexe (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="2a79a-103">-target:winexe (C# Compiler Options)</span></span>
<span data-ttu-id="2a79a-104">Opcja **-target: winexe** powoduje, że kompilator tworzy plik wykonywalny (exe), program systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="2a79a-104">The **-target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a79a-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="2a79a-105">Syntax</span></span>  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="2a79a-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2a79a-106">Remarks</span></span>  
 <span data-ttu-id="2a79a-107">Plik wykonywalny zostanie utworzony z rozszerzeniem. exe.</span><span class="sxs-lookup"><span data-stu-id="2a79a-107">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="2a79a-108">Program systemu Windows to taki, który udostępnia interfejs użytkownika z biblioteki .NET Framework lub interfejsów API systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="2a79a-108">A Windows program is one that provides a user interface from either the .NET Framework library or with the Windows APIs.</span></span>  
  
 <span data-ttu-id="2a79a-109">Użyj [-target: exe](./target-exe-compiler-option.md) , aby utworzyć aplikację konsolową.</span><span class="sxs-lookup"><span data-stu-id="2a79a-109">Use [-target:exe](./target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="2a79a-110">O ile nie określono inaczej z opcją [-out](./out-compiler-option.md) , nazwa pliku wyjściowego przyjmuje nazwę pliku wejściowego, który zawiera metodę [Main](../../programming-guide/main-and-command-args/index.md) .</span><span class="sxs-lookup"><span data-stu-id="2a79a-110">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="2a79a-111">Gdy jest określony w wierszu polecenia, wszystkie pliki do momentu użycia **opcji Dalej lub** [-Target](./target-compiler-option.md) są używane do tworzenia programu systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="2a79a-111">When specified at the command line, all files until the next **-out** or [-target](./target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="2a79a-112">Jedna i tylko jedna metoda **Main** jest wymagana w plikach kodu źródłowego, które są kompilowane w pliku. exe.</span><span class="sxs-lookup"><span data-stu-id="2a79a-112">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="2a79a-113">Opcja [-Main](./main-compiler-option.md) pozwala określić, która Klasa zawiera metodę **Main** , w przypadkach, gdy kod zawiera więcej niż jedną klasę przy użyciu metody **Main** .</span><span class="sxs-lookup"><span data-stu-id="2a79a-113">The [-main](./main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="2a79a-114">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2a79a-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="2a79a-115">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="2a79a-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="2a79a-116">Kliknij stronę właściwości **aplikacji** .</span><span class="sxs-lookup"><span data-stu-id="2a79a-116">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="2a79a-117">Zmodyfikuj właściwość **typu danych wyjściowych** .</span><span class="sxs-lookup"><span data-stu-id="2a79a-117">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="2a79a-118">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A> .</span><span class="sxs-lookup"><span data-stu-id="2a79a-118">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a79a-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="2a79a-119">Example</span></span>  
 <span data-ttu-id="2a79a-120">Kompiluj `in.cs` do programu Windows:</span><span class="sxs-lookup"><span data-stu-id="2a79a-120">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a79a-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2a79a-121">See also</span></span>

- [<span data-ttu-id="2a79a-122">-Target (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="2a79a-122">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="2a79a-123">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="2a79a-123">C# Compiler Options</span></span>](./index.md)
