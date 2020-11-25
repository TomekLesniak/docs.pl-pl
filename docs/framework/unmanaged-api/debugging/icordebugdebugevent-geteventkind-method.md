---
title: Metoda ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 7876dc6ec5ecee52b64e54e1c42533f8348e4dc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713681"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="5c2d7-102">Metoda ICorDebugDebugEvent::GetEventKind</span><span class="sxs-lookup"><span data-stu-id="5c2d7-102">ICorDebugDebugEvent::GetEventKind Method</span></span>

<span data-ttu-id="5c2d7-103">Wskazuje, jaki rodzaj zdarzenia `ICorDebugDebugEvent` reprezentuje ten obiekt.</span><span class="sxs-lookup"><span data-stu-id="5c2d7-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c2d7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5c2d7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c2d7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="5c2d7-105">Parameters</span></span>  

 <span data-ttu-id="5c2d7-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="5c2d7-106">pDebugEventKind</span></span>  
 <span data-ttu-id="5c2d7-107">Wskaźnik do elementu członkowskiego wyliczenia [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) , który wskazuje typ zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="5c2d7-107">A pointer to a [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c2d7-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5c2d7-108">Remarks</span></span>  

 <span data-ttu-id="5c2d7-109">Na podstawie wartości, można `pDebugEventKind` wywołać, `QueryInterface` Aby uzyskać dokładniejszy interfejs zdarzenia debugowania, który zawiera dodatkowe dane.</span><span class="sxs-lookup"><span data-stu-id="5c2d7-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c2d7-110">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5c2d7-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c2d7-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5c2d7-111">Requirements</span></span>  

 <span data-ttu-id="5c2d7-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c2d7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c2d7-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5c2d7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c2d7-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5c2d7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c2d7-115">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c2d7-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c2d7-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5c2d7-116">See also</span></span>

- [<span data-ttu-id="5c2d7-117">Interfejs ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="5c2d7-117">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="5c2d7-118">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="5c2d7-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
