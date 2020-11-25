---
title: ISymUnmanagedVariable::GetEndOffset — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
ms.openlocfilehash: cf4179f839b62409d5b2185f3e11e8e732c29187
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721871"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="c9878-102">ISymUnmanagedVariable::GetEndOffset — Metoda</span><span class="sxs-lookup"><span data-stu-id="c9878-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>

<span data-ttu-id="c9878-103">Pobiera przesunięcie końca tej zmiennej w elemencie nadrzędnym.</span><span class="sxs-lookup"><span data-stu-id="c9878-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="c9878-104">Jeśli jest to zmienna lokalna w zakresie, przesunięcie końcowe będzie należeć do przesunięć zdefiniowanych dla zakresu.</span><span class="sxs-lookup"><span data-stu-id="c9878-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9878-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="c9878-105">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9878-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="c9878-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="c9878-107">określoną Wskaźnik do elementu `ULONG32` , który odbiera przesunięcie końcowe.</span><span class="sxs-lookup"><span data-stu-id="c9878-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9878-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="c9878-108">Return Value</span></span>  

 <span data-ttu-id="c9878-109">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="c9878-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9878-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c9878-110">Requirements</span></span>  

 <span data-ttu-id="c9878-111">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c9878-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9878-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c9878-112">See also</span></span>

- [<span data-ttu-id="c9878-113">ISymUnmanagedVariable — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c9878-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="c9878-114">GetStartOffset, metoda</span><span class="sxs-lookup"><span data-stu-id="c9878-114">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)
