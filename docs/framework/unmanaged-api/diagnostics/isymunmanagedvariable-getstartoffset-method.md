---
title: ISymUnmanagedVariable::GetStartOffset — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
ms.openlocfilehash: 68d20c33c5ccd554554cae57ee55f6f51d5d980c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733311"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="60965-102">ISymUnmanagedVariable::GetStartOffset — Metoda</span><span class="sxs-lookup"><span data-stu-id="60965-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>

<span data-ttu-id="60965-103">Pobiera przesunięcie początku tej zmiennej w elemencie nadrzędnym.</span><span class="sxs-lookup"><span data-stu-id="60965-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="60965-104">Jeśli jest to zmienna lokalna w zakresie, przesunięcie rozpoczęcia będzie należeć do przesunięć zdefiniowanych dla zakresu.</span><span class="sxs-lookup"><span data-stu-id="60965-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60965-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="60965-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60965-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="60965-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="60965-107">określoną Wskaźnik do elementu `ULONG32` , który odbiera przesunięcie rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="60965-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60965-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="60965-108">Return Value</span></span>  

 <span data-ttu-id="60965-109">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="60965-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60965-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="60965-110">Requirements</span></span>  

 <span data-ttu-id="60965-111">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="60965-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60965-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="60965-112">See also</span></span>

- [<span data-ttu-id="60965-113">ISymUnmanagedVariable — Interfejs</span><span class="sxs-lookup"><span data-stu-id="60965-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="60965-114">GetEndOffset — Metoda</span><span class="sxs-lookup"><span data-stu-id="60965-114">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)
