---
description: -out (opcje kompilatora C#)
title: -out (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /out
helpviewer_keywords:
- /out compiler option [C#]
- out compiler option [C#]
- -out compiler option [C#]
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
ms.openlocfilehash: 409760ee0b147065a2128c62c304fb5d70cfcf42
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193884"
---
# <a name="-out-c-compiler-options"></a><span data-ttu-id="3c632-103">-out (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="3c632-103">-out (C# Compiler Options)</span></span>

<span data-ttu-id="3c632-104">Opcja **-out** określa nazwę pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="3c632-104">The **-out** option specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c632-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="3c632-105">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="3c632-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="3c632-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="3c632-107">Nazwa pliku wyjściowego utworzonego przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="3c632-107">The name of the output file created by the compiler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c632-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3c632-108">Remarks</span></span>  

 <span data-ttu-id="3c632-109">W wierszu polecenia można określić wiele plików wyjściowych dla kompilacji.</span><span class="sxs-lookup"><span data-stu-id="3c632-109">On the command line, it is possible to specify multiple output files for your compilation.</span></span> <span data-ttu-id="3c632-110">Kompilator oczekuje na znalezienie co najmniej jednego pliku kodu źródłowego po opcji **-out** .</span><span class="sxs-lookup"><span data-stu-id="3c632-110">The compiler expects to find one or more source code files following the **-out** option.</span></span> <span data-ttu-id="3c632-111">Następnie wszystkie pliki kodu źródłowego zostaną skompilowane do pliku wyjściowego określonego **przez tę opcję** .</span><span class="sxs-lookup"><span data-stu-id="3c632-111">Then, all source code files will be compiled into the output file specified by that **-out** option.</span></span>  
  
 <span data-ttu-id="3c632-112">Określ pełną nazwę i rozszerzenie pliku, który chcesz utworzyć.</span><span class="sxs-lookup"><span data-stu-id="3c632-112">Specify the full name and extension of the file you want to create.</span></span>  
  
 <span data-ttu-id="3c632-113">Jeśli nie określisz nazwy pliku wyjściowego:</span><span class="sxs-lookup"><span data-stu-id="3c632-113">If you do not specify the name of the output file:</span></span>  
  
- <span data-ttu-id="3c632-114">Plik. exe zajmie swoją nazwę z pliku kodu źródłowego, który zawiera metodę **Main** .</span><span class="sxs-lookup"><span data-stu-id="3c632-114">An .exe will take its name from the source code file that contains the **Main** method.</span></span>  
  
- <span data-ttu-id="3c632-115">Plik. dll lub. webmodule przyjmuje swoją nazwę z pierwszego pliku kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="3c632-115">A .dll or .netmodule will take its name from the first source code file.</span></span>  
  
 <span data-ttu-id="3c632-116">Plik kodu źródłowego używany do kompilowania jednego pliku wyjściowego nie może być używany w tej samej kompilacji dla kompilacji innego pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="3c632-116">A source code file used to compile one output file cannot be used in the same compilation for the compilation of another output file.</span></span>  
  
 <span data-ttu-id="3c632-117">W przypadku tworzenia wielu plików wyjściowych w kompilacji wiersza polecenia należy pamiętać, że tylko jeden z plików wyjściowych może być zestawem i że tylko pierwszy plik wyjściowy określony (niejawnie lub jawnie w **trybie out**) może być zestawem.</span><span class="sxs-lookup"><span data-stu-id="3c632-117">When producing multiple output files in a command-line compilation, keep in mind that only one of the output files can be an assembly and that only the first output file specified (implicitly or explicitly with **-out**) can be the assembly.</span></span>  
  
 <span data-ttu-id="3c632-118">Wszystkie moduły tworzone w ramach kompilacji stają się plikami skojarzonymi z dowolnym zestawem również w kompilacji.</span><span class="sxs-lookup"><span data-stu-id="3c632-118">Any modules produced as part of a compilation become files associated with any assembly also produced in the compilation.</span></span> <span data-ttu-id="3c632-119">Użyj [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) , aby wyświetlić manifest zestawu, aby wyświetlić skojarzone pliki.</span><span class="sxs-lookup"><span data-stu-id="3c632-119">Use [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) to view the assembly manifest to see the associated files.</span></span>  
  
 <span data-ttu-id="3c632-120">Opcja kompilatora-out jest wymagana, aby plik exe był elementem docelowym zestawu zaprzyjaźnionego.</span><span class="sxs-lookup"><span data-stu-id="3c632-120">The -out compiler option is required in order for an exe to be the target of a friend assembly.</span></span> <span data-ttu-id="3c632-121">Aby uzyskać więcej informacji, zobacz [zaprzyjaźnione zestawy](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="3c632-121">For more information see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="3c632-122">Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3c632-122">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="3c632-123">Otwórz stronę **Właściwości** projektu.</span><span class="sxs-lookup"><span data-stu-id="3c632-123">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="3c632-124">Kliknij stronę właściwości **aplikacji** .</span><span class="sxs-lookup"><span data-stu-id="3c632-124">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="3c632-125">Zmodyfikuj właściwość **nazwy zestawu** .</span><span class="sxs-lookup"><span data-stu-id="3c632-125">Modify the **Assembly name** property.</span></span>  
  
     <span data-ttu-id="3c632-126">Aby programowo ustawić tę opcję kompilatora: <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> jest to właściwość tylko do odczytu, która jest określana przez kombinację typu projektu (exe, biblioteka i tak dalej) i nazwę zestawu.</span><span class="sxs-lookup"><span data-stu-id="3c632-126">To set this compiler option programmatically: the <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> is a read-only property, which is determined by a combination of the project type (exe, library, and so forth) and the assembly name.</span></span> <span data-ttu-id="3c632-127">Modyfikacja jednej lub obu tych właściwości będzie konieczna do ustawienia nazwy pliku wyjściowego.</span><span class="sxs-lookup"><span data-stu-id="3c632-127">Modifying one or both of these properties will be necessary to set the output file name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c632-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="3c632-128">Example</span></span>  

 <span data-ttu-id="3c632-129">Kompiluj `t.cs` i twórz plik wyjściowy `t.exe` , a także Kompiluj `t2.cs` i twórz plik wyjściowy modułu `mymodule.netmodule` :</span><span class="sxs-lookup"><span data-stu-id="3c632-129">Compile `t.cs` and create output file `t.exe`, as well as build `t2.cs` and create module output file `mymodule.netmodule`:</span></span>  
  
```console  
csc t.cs -out:mymodule.netmodule -target:module t2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c632-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3c632-130">See also</span></span>

- [<span data-ttu-id="3c632-131">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="3c632-131">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="3c632-132">Zaprzyjaźnione zestawy</span><span class="sxs-lookup"><span data-stu-id="3c632-132">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
- [<span data-ttu-id="3c632-133">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="3c632-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
