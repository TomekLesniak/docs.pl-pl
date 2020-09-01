---
description: -nostdlib (opcje kompilatora C#)
title: -nostdlib (opcje kompilatora C#)
ms.date: 12/20/2019
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 214918b32f1f1276eb936e66daba3d372a1e9228
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125101"
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="5c1e0-103">-nostdlib (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="5c1e0-103">-nostdlib (C# Compiler Options)</span></span>

<span data-ttu-id="5c1e0-104">**-nostdlib** uniemożliwia import mscorlib.dll, który definiuje całą przestrzeń nazw System.</span><span class="sxs-lookup"><span data-stu-id="5c1e0-104">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>

## <a name="syntax"></a><span data-ttu-id="5c1e0-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="5c1e0-105">Syntax</span></span>

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a><span data-ttu-id="5c1e0-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5c1e0-106">Remarks</span></span>

<span data-ttu-id="5c1e0-107">Użyj tej opcji, jeśli chcesz zdefiniować lub utworzyć własną przestrzeń nazw systemu i obiekty.</span><span class="sxs-lookup"><span data-stu-id="5c1e0-107">Use this option if you want to define or create your own System namespace and objects.</span></span>

<span data-ttu-id="5c1e0-108">Jeśli nie określisz opcji **-nostdlib**, mscorlib.dll jest zaimportowana do programu (tak samo jak w przypadku określenia **-nostdlib-**).</span><span class="sxs-lookup"><span data-stu-id="5c1e0-108">If you do not specify **-nostdlib**, mscorlib.dll is imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="5c1e0-109">Określenie **-nostdlib** jest taka sama jak w przypadku określenia **-nostdlib +**.</span><span class="sxs-lookup"><span data-stu-id="5c1e0-109">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>

### <a name="to-set-this-compiler-option-in-visual-studio"></a><span data-ttu-id="5c1e0-110">Aby ustawić tę opcję kompilatora w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5c1e0-110">To set this compiler option in Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="5c1e0-111">Poniższe instrukcje dotyczą tylko programu Visual Studio 2015 (i jego wcześniejszych wersji).</span><span class="sxs-lookup"><span data-stu-id="5c1e0-111">The following instructions apply to Visual Studio 2015 (and earlier versions) only.</span></span> <span data-ttu-id="5c1e0-112">Właściwość kompilacji \*\*mscorlib.dllnie \*\* istnieje w nowszych wersjach programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5c1e0-112">The **Do not reference mscorlib.dll** build property doesn't exist in newer versions of Visual Studio.</span></span>

1. <span data-ttu-id="5c1e0-113">Otwórz stronę **Właściwości** dla projektu.</span><span class="sxs-lookup"><span data-stu-id="5c1e0-113">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="5c1e0-114">Kliknij stronę właściwości **kompilacji** .</span><span class="sxs-lookup"><span data-stu-id="5c1e0-114">Click the **Build** properties page.</span></span>

3. <span data-ttu-id="5c1e0-115">Kliknij przycisk **Zaawansowane** .</span><span class="sxs-lookup"><span data-stu-id="5c1e0-115">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="5c1e0-116">Zmodyfikuj właściwość nie **odwołuj mscorlib.dll** .</span><span class="sxs-lookup"><span data-stu-id="5c1e0-116">Modify the **Do not reference mscorlib.dll** property.</span></span>

### <a name="to-set-this-compiler-option-programmatically"></a><span data-ttu-id="5c1e0-117">Aby programowo ustawić tę opcję kompilatora</span><span class="sxs-lookup"><span data-stu-id="5c1e0-117">To set this compiler option programmatically</span></span>

<span data-ttu-id="5c1e0-118">Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A> .</span><span class="sxs-lookup"><span data-stu-id="5c1e0-118">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c1e0-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5c1e0-119">See also</span></span>

- [<span data-ttu-id="5c1e0-120">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="5c1e0-120">C# Compiler Options</span></span>](./index.md)
