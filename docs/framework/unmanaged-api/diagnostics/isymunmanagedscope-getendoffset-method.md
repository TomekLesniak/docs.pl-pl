---
title: ISymUnmanagedScope::GetEndOffset — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
ms.openlocfilehash: 14e747e81e467019d464212e75513bdf98344916
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678366"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="c6dc1-102">ISymUnmanagedScope::GetEndOffset — Metoda</span><span class="sxs-lookup"><span data-stu-id="c6dc1-102">ISymUnmanagedScope::GetEndOffset Method</span></span>

<span data-ttu-id="c6dc1-103">Pobiera przesunięcie końca dla tego zakresu.</span><span class="sxs-lookup"><span data-stu-id="c6dc1-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6dc1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c6dc1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6dc1-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c6dc1-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="c6dc1-106">określoną Wskaźnik do elementu `ULONG32` , który odbiera przesunięcie końcowe.</span><span class="sxs-lookup"><span data-stu-id="c6dc1-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6dc1-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="c6dc1-107">Return Value</span></span>  

 <span data-ttu-id="c6dc1-108">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="c6dc1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6dc1-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c6dc1-109">Requirements</span></span>  

 <span data-ttu-id="c6dc1-110">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c6dc1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6dc1-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c6dc1-111">See also</span></span>

- [<span data-ttu-id="c6dc1-112">ISymUnmanagedScope — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c6dc1-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="c6dc1-113">GetStartOffset, metoda</span><span class="sxs-lookup"><span data-stu-id="c6dc1-113">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)
