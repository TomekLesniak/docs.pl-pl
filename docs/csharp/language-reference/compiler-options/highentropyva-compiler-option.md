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
# <a name="-highentropyva-c-compiler-options"></a>-HIGHENTROPYVA (opcje kompilatora C#)
Opcja kompilatora **-HIGHENTROPYVA** informuje jądro systemu Windows o tym, czy określony plik wykonywalny obsługuje generowanie losowe układu przestrzeni adresowej (ASLR).  
  
## <a name="syntax"></a>Składnia  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argumenty  
 `+` &#124; `-`  
 Ta opcja określa, że 64-bitowy plik wykonywalny lub plik wykonywalny, który jest oznaczony przez opcję kompilator [-platform: anycpu](./platform-compiler-option.md) , obsługuje wirtualną przestrzeń adresową o wysokiej entropii. Opcja jest domyślnie wyłączona. Użyj **-HIGHENTROPYVA +** lub **-HIGHENTROPYVA** , aby je włączyć.  
  
## <a name="remarks"></a>Uwagi  
 Opcja **-HIGHENTROPYVA** umożliwia używanie zgodnych wersji jądra systemu Windows w celu użycia wyższych stopni entropii podczas losowego układu przestrzeni adresowej procesu w ramach ASLR. Użycie wyższych stopni entropii oznacza, że większa liczba adresów może być przypisana do regionów pamięci, takich jak stosy i sterty. W związku z tym trudniejsze jest odpuszczenie lokalizacji określonego obszaru pamięci.  
  
 Gdy opcja kompilatora **-HIGHENTROPYVA** jest określona, docelowy plik wykonywalny i wszystkie moduły, od których zależy, muszą być w stanie obsłużyć wartości wskaźników, które są większe niż 4 gigabajty (GB), gdy są uruchamiane jako proces 64-bitowy.
