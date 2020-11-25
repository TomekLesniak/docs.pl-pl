---
title: ISymUnmanagedReader2::GetMethodByVersionPreRemap — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
ms.openlocfilehash: 5484242562deaf463b7435ad4e54735a7abee45e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730490"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="f2c8b-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap — Metoda</span><span class="sxs-lookup"><span data-stu-id="f2c8b-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>

<span data-ttu-id="f2c8b-103">Pobiera metodę czytnika symboli, używając tokenu metody oraz numeru wersji Edit-and-Continue.</span><span class="sxs-lookup"><span data-stu-id="f2c8b-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="f2c8b-104">Numery wersji zaczynają się od 1 i zwiększają się za każdym razem, gdy metoda zostanie zmieniona w wyniku operacji Edit-and-Continue.</span><span class="sxs-lookup"><span data-stu-id="f2c8b-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2c8b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="f2c8b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2c8b-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="f2c8b-106">Parameters</span></span>  

 `token`  
 <span data-ttu-id="f2c8b-107">podczas Token metadanych metody.</span><span class="sxs-lookup"><span data-stu-id="f2c8b-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="f2c8b-108">podczas Wersja metody.</span><span class="sxs-lookup"><span data-stu-id="f2c8b-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="f2c8b-109">określoną Wskaźnik do zwracanego interfejsu [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f2c8b-109">[out] A pointer to the returned [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2c8b-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="f2c8b-110">Return Value</span></span>  

 <span data-ttu-id="f2c8b-111">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="f2c8b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2c8b-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f2c8b-112">Requirements</span></span>  

 <span data-ttu-id="f2c8b-113">**Nagłówek:** CorSym. idl.</span><span class="sxs-lookup"><span data-stu-id="f2c8b-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="f2c8b-114">CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f2c8b-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2c8b-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f2c8b-115">See also</span></span>

- [<span data-ttu-id="f2c8b-116">ISymUnmanagedReader2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f2c8b-116">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
