---
title: ISymUnmanagedConstant::GetValue — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
ms.openlocfilehash: 7a1c795f4a162699078e91bcaa274253169234e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732843"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="26bf9-102">ISymUnmanagedConstant::GetValue — Metoda</span><span class="sxs-lookup"><span data-stu-id="26bf9-102">ISymUnmanagedConstant::GetValue Method</span></span>

<span data-ttu-id="26bf9-103">Pobiera wartość stałej.</span><span class="sxs-lookup"><span data-stu-id="26bf9-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26bf9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="26bf9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26bf9-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="26bf9-105">Parameters</span></span>  

 `pValue`  
 <span data-ttu-id="26bf9-106">określoną Wskaźnik do zmiennej, która otrzymuje wartość.</span><span class="sxs-lookup"><span data-stu-id="26bf9-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26bf9-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="26bf9-107">Return Value</span></span>  

 <span data-ttu-id="26bf9-108">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="26bf9-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26bf9-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="26bf9-109">Requirements</span></span>  

 <span data-ttu-id="26bf9-110">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="26bf9-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26bf9-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="26bf9-111">See also</span></span>

- [<span data-ttu-id="26bf9-112">ISymUnmanagedConstant — Interfejs</span><span class="sxs-lookup"><span data-stu-id="26bf9-112">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="26bf9-113">GetName — Metoda</span><span class="sxs-lookup"><span data-stu-id="26bf9-113">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="26bf9-114">GetSignature — Metoda</span><span class="sxs-lookup"><span data-stu-id="26bf9-114">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
