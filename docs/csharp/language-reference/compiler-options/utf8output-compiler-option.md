---
description: -utf8output — (opcje kompilatora C#)
title: -utf8output — (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /utf8output
helpviewer_keywords:
- utf8output compiler option [C#]
- /utf8output compiler option [C#]
- -utf8output compiler option [C#]
ms.assetid: 27ff7381-c281-45d7-b2eb-1ad644b1354e
ms.openlocfilehash: 675782ffef9768e57397e765538924b78a2abcaa
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "91171367"
---
# <a name="-utf8output-c-compiler-options"></a><span data-ttu-id="78a36-103">-utf8output — (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="78a36-103">-utf8output (C# Compiler Options)</span></span>

<span data-ttu-id="78a36-104">Opcja **-utf8output —** wyświetla dane wyjściowe kompilatora przy użyciu kodowania UTF-8.</span><span class="sxs-lookup"><span data-stu-id="78a36-104">The **-utf8output** option displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a36-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="78a36-105">Syntax</span></span>  
  
```console  
-utf8output  
```  
  
## <a name="remarks"></a><span data-ttu-id="78a36-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="78a36-106">Remarks</span></span>  

 <span data-ttu-id="78a36-107">W niektórych konfiguracjach międzynarodowych dane wyjściowe kompilatora nie mogą być prawidłowo wyświetlane w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="78a36-107">In some international configurations, compiler output cannot correctly be displayed in the console.</span></span> <span data-ttu-id="78a36-108">W tych konfiguracjach należy użyć parametrów **-utf8output —** i przekierować dane wyjściowe kompilatora do pliku.</span><span class="sxs-lookup"><span data-stu-id="78a36-108">In these configurations, use **-utf8output** and redirect compiler output to a file.</span></span>  
  
 <span data-ttu-id="78a36-109">Ta opcja kompilatora jest niedostępna w programie Visual Studio i nie można jej zmienić programowo.</span><span class="sxs-lookup"><span data-stu-id="78a36-109">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a36-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="78a36-110">See also</span></span>

- [<span data-ttu-id="78a36-111">Opcje kompilatora C#</span><span class="sxs-lookup"><span data-stu-id="78a36-111">C# Compiler Options</span></span>](./index.md)
