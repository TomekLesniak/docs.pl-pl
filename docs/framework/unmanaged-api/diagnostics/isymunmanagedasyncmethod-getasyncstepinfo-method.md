---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo — Metoda
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
ms.openlocfilehash: f9392dae4119e59b4eb0fdb87e2b334b32b77109
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707259"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="41b66-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo — Metoda</span><span class="sxs-lookup"><span data-stu-id="41b66-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>

<span data-ttu-id="41b66-103">Zobacz [DefineAsyncStepInfo —](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="41b66-103">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41b66-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="41b66-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41b66-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="41b66-105">Parameters</span></span>  
  
|<span data-ttu-id="41b66-106">Parametr</span><span class="sxs-lookup"><span data-stu-id="41b66-106">Parameter</span></span>|<span data-ttu-id="41b66-107">Opis</span><span class="sxs-lookup"><span data-stu-id="41b66-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="41b66-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="41b66-108">Return Value</span></span>  

 <span data-ttu-id="41b66-109">Zwraca wartość `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="41b66-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41b66-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="41b66-110">Requirements</span></span>  

 <span data-ttu-id="41b66-111">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="41b66-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41b66-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="41b66-112">See also</span></span>

- [<span data-ttu-id="41b66-113">ISymUnmanagedAsyncMethod — Interfejs</span><span class="sxs-lookup"><span data-stu-id="41b66-113">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
