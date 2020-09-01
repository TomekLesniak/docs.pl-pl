---
description: -opcji refout (opcje kompilatora C#)
title: -opcji refout (opcje kompilatora C#)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: 424782e4607fea63130e95ab09a671c75fe1404d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128717"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="bceaa-103">-opcji refout (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="bceaa-103">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="bceaa-104">Opcja **-opcji refout** określa ścieżkę pliku, w którym zestaw odniesienia powinien być wyjściowy.</span><span class="sxs-lookup"><span data-stu-id="bceaa-104">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="bceaa-105">Powoduje to przetłumaczenie na `metadataPeStream` w interfejsie API emisji.</span><span class="sxs-lookup"><span data-stu-id="bceaa-105">This translates to `metadataPeStream` in the Emit API.</span></span> <span data-ttu-id="bceaa-106">Ta opcja odnosi się do właściwości Project [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) programu MSBuild.</span><span class="sxs-lookup"><span data-stu-id="bceaa-106">This option corresponds to the [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="bceaa-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="bceaa-107">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="bceaa-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="bceaa-108">Arguments</span></span>

 <span data-ttu-id="bceaa-109">`filepath` Ścieżka do zestawu referencyjnego.</span><span class="sxs-lookup"><span data-stu-id="bceaa-109">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="bceaa-110">Zwykle powinna być zgodna z zestawem podstawowym.</span><span class="sxs-lookup"><span data-stu-id="bceaa-110">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="bceaa-111">Zalecaną konwencją (używaną przez program MSBuild) jest umieszczenie zestawu odwołania w podfolderze "ref/" względem podstawowego zestawu.</span><span class="sxs-lookup"><span data-stu-id="bceaa-111">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="bceaa-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bceaa-112">Remarks</span></span>

<span data-ttu-id="bceaa-113">Zestawy referencyjne są specjalnym typem zestawu, który zawiera tylko minimalną ilość metadanych wymaganą do reprezentowania publicznej powierzchni interfejsu API biblioteki.</span><span class="sxs-lookup"><span data-stu-id="bceaa-113">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="bceaa-114">Obejmują one deklaracje dla wszystkich elementów członkowskich, które są istotne w przypadku odwoływania się do zestawu w narzędziach kompilacji, ale wyklucza wszystkie implementacje składowych i deklaracje prywatnych członków, którzy nie mają zauważalnego wpływu na ich kontrakt interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="bceaa-114">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="bceaa-115">Aby uzyskać więcej informacji, zobacz [zestawy referencyjne](../../../standard/assembly/reference-assemblies.md) w przewodniku .NET.</span><span class="sxs-lookup"><span data-stu-id="bceaa-115">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="bceaa-116">`-refout`Opcje i [`-refonly`](refonly-compiler-option.md) wzajemnie się wykluczają.</span><span class="sxs-lookup"><span data-stu-id="bceaa-116">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="bceaa-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bceaa-117">See also</span></span>

- [<span data-ttu-id="bceaa-118">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="bceaa-118">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="bceaa-119">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="bceaa-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
