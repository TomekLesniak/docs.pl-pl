---
description: -Target (opcje kompilatora C#)
title: -Target (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /target
helpviewer_keywords:
- target compiler options [C#]
- /target compiler options [C#]
- assemblies [C#], compiling
- -target compiler options [C#]
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
ms.openlocfilehash: 5bfd988e8e399273dbd3292543a3730234c022d6
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128559"
---
# <a name="-target-c-compiler-options"></a><span data-ttu-id="c10c2-103">-Target (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="c10c2-103">-target (C# Compiler Options)</span></span>
<span data-ttu-id="c10c2-104">Opcję kompilatora **-Target** można określić w jednej z następujących form:</span><span class="sxs-lookup"><span data-stu-id="c10c2-104">The **-target** compiler option can be specified in one of the following forms:</span></span>  
  
 [<span data-ttu-id="c10c2-105">-target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="c10c2-105">-target:appcontainerexe</span></span>](./target-appcontainerexe-compiler-option.md)  
 <span data-ttu-id="c10c2-106">Aby utworzyć plik exe dla aplikacji ze sklepu Windows 8. x.</span><span class="sxs-lookup"><span data-stu-id="c10c2-106">To create an .exe file for Windows 8.x Store apps.</span></span>  
  
 [<span data-ttu-id="c10c2-107">-target:exe</span><span class="sxs-lookup"><span data-stu-id="c10c2-107">-target:exe</span></span>](./target-exe-compiler-option.md)  
 <span data-ttu-id="c10c2-108">Do utworzenia pliku. exe.</span><span class="sxs-lookup"><span data-stu-id="c10c2-108">To create an .exe file.</span></span>  
  
 [<span data-ttu-id="c10c2-109">-target:library</span><span class="sxs-lookup"><span data-stu-id="c10c2-109">-target:library</span></span>](./target-library-compiler-option.md)  
 <span data-ttu-id="c10c2-110">Aby utworzyć bibliotekę kodu.</span><span class="sxs-lookup"><span data-stu-id="c10c2-110">To create a code library.</span></span>  
  
 [<span data-ttu-id="c10c2-111">-target:module</span><span class="sxs-lookup"><span data-stu-id="c10c2-111">-target:module</span></span>](./target-module-compiler-option.md)  
 <span data-ttu-id="c10c2-112">Do utworzenia modułu.</span><span class="sxs-lookup"><span data-stu-id="c10c2-112">To create a module.</span></span>  
  
 [<span data-ttu-id="c10c2-113">-target:winexe</span><span class="sxs-lookup"><span data-stu-id="c10c2-113">-target:winexe</span></span>](./target-winexe-compiler-option.md)  
 <span data-ttu-id="c10c2-114">Do utworzenia programu systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="c10c2-114">To create a Windows program.</span></span>  
  
 [<span data-ttu-id="c10c2-115">-target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="c10c2-115">-target:winmdobj</span></span>](./target-winmdobj-compiler-option.md)  
 <span data-ttu-id="c10c2-116">Aby utworzyć pośredni plik. winmdobj.</span><span class="sxs-lookup"><span data-stu-id="c10c2-116">To create an intermediate .winmdobj file.</span></span>  
  
 <span data-ttu-id="c10c2-117">O ile nie określono **elementu-target: module**, **-Target** powoduje, że manifest zestawu .NET Framework zostanie umieszczony w pliku wyjściowym.</span><span class="sxs-lookup"><span data-stu-id="c10c2-117">Unless you specify **-target:module**, **-target** causes a .NET Framework assembly manifest to be placed in an output file.</span></span> <span data-ttu-id="c10c2-118">Aby uzyskać więcej informacji, zobacz [zestawy w programie .NET](../../../standard/assembly/index.md) i [wspólne atrybuty](../attributes/global.md).</span><span class="sxs-lookup"><span data-stu-id="c10c2-118">For more information, see [Assemblies in .NET](../../../standard/assembly/index.md) and [Common Attributes](../attributes/global.md).</span></span>  
  
 <span data-ttu-id="c10c2-119">Manifest zestawu jest umieszczany w pierwszym pliku wyjściowym exe w kompilacji lub w pierwszej bibliotece DLL, jeśli nie ma pliku wyjściowego. exe.</span><span class="sxs-lookup"><span data-stu-id="c10c2-119">The assembly manifest is placed in the first .exe output file in the compilation or in the first DLL, if there is no .exe output file.</span></span> <span data-ttu-id="c10c2-120">Na przykład w następującym wierszu polecenia manifest zostanie umieszczony w `1.exe` :</span><span class="sxs-lookup"><span data-stu-id="c10c2-120">For example, in the following command line, the manifest will be placed in `1.exe`:</span></span>  
  
```console  
csc -out:1.exe t1.cs -out:2.netmodule t2.cs  
```  
  
 <span data-ttu-id="c10c2-121">Kompilator tworzy tylko jeden manifest zestawu na kompilację.</span><span class="sxs-lookup"><span data-stu-id="c10c2-121">The compiler creates only one assembly manifest per compilation.</span></span> <span data-ttu-id="c10c2-122">Informacje o wszystkich plikach w kompilacji są umieszczane w manifeście zestawu.</span><span class="sxs-lookup"><span data-stu-id="c10c2-122">Information about all files in a compilation is placed in the assembly manifest.</span></span> <span data-ttu-id="c10c2-123">Wszystkie pliki wyjściowe z wyjątkiem plików utworzonych za pomocą **elementu-target: module** mogą zawierać manifest zestawu.</span><span class="sxs-lookup"><span data-stu-id="c10c2-123">All output files except those created with **-target:module** can contain an assembly manifest.</span></span> <span data-ttu-id="c10c2-124">W przypadku tworzenia wielu plików wyjściowych w wierszu polecenia można utworzyć tylko jeden manifest zestawu i musi on przejść do pierwszego pliku wyjściowego określonego w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="c10c2-124">When producing multiple output files at the command line, only one assembly manifest can be created and it must go into the first output file specified on the command line.</span></span> <span data-ttu-id="c10c2-125">Niezależnie od tego, jaki pierwszy plik wyjściowy jest (**-target: exe**, **-target: winexe**, **-target: Library** lub **-target: module**), wszystkie inne pliki wyjściowe utworzone w tej samej kompilacji muszą być modułami (**-target: module**).</span><span class="sxs-lookup"><span data-stu-id="c10c2-125">No matter what the first output file is (**-target:exe**, **-target:winexe**, **-target:library** or **-target:module**), any other output files produced in the same compilation must be modules (**-target:module**).</span></span>  
  
 <span data-ttu-id="c10c2-126">W przypadku utworzenia zestawu można wskazać, że całość lub część kodu jest zgodna ze specyfikacją CLS z <xref:System.CLSCompliantAttribute> atrybutem.</span><span class="sxs-lookup"><span data-stu-id="c10c2-126">If you create an assembly, you can indicate that all or part of your code is CLS compliant with the <xref:System.CLSCompliantAttribute> attribute.</span></span>  
  
```csharp  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 <span data-ttu-id="c10c2-127">Aby uzyskać więcej informacji o tym, jak można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A> .</span><span class="sxs-lookup"><span data-stu-id="c10c2-127">For more information about setting this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c10c2-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c10c2-128">See also</span></span>

- [<span data-ttu-id="c10c2-129">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="c10c2-129">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="c10c2-130">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="c10c2-130">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="c10c2-131">-subsystemversion (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="c10c2-131">-subsystemversion (C# Compiler Options)</span></span>](./subsystemversion-compiler-option.md)
