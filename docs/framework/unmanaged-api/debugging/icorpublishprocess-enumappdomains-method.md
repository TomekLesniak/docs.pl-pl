---
title: ICorPublishProcess::EnumAppDomains — Metoda
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
ms.openlocfilehash: 2acf8fb507ab617e066a31c9c2657b1ef0d18e47
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693284"
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="b7174-102">ICorPublishProcess::EnumAppDomains — Metoda</span><span class="sxs-lookup"><span data-stu-id="b7174-102">ICorPublishProcess::EnumAppDomains Method</span></span>

<span data-ttu-id="b7174-103">Pobiera moduł wyliczający dla domen aplikacji w procesie, do którego odwołuje się ten [ICorPublishProcess](icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="b7174-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7174-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b7174-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7174-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b7174-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="b7174-106">określoną Wskaźnik do adresu wystąpienia [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) , który umożliwia iterację w kolekcji domen aplikacji w tym procesie.</span><span class="sxs-lookup"><span data-stu-id="b7174-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7174-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b7174-107">Remarks</span></span>  

 <span data-ttu-id="b7174-108">Lista domen aplikacji jest oparta na migawce domen aplikacji, które istnieją podczas `EnumAppDomains` wywoływania metody.</span><span class="sxs-lookup"><span data-stu-id="b7174-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="b7174-109">Ta metoda może być wywoływana więcej niż raz w celu utworzenia nowej listy aktualnych danych.</span><span class="sxs-lookup"><span data-stu-id="b7174-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="b7174-110">Kolejne wywołania tej metody nie będą miały wpływ na istniejące listy.</span><span class="sxs-lookup"><span data-stu-id="b7174-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="b7174-111">Jeśli proces został zakończony, zakończy `EnumAppDomains` się niepowodzeniem z wartością HRESULT równą CORDBG_E_PROCESS_TERMINATED.</span><span class="sxs-lookup"><span data-stu-id="b7174-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7174-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b7174-112">Requirements</span></span>  

 <span data-ttu-id="b7174-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7174-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7174-114">**Nagłówek:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="b7174-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b7174-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b7174-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7174-116">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7174-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7174-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b7174-117">See also</span></span>

- [<span data-ttu-id="b7174-118">ICorPublishProcess — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b7174-118">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
