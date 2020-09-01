---
description: '-target: module (opcje kompilatora C#)'
title: '-target: module (opcje kompilatora C#)'
ms.date: 07/20/2015
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
ms.openlocfilehash: 2c592d2fe001bb0908a06a6eb3287a39040b8715
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128455"
---
# <a name="-targetmodule-c-compiler-options"></a><span data-ttu-id="9daa7-103">-target: module (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="9daa7-103">-target:module (C# Compiler Options)</span></span>
<span data-ttu-id="9daa7-104">Ta opcja powoduje, że kompilator nie generuje manifestu zestawu.</span><span class="sxs-lookup"><span data-stu-id="9daa7-104">This option causes the compiler to not generate an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9daa7-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="9daa7-105">Syntax</span></span>  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a><span data-ttu-id="9daa7-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9daa7-106">Remarks</span></span>  
 <span data-ttu-id="9daa7-107">Domyślnie plik wyjściowy utworzony przez kompilację z tą opcją będzie miał rozszerzenie.</span><span class="sxs-lookup"><span data-stu-id="9daa7-107">By default, the output file created by compiling with this option will have an extension of .netmodule.</span></span>  
  
 <span data-ttu-id="9daa7-108">Nie można załadować pliku, który nie zawiera manifestu zestawu, za pomocą środowiska uruchomieniowego języka wspólnego .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9daa7-108">A file that does not have an assembly manifest cannot be loaded by the .NET Framework common language runtime.</span></span> <span data-ttu-id="9daa7-109">Jednak taki plik można włączyć do manifestu zestawu zestawu za pomocą [-addmodule](./addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="9daa7-109">However, such a file can be incorporated into the assembly manifest of an assembly by means of [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="9daa7-110">W przypadku utworzenia więcej niż jednego modułu w pojedynczej kompilacji typy [wewnętrzne](../keywords/internal.md) w jednym module będą dostępne dla innych modułów w kompilacji.</span><span class="sxs-lookup"><span data-stu-id="9daa7-110">If more than one module is created in a single compilation, [internal](../keywords/internal.md) types in one module will be available to other modules in the compilation.</span></span> <span data-ttu-id="9daa7-111">Gdy kod w jednym module odwołuje się do `internal` typów w innym module, oba moduły muszą być dołączone do manifestu zestawu, za pomocą **-addmodule**.</span><span class="sxs-lookup"><span data-stu-id="9daa7-111">When code in one module references `internal` types in another module, then both modules must be incorporated into an assembly manifest, by means of **-addmodule**.</span></span>  
  
 <span data-ttu-id="9daa7-112">Tworzenie modułu nie jest obsługiwane w środowisku deweloperskim programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9daa7-112">Creating a module is not supported in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="9daa7-113">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A> .</span><span class="sxs-lookup"><span data-stu-id="9daa7-113">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9daa7-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="9daa7-114">Example</span></span>  
 <span data-ttu-id="9daa7-115">Kompiluj `in.cs` , Utwórz `in.netmodule` :</span><span class="sxs-lookup"><span data-stu-id="9daa7-115">Compile `in.cs`, creating `in.netmodule`:</span></span>  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="9daa7-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9daa7-116">See also</span></span>

- [<span data-ttu-id="9daa7-117">-Target (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="9daa7-117">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="9daa7-118">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="9daa7-118">C# Compiler Options</span></span>](./index.md)
