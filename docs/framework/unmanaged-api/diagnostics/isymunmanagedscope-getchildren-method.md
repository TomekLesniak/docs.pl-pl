---
title: ISymUnmanagedScope::GetChildren — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetChildren
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type:
- apiref
ms.openlocfilehash: 8f3c83a7a89553ba600f3e0e368eec0ddd0350e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727612"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="cbfe7-102">ISymUnmanagedScope::GetChildren — Metoda</span><span class="sxs-lookup"><span data-stu-id="cbfe7-102">ISymUnmanagedScope::GetChildren Method</span></span>

<span data-ttu-id="cbfe7-103">Pobiera elementy podrzędne tego zakresu.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbfe7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cbfe7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbfe7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="cbfe7-105">Parameters</span></span>  

 `cChildren`  
 <span data-ttu-id="cbfe7-106">podczas `ULONG32` Wskazuje rozmiar `children` tablicy.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="cbfe7-107">określoną Wskaźnik do obiektu `ULONG32` , który odbiera rozmiar buforu wymaganego do zawierania elementów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="cbfe7-108">określoną Zwracana tablica elementów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbfe7-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="cbfe7-109">Return Value</span></span>  

 <span data-ttu-id="cbfe7-110">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="cbfe7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbfe7-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cbfe7-111">Requirements</span></span>  

 <span data-ttu-id="cbfe7-112">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="cbfe7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbfe7-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cbfe7-113">See also</span></span>

- [<span data-ttu-id="cbfe7-114">ISymUnmanagedScope — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cbfe7-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="cbfe7-115">GetParent, metoda</span><span class="sxs-lookup"><span data-stu-id="cbfe7-115">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)
