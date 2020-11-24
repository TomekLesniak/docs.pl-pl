---
title: CoUninitializeEE — Funkcja
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
ms.openlocfilehash: e6616392eaa23f8ba40247c5aabd12e4d530cea1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687850"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="d0ae4-102">CoUninitializeEE — Funkcja</span><span class="sxs-lookup"><span data-stu-id="d0ae4-102">CoUninitializeEE Function</span></span>

<span data-ttu-id="d0ae4-103">`CoUninitializeEE` jest przestarzały i nie zapewnia żadnych funkcji.</span><span class="sxs-lookup"><span data-stu-id="d0ae4-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0ae4-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d0ae4-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="d0ae4-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d0ae4-105">Remarks</span></span>  

 <span data-ttu-id="d0ae4-106">Nie można zwolnić aparatu wykonywania środowiska uruchomieniowego języka wspólnego z procesu.</span><span class="sxs-lookup"><span data-stu-id="d0ae4-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="d0ae4-107">Aby zamknąć wywołanie aparatu wykonywania [CorExitProcess —](corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="d0ae4-107">To shut down the execution engine call [CorExitProcess](corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ae4-108">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d0ae4-108">See also</span></span>

- [<span data-ttu-id="d0ae4-109">CoInitializeEE — Funkcja</span><span class="sxs-lookup"><span data-stu-id="d0ae4-109">CoInitializeEE Function</span></span>](coinitializeee-function.md)
- [<span data-ttu-id="d0ae4-110">Statyczne funkcje globalne metadanych</span><span class="sxs-lookup"><span data-stu-id="d0ae4-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
