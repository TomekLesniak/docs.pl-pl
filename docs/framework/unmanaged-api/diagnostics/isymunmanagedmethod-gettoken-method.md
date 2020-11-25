---
title: ISymUnmanagedMethod::GetToken — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
ms.openlocfilehash: 76134a2447cbc40b5c97304540d9907648bc89e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719921"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="ba002-102">ISymUnmanagedMethod::GetToken — Metoda</span><span class="sxs-lookup"><span data-stu-id="ba002-102">ISymUnmanagedMethod::GetToken Method</span></span>

<span data-ttu-id="ba002-103">Zwraca token metadanych dla tej metody.</span><span class="sxs-lookup"><span data-stu-id="ba002-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba002-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ba002-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba002-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ba002-105">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="ba002-106">określoną Wskaźnik do obiektu, `mdMethodDef` który odbiera rozmiar (w znakach) bufora wymaganego do przechowywania metadanych.</span><span class="sxs-lookup"><span data-stu-id="ba002-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba002-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="ba002-107">Return Value</span></span>  

 <span data-ttu-id="ba002-108">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="ba002-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba002-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ba002-109">Requirements</span></span>  

 <span data-ttu-id="ba002-110">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ba002-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba002-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ba002-111">See also</span></span>

- [<span data-ttu-id="ba002-112">ISymUnmanagedMethod — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ba002-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
