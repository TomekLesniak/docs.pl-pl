---
title: ICorPublish::EnumProcesses — Metoda
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
ms.openlocfilehash: 297f672097dd6561a971608f368369c623532907
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716918"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="cf147-102">ICorPublish::EnumProcesses — Metoda</span><span class="sxs-lookup"><span data-stu-id="cf147-102">ICorPublish::EnumProcesses Method</span></span>

<span data-ttu-id="cf147-103">Pobiera moduł wyliczający dla zarządzanych procesów uruchomionych na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="cf147-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf147-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cf147-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf147-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="cf147-105">Parameters</span></span>  

 `Type`  
 <span data-ttu-id="cf147-106">Wartość wyliczenia [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) , która określa typ procesu do pobrania.</span><span class="sxs-lookup"><span data-stu-id="cf147-106">A value of the [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="cf147-107">W bieżącej wersji tylko COR_PUB_MANAGEDONLY jest prawidłowy.</span><span class="sxs-lookup"><span data-stu-id="cf147-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="cf147-108">Wskaźnik do adresu wystąpienia [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) , który jest modułem wyliczającym procesy.</span><span class="sxs-lookup"><span data-stu-id="cf147-108">A pointer to the address of an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf147-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cf147-109">Remarks</span></span>  

 <span data-ttu-id="cf147-110">Kolekcja procesów modułu wyliczającego jest oparta na migawce procesów, które są uruchomione, gdy `EnumProcesses` Metoda jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="cf147-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="cf147-111">Moduł wyliczający nie będzie zawierać żadnych procesów kończących się przed lub po `EnumProcesses` wywołaniu.</span><span class="sxs-lookup"><span data-stu-id="cf147-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="cf147-112">`EnumProcesses`Metoda może być wywoływana więcej niż raz w tym wystąpieniu [ICorPublish](icorpublish-interface.md) , aby utworzyć nową, aktualną kolekcję procesów.</span><span class="sxs-lookup"><span data-stu-id="cf147-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="cf147-113">Kolejne wywołania metody nie będą miały wpływ na istniejące kolekcje `EnumProcesses` .</span><span class="sxs-lookup"><span data-stu-id="cf147-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf147-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cf147-114">Requirements</span></span>  

 <span data-ttu-id="cf147-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf147-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf147-116">**Nagłówek:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="cf147-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="cf147-117">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="cf147-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf147-118">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf147-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf147-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cf147-119">See also</span></span>

- [<span data-ttu-id="cf147-120">ICorPublish — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cf147-120">ICorPublish Interface</span></span>](icorpublish-interface.md)
