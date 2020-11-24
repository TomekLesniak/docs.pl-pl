---
title: ICorPublishProcess::IsManaged — Metoda
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: dfe247bda75c3695c7c09b85729b4e057c13c62d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692634"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="70e8b-102">ICorPublishProcess::IsManaged — Metoda</span><span class="sxs-lookup"><span data-stu-id="70e8b-102">ICorPublishProcess::IsManaged Method</span></span>

<span data-ttu-id="70e8b-103">Pobiera wartość wskazującą, czy proces, do którego odwołuje się ten [ICorPublishProcess](icorpublishprocess-interface.md) , ma znany kod zarządzany.</span><span class="sxs-lookup"><span data-stu-id="70e8b-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70e8b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="70e8b-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70e8b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="70e8b-105">Parameters</span></span>  

 `pbManaged`  
 <span data-ttu-id="70e8b-106">określoną Wskaźnik do wartości logicznej wskazującej, czy proces ma kod zarządzany.</span><span class="sxs-lookup"><span data-stu-id="70e8b-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="70e8b-107">Wartość jest w `true` przypadku, gdy proces ma kod zarządzany; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="70e8b-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70e8b-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="70e8b-108">Remarks</span></span>  

 <span data-ttu-id="70e8b-109">Ponieważ bieżąca wersja programu `ICorPublishProcess` zezwala na dostęp tylko do procesów, które mają kod zarządzany, `IsManaged` zawsze zwraca `true` .</span><span class="sxs-lookup"><span data-stu-id="70e8b-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70e8b-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="70e8b-110">Requirements</span></span>  

 <span data-ttu-id="70e8b-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70e8b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70e8b-112">**Nagłówek:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="70e8b-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="70e8b-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="70e8b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70e8b-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70e8b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70e8b-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="70e8b-115">See also</span></span>

- [<span data-ttu-id="70e8b-116">ICorPublishProcess — Interfejs</span><span class="sxs-lookup"><span data-stu-id="70e8b-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
