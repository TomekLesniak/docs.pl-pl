---
title: ISymUnmanagedScope::GetStartOffset — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
ms.openlocfilehash: 69b72ce66a203f403fcfe0fd4b4e728ece7397e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725875"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="7e384-102">ISymUnmanagedScope::GetStartOffset — Metoda</span><span class="sxs-lookup"><span data-stu-id="7e384-102">ISymUnmanagedScope::GetStartOffset Method</span></span>

<span data-ttu-id="7e384-103">Pobiera przesunięcie początku dla tego zakresu.</span><span class="sxs-lookup"><span data-stu-id="7e384-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e384-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7e384-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e384-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7e384-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="7e384-106">określoną Wskaźnik do elementu `ULONG32` , który zawiera przesunięcie początkowe.</span><span class="sxs-lookup"><span data-stu-id="7e384-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e384-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="7e384-107">Return Value</span></span>  

 <span data-ttu-id="7e384-108">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="7e384-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e384-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7e384-109">Requirements</span></span>  

 <span data-ttu-id="7e384-110">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7e384-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e384-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7e384-111">See also</span></span>

- [<span data-ttu-id="7e384-112">ISymUnmanagedScope — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7e384-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="7e384-113">GetEndOffset — Metoda</span><span class="sxs-lookup"><span data-stu-id="7e384-113">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)
