---
title: ICorDebugThread::GetRegisterSet — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetRegisterSet
helpviewer_keywords:
- ICorDebugThread::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3b9b6260-98ac-4cfd-88e5-5d7614f94a0c
topic_type:
- apiref
ms.openlocfilehash: 7d3575909f54c8d676c9fd4246e6eac4a8a0ea1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727981"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="8d233-102">ICorDebugThread::GetRegisterSet — Metoda</span><span class="sxs-lookup"><span data-stu-id="8d233-102">ICorDebugThread::GetRegisterSet Method</span></span>

<span data-ttu-id="8d233-103">Pobiera wskaźnik interfejsu do zestawu rejestru, który jest skojarzony z aktywną częścią tego obiektu ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="8d233-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d233-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8d233-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d233-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="8d233-105">Parameters</span></span>  

 `ppRegisters`  
 <span data-ttu-id="8d233-106">określoną Wskaźnik do adresu obiektu interfejsu [ICorDebugRegisterSet](icordebugregisterset-interface.md) , który reprezentuje zestaw rejestru dla aktywnej części tego wątku.</span><span class="sxs-lookup"><span data-stu-id="8d233-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d233-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8d233-107">Requirements</span></span>  

 <span data-ttu-id="8d233-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d233-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d233-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8d233-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d233-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="8d233-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d233-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d233-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
