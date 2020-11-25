---
title: ISymUnmanagedENCUpdate::UpdateMethodLines — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateMethodLines
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type:
- apiref
ms.openlocfilehash: 99499b8717f219616b6b368e6393b4b7ca0a79d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699589"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="4bfba-102">ISymUnmanagedENCUpdate::UpdateMethodLines — Metoda</span><span class="sxs-lookup"><span data-stu-id="4bfba-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>

<span data-ttu-id="4bfba-103">Umożliwia aktualizowanie informacji o wierszu dla metody, która nie została ponownie skompilowana, ale których linie nie zostały przesunięte niezależnie.</span><span class="sxs-lookup"><span data-stu-id="4bfba-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="4bfba-104">Różnicowa dla każdej instrukcji jest dozwolony.</span><span class="sxs-lookup"><span data-stu-id="4bfba-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bfba-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="4bfba-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bfba-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="4bfba-106">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="4bfba-107">podczas Metadane tokenu metody.</span><span class="sxs-lookup"><span data-stu-id="4bfba-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="4bfba-108">podczas Tablica `INT32` wartości, która wskazuje różnice dla każdego punktu sekwencji w metodzie.</span><span class="sxs-lookup"><span data-stu-id="4bfba-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="4bfba-109">podczas `ULONG` Zawierający rozmiar `pDeltas` parametru.</span><span class="sxs-lookup"><span data-stu-id="4bfba-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4bfba-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="4bfba-110">Return Value</span></span>  

 <span data-ttu-id="4bfba-111">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="4bfba-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bfba-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4bfba-112">Requirements</span></span>  

 <span data-ttu-id="4bfba-113">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="4bfba-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bfba-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4bfba-114">See also</span></span>

- [<span data-ttu-id="4bfba-115">ISymUnmanagedENCUpdate — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4bfba-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
