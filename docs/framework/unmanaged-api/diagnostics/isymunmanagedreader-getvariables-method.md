---
title: ISymUnmanagedReader::GetVariables — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type:
- apiref
ms.openlocfilehash: c4341a5ffe557694473ae505590b57d39a27a721
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675896"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="eeefa-102">ISymUnmanagedReader::GetVariables — Metoda</span><span class="sxs-lookup"><span data-stu-id="eeefa-102">ISymUnmanagedReader::GetVariables Method</span></span>

<span data-ttu-id="eeefa-103">Zwraca zmienną nielokalną, używając jej elementu nadrzędnego i nazwy.</span><span class="sxs-lookup"><span data-stu-id="eeefa-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeefa-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="eeefa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eeefa-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="eeefa-105">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="eeefa-106">podczas Element nadrzędny zmiennej.</span><span class="sxs-lookup"><span data-stu-id="eeefa-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="eeefa-107">podczas Rozmiar `pVars` tablicy.</span><span class="sxs-lookup"><span data-stu-id="eeefa-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="eeefa-108">określoną Wskaźnik do zmiennej, która otrzymuje liczbę zmiennych zwróconych w `pVars` .</span><span class="sxs-lookup"><span data-stu-id="eeefa-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="eeefa-109">określoną Wskaźnik do zmiennej, która odbiera zmienne.</span><span class="sxs-lookup"><span data-stu-id="eeefa-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eeefa-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="eeefa-110">Return Value</span></span>  

 <span data-ttu-id="eeefa-111">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="eeefa-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeefa-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="eeefa-112">Requirements</span></span>  

 <span data-ttu-id="eeefa-113">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="eeefa-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeefa-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="eeefa-114">See also</span></span>

- [<span data-ttu-id="eeefa-115">ISymUnmanagedReader — Interfejs</span><span class="sxs-lookup"><span data-stu-id="eeefa-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
