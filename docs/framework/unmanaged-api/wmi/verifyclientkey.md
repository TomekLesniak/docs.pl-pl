---
title: VerifyClientKey — funkcja (niezarządzana dokumentacja interfejsu API)
description: Funkcja VerifyClientKey gwarantuje, że klucz klienta ma poprawne zabezpieczenia.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 26cffe9936f2e01078b6f54e8499b58519f1018e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729424"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="746e5-103">VerifyClientKey, funkcja</span><span class="sxs-lookup"><span data-stu-id="746e5-103">VerifyClientKey function</span></span>

<span data-ttu-id="746e5-104">Zapewnia, że klucz klienta ma poprawne zabezpieczenia.</span><span class="sxs-lookup"><span data-stu-id="746e5-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="746e5-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="746e5-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey();
```  

## <a name="return-value"></a><span data-ttu-id="746e5-106">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="746e5-106">Return value</span></span>

<span data-ttu-id="746e5-107">Jeśli funkcja się powiedzie, zwracaną wartością jest `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="746e5-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="746e5-108">Jeśli funkcja się nie powiedzie, wartość zwracana jest kodem błędu o wartości innej niż zero zdefiniowanym w *Winerror. h*.</span><span class="sxs-lookup"><span data-stu-id="746e5-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="746e5-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="746e5-109">Requirements</span></span>  

 <span data-ttu-id="746e5-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="746e5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="746e5-111">**Nagłówek:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="746e5-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="746e5-112">**.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="746e5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="746e5-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="746e5-113">See also</span></span>

- [<span data-ttu-id="746e5-114">WMI i liczniki wydajności (niezarządzana dokumentacja interfejsu API)</span><span class="sxs-lookup"><span data-stu-id="746e5-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
