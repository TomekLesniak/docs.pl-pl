---
title: ISymUnmanagedENCUpdate::GetLocalVariableCount — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
ms.openlocfilehash: 19e07fb181f631335a0c56bd59b6fc8e14e2f36d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726928"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="64abf-102">ISymUnmanagedENCUpdate::GetLocalVariableCount — Metoda</span><span class="sxs-lookup"><span data-stu-id="64abf-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>

<span data-ttu-id="64abf-103">Pobiera liczbę zmiennych lokalnych.</span><span class="sxs-lookup"><span data-stu-id="64abf-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64abf-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="64abf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64abf-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="64abf-105">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="64abf-106">podczas Token metadanych metod.</span><span class="sxs-lookup"><span data-stu-id="64abf-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="64abf-107">określoną Wskaźnik do obiektu, `ULONG32` który odbiera rozmiar (w znakach) bufora wymaganego do przechowywania liczby zmiennych lokalnych.</span><span class="sxs-lookup"><span data-stu-id="64abf-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64abf-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="64abf-108">Return Value</span></span>  

 <span data-ttu-id="64abf-109">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="64abf-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64abf-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="64abf-110">Requirements</span></span>  

 <span data-ttu-id="64abf-111">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="64abf-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64abf-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="64abf-112">See also</span></span>

- [<span data-ttu-id="64abf-113">ISymUnmanagedENCUpdate — Interfejs</span><span class="sxs-lookup"><span data-stu-id="64abf-113">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
