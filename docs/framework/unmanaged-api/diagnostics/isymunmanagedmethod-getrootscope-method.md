---
title: ISymUnmanagedMethod::GetRootScope — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
ms.openlocfilehash: 071738c8fb9b40457215e21172240aa7e77198cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699472"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="244f0-102">ISymUnmanagedMethod::GetRootScope — Metoda</span><span class="sxs-lookup"><span data-stu-id="244f0-102">ISymUnmanagedMethod::GetRootScope Method</span></span>

<span data-ttu-id="244f0-103">Pobiera zakres leksykalny głównej w ramach tej metody.</span><span class="sxs-lookup"><span data-stu-id="244f0-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="244f0-104">Ten zakres obejmuje całą metodę.</span><span class="sxs-lookup"><span data-stu-id="244f0-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="244f0-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="244f0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="244f0-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="244f0-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="244f0-107">określoną Wskaźnik, który jest ustawiony na zwracany Interfejs [ISymUnmanagedScope](isymunmanagedscope-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="244f0-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="244f0-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="244f0-108">Return Value</span></span>  

 <span data-ttu-id="244f0-109">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="244f0-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="244f0-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="244f0-110">Requirements</span></span>  

 <span data-ttu-id="244f0-111">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="244f0-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="244f0-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="244f0-112">See also</span></span>

- [<span data-ttu-id="244f0-113">ISymUnmanagedMethod — Interfejs</span><span class="sxs-lookup"><span data-stu-id="244f0-113">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
