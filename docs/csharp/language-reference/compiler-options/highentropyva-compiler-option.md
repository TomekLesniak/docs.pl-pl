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
ms.openlocfilehash: f3cdeb5e63d632fecbbd94501558cc53c28a918a
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91173207"
---
# <a name="-highentropyva-c-compiler-options"></a><span data-ttu-id="2b4dc-103">-HIGHENTROPYVA (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="2b4dc-103">-highentropyva (C# Compiler Options)</span></span>

<span data-ttu-id="2b4dc-104">Opcja kompilatora **-HIGHENTROPYVA** informuje jądro systemu Windows o tym, czy określony plik wykonywalny obsługuje generowanie losowe układu przestrzeni adresowej (ASLR).</span><span class="sxs-lookup"><span data-stu-id="2b4dc-104">The **-highentropyva** compiler option tells the Windows kernel whether a particular executable supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b4dc-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="2b4dc-105">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2b4dc-106">Argumenty</span><span class="sxs-lookup"><span data-stu-id="2b4dc-106">Arguments</span></span>  

 <span data-ttu-id="2b4dc-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2b4dc-107">`+` &#124; `-`</span></span>  
 <span data-ttu-id="2b4dc-108">Ta opcja określa, że 64-bitowy plik wykonywalny lub plik wykonywalny, który jest oznaczony przez opcję kompilator [-platform: anycpu](./platform-compiler-option.md) , obsługuje wirtualną przestrzeń adresową o wysokiej entropii.</span><span class="sxs-lookup"><span data-stu-id="2b4dc-108">This option specifies that a 64-bit executable or an executable that is marked by the [-platform:anycpu](./platform-compiler-option.md) compiler option supports a high entropy virtual address space.</span></span> <span data-ttu-id="2b4dc-109">Opcja jest domyślnie wyłączona.</span><span class="sxs-lookup"><span data-stu-id="2b4dc-109">The option is disabled by default.</span></span> <span data-ttu-id="2b4dc-110">Użyj **-HIGHENTROPYVA +** lub **-HIGHENTROPYVA** , aby je włączyć.</span><span class="sxs-lookup"><span data-stu-id="2b4dc-110">Use **-highentropyva+** or **-highentropyva** to enable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b4dc-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2b4dc-111">Remarks</span></span>  

 <span data-ttu-id="2b4dc-112">Opcja **-HIGHENTROPYVA** umożliwia używanie zgodnych wersji jądra systemu Windows w celu użycia wyższych stopni entropii podczas losowego układu przestrzeni adresowej procesu w ramach ASLR.</span><span class="sxs-lookup"><span data-stu-id="2b4dc-112">The **-highentropyva** option enables compatible versions of the Windows kernel to use higher degrees of entropy when randomizing the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="2b4dc-113">Użycie wyższych stopni entropii oznacza, że większa liczba adresów może być przypisana do regionów pamięci, takich jak stosy i sterty.</span><span class="sxs-lookup"><span data-stu-id="2b4dc-113">Using higher degrees of entropy means that a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="2b4dc-114">W związku z tym trudniejsze jest odpuszczenie lokalizacji określonego obszaru pamięci.</span><span class="sxs-lookup"><span data-stu-id="2b4dc-114">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="2b4dc-115">Gdy opcja kompilatora **-HIGHENTROPYVA** jest określona, docelowy plik wykonywalny i wszystkie moduły, od których zależy, muszą być w stanie obsłużyć wartości wskaźników, które są większe niż 4 gigabajty (GB), gdy są uruchamiane jako proces 64-bitowy.</span><span class="sxs-lookup"><span data-stu-id="2b4dc-115">When the **-highentropyva** compiler option is specified, the target executable and any modules that it depends on must be able to handle pointer values that are larger than 4 gigabytes (GB) when they are running as a 64-bit process.</span></span>
