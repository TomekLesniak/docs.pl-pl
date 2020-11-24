---
title: ISymUnmanagedWriter::RemapToken — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
ms.openlocfilehash: 8799815f7c6c6aefc7081f3583e6fd174cd478f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683560"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="26089-102">ISymUnmanagedWriter::RemapToken — Metoda</span><span class="sxs-lookup"><span data-stu-id="26089-102">ISymUnmanagedWriter::RemapToken Method</span></span>

<span data-ttu-id="26089-103">Powiadamia moduł zapisujący symboli o tym, że token metadanych został ponownie zmapowany w miarę emitowania metadanych.</span><span class="sxs-lookup"><span data-stu-id="26089-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="26089-104">Jeśli moduł zapisujący symboli przechowuje stary token w magazynie symboli, musi zaktualizować przechowywany token nową wartością lub zapisać mapę dla odpowiedniego czytnika symboli do ponownego mapowania w fazie odczytu.</span><span class="sxs-lookup"><span data-stu-id="26089-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26089-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="26089-105">Syntax</span></span>  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26089-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="26089-106">Parameters</span></span>  

 `oldToken`  
 <span data-ttu-id="26089-107">podczas Token metadanych, który został ponownie zamapowany.</span><span class="sxs-lookup"><span data-stu-id="26089-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="26089-108">podczas Nowy token metadanych, który `oldToken` został ponownie zamapowany.</span><span class="sxs-lookup"><span data-stu-id="26089-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26089-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="26089-109">Return Value</span></span>  

 <span data-ttu-id="26089-110">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="26089-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26089-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="26089-111">Requirements</span></span>  

 <span data-ttu-id="26089-112">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="26089-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26089-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="26089-113">See also</span></span>

- [<span data-ttu-id="26089-114">ISymUnmanagedWriter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="26089-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
