---
title: IDebuggerInfo::IsDebuggerAttached — Metoda
ms.date: 03/30/2017
api_name:
- IDebuggerInfo.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type:
- apiref
ms.openlocfilehash: 28b0c5ad5ed8b706974399dcd5468e9810b9fd57
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721702"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="a8ff5-102">IDebuggerInfo::IsDebuggerAttached — Metoda</span><span class="sxs-lookup"><span data-stu-id="a8ff5-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>

<span data-ttu-id="a8ff5-103">Pobiera wartość wskazującą, czy zarządzany debuger jest dołączony do tego procesu.</span><span class="sxs-lookup"><span data-stu-id="a8ff5-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8ff5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a8ff5-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8ff5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a8ff5-105">Parameters</span></span>  

 `pbAttached`  
 <span data-ttu-id="a8ff5-106">określoną Wskaźnik do wartości, która jest w `true` przypadku dołączenia zarządzanego debugera do procesu; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="a8ff5-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8ff5-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a8ff5-107">Requirements</span></span>  

 <span data-ttu-id="a8ff5-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8ff5-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8ff5-109">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a8ff5-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8ff5-110">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8ff5-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8ff5-111">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8ff5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8ff5-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a8ff5-112">See also</span></span>

- [<span data-ttu-id="a8ff5-113">IDebuggerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a8ff5-113">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)
