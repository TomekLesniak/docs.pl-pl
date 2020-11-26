---
description: -refonly (opcje kompilatora C#)
title: -refonly (opcje kompilatora C#)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: f9a92462203bedff93a4a711ca8742465b7a561c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "89124750"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="eff96-103">-refonly (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="eff96-103">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="eff96-104">Opcja **-refonly** wskazuje, że zestaw odwołania powinien być wyjściem, a nie zestawem implementacji, jako podstawowy wynik.</span><span class="sxs-lookup"><span data-stu-id="eff96-104">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="eff96-105">`-refonly`Parametr dyskretnie wyłącza umieszczanie plików PDB, ponieważ nie można wykonać zestawów referencyjnych.</span><span class="sxs-lookup"><span data-stu-id="eff96-105">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span> <span data-ttu-id="eff96-106">Ta opcja odnosi się do właściwości Project [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) programu MSBuild.</span><span class="sxs-lookup"><span data-stu-id="eff96-106">This option corresponds to the [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="eff96-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="eff96-107">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="eff96-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="eff96-108">Remarks</span></span>

<span data-ttu-id="eff96-109">Zestawy referencyjne są specjalnym typem zestawu, który zawiera tylko minimalną ilość metadanych wymaganą do reprezentowania publicznej powierzchni interfejsu API biblioteki.</span><span class="sxs-lookup"><span data-stu-id="eff96-109">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="eff96-110">Obejmują one deklaracje dla wszystkich elementów członkowskich, które są istotne w przypadku odwoływania się do zestawu w narzędziach kompilacji, ale wyklucza wszystkie implementacje składowych i deklaracje prywatnych członków, którzy nie mają zauważalnego wpływu na ich kontrakt interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="eff96-110">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="eff96-111">Aby uzyskać więcej informacji, zobacz [zestawy referencyjne](../../../standard/assembly/reference-assemblies.md) w przewodniku .NET.</span><span class="sxs-lookup"><span data-stu-id="eff96-111">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="eff96-112">`-refonly`Opcje i [`-refout`](refout-compiler-option.md) wzajemnie się wykluczają.</span><span class="sxs-lookup"><span data-stu-id="eff96-112">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="eff96-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="eff96-113">See also</span></span>

- [<span data-ttu-id="eff96-114">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="eff96-114">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="eff96-115">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="eff96-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
