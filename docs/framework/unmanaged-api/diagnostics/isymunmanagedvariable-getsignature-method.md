---
title: ISymUnmanagedVariable::GetSignature — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
ms.openlocfilehash: 791b92c30fc2bf3d506113620b59ba20015e077e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725823"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="85813-102">ISymUnmanagedVariable::GetSignature — Metoda</span><span class="sxs-lookup"><span data-stu-id="85813-102">ISymUnmanagedVariable::GetSignature Method</span></span>

<span data-ttu-id="85813-103">Pobiera sygnaturę tej zmiennej.</span><span class="sxs-lookup"><span data-stu-id="85813-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85813-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="85813-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85813-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="85813-105">Parameters</span></span>  

 `cSig`  
 <span data-ttu-id="85813-106">podczas Długość buforu wskazywanego przez `sig` parametr.</span><span class="sxs-lookup"><span data-stu-id="85813-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="85813-107">określoną Wskaźnik do obiektu, `ULONG32` który odbiera rozmiar (w znakach) bufora wymaganego do zawierania podpisu.</span><span class="sxs-lookup"><span data-stu-id="85813-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="85813-108">określoną Bufor przechowujący podpis.</span><span class="sxs-lookup"><span data-stu-id="85813-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85813-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="85813-109">Return Value</span></span>  

 <span data-ttu-id="85813-110">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="85813-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85813-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="85813-111">Requirements</span></span>  

 <span data-ttu-id="85813-112">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="85813-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85813-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="85813-113">See also</span></span>

- [<span data-ttu-id="85813-114">ISymUnmanagedVariable — Interfejs</span><span class="sxs-lookup"><span data-stu-id="85813-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
