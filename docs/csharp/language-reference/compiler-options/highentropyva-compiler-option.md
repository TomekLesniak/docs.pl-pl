---
description: -HIGHENTROPYVA (opcje kompilatora C#)
title: -HIGHENTROPYVA (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /highentropyva
helpviewer_keywords:
- /highentropyva compiler option [C#]
- -highentropyva compiler option [C#]
- highentropyva compiler option [C#]
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
ms.openlocfilehash: 2c2e2780693a89072c4bb55b318be94089bf3ced
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125660"
---
# <a name="-highentropyva-c-compiler-options"></a><span data-ttu-id="0e537-103">-HIGHENTROPYVA (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="0e537-103">-highentropyva (C# Compiler Options)</span></span>
<span data-ttu-id="0e537-104">Opcja kompilatora **-HIGHENTROPYVA** informuje jądro systemu Windows o tym, czy określony plik wykonywalny obsługuje generowanie losowe układu przestrzeni adresowej (ASLR).</span><span class="sxs-lookup"><span data-stu-id="0e537-104">The **-highentropyva** compiler option tells the Windows kernel whether a particular executable supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e537-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="0e537-105">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0e537-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="0e537-106">Arguments</span></span>  
 <span data-ttu-id="0e537-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="0e537-107">`+` &#124; `-`</span></span>  
 <span data-ttu-id="0e537-108">Ta opcja określa, że 64-bitowy plik wykonywalny lub plik wykonywalny, który jest oznaczony przez opcję kompilator [-platform: anycpu](./platform-compiler-option.md) , obsługuje wirtualną przestrzeń adresową o wysokiej entropii.</span><span class="sxs-lookup"><span data-stu-id="0e537-108">This option specifies that a 64-bit executable or an executable that is marked by the [-platform:anycpu](./platform-compiler-option.md) compiler option supports a high entropy virtual address space.</span></span> <span data-ttu-id="0e537-109">Opcja jest domyślnie wyłączona.</span><span class="sxs-lookup"><span data-stu-id="0e537-109">The option is disabled by default.</span></span> <span data-ttu-id="0e537-110">Użyj **-HIGHENTROPYVA +** lub **-HIGHENTROPYVA** , aby je włączyć.</span><span class="sxs-lookup"><span data-stu-id="0e537-110">Use **-highentropyva+** or **-highentropyva** to enable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e537-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0e537-111">Remarks</span></span>  
 <span data-ttu-id="0e537-112">Opcja **-HIGHENTROPYVA** umożliwia używanie zgodnych wersji jądra systemu Windows w celu użycia wyższych stopni entropii podczas losowego układu przestrzeni adresowej procesu w ramach ASLR.</span><span class="sxs-lookup"><span data-stu-id="0e537-112">The **-highentropyva** option enables compatible versions of the Windows kernel to use higher degrees of entropy when randomizing the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="0e537-113">Użycie wyższych stopni entropii oznacza, że większa liczba adresów może być przypisana do regionów pamięci, takich jak stosy i sterty.</span><span class="sxs-lookup"><span data-stu-id="0e537-113">Using higher degrees of entropy means that a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="0e537-114">W związku z tym trudniejsze jest odpuszczenie lokalizacji określonego obszaru pamięci.</span><span class="sxs-lookup"><span data-stu-id="0e537-114">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="0e537-115">Gdy opcja kompilatora **-HIGHENTROPYVA** jest określona, docelowy plik wykonywalny i wszystkie moduły, od których zależy, muszą być w stanie obsłużyć wartości wskaźników, które są większe niż 4 gigabajty (GB), gdy są uruchamiane jako proces 64-bitowy.</span><span class="sxs-lookup"><span data-stu-id="0e537-115">When the **-highentropyva** compiler option is specified, the target executable and any modules that it depends on must be able to handle pointer values that are larger than 4 gigabytes (GB) when they are running as a 64-bit process.</span></span>
