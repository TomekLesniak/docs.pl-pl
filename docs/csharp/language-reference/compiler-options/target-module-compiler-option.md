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
ms.openlocfilehash: d8691e5e4477dbbe989344469b44382d5e0e7c8b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193611"
---
# <a name="-targetmodule-c-compiler-options"></a><span data-ttu-id="5fb9d-103">-target: module (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="5fb9d-103">-target:module (C# Compiler Options)</span></span>

<span data-ttu-id="5fb9d-104">Ta opcja powoduje, że kompilator nie generuje manifestu zestawu.</span><span class="sxs-lookup"><span data-stu-id="5fb9d-104">This option causes the compiler to not generate an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fb9d-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="5fb9d-105">Syntax</span></span>  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a><span data-ttu-id="5fb9d-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5fb9d-106">Remarks</span></span>  

 <span data-ttu-id="5fb9d-107">Domyślnie plik wyjściowy utworzony przez kompilację z tą opcją będzie miał rozszerzenie.</span><span class="sxs-lookup"><span data-stu-id="5fb9d-107">By default, the output file created by compiling with this option will have an extension of .netmodule.</span></span>  
  
 <span data-ttu-id="5fb9d-108">Nie można załadować pliku, który nie zawiera manifestu zestawu, przez środowisko uruchomieniowe platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="5fb9d-108">A file that does not have an assembly manifest cannot be loaded by the .NET runtime.</span></span> <span data-ttu-id="5fb9d-109">Jednak taki plik można włączyć do manifestu zestawu zestawu za pomocą [-addmodule](./addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5fb9d-109">However, such a file can be incorporated into the assembly manifest of an assembly by means of [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="5fb9d-110">W przypadku utworzenia więcej niż jednego modułu w pojedynczej kompilacji typy [wewnętrzne](../keywords/internal.md) w jednym module będą dostępne dla innych modułów w kompilacji.</span><span class="sxs-lookup"><span data-stu-id="5fb9d-110">If more than one module is created in a single compilation, [internal](../keywords/internal.md) types in one module will be available to other modules in the compilation.</span></span> <span data-ttu-id="5fb9d-111">Gdy kod w jednym module odwołuje się do `internal` typów w innym module, oba moduły muszą być dołączone do manifestu zestawu, za pomocą **-addmodule**.</span><span class="sxs-lookup"><span data-stu-id="5fb9d-111">When code in one module references `internal` types in another module, then both modules must be incorporated into an assembly manifest, by means of **-addmodule**.</span></span>  
  
 <span data-ttu-id="5fb9d-112">Tworzenie modułu nie jest obsługiwane w środowisku deweloperskim programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5fb9d-112">Creating a module is not supported in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="5fb9d-113">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A> .</span><span class="sxs-lookup"><span data-stu-id="5fb9d-113">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fb9d-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="5fb9d-114">Example</span></span>  

 <span data-ttu-id="5fb9d-115">Kompiluj `in.cs` , Utwórz `in.netmodule` :</span><span class="sxs-lookup"><span data-stu-id="5fb9d-115">Compile `in.cs`, creating `in.netmodule`:</span></span>  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="5fb9d-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5fb9d-116">See also</span></span>

- [<span data-ttu-id="5fb9d-117">-Target (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="5fb9d-117">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="5fb9d-118">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="5fb9d-118">C# Compiler Options</span></span>](./index.md)
