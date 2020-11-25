---
title: ISymUnmanagedReader::GetGlobalVariables — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetGlobalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetGlobalVariables
helpviewer_keywords:
- GetGlobalVariables method [.NET Framework debugging]
- ISymUnmanagedReader::GetGlobalVariables method [.NET Framework debugging]
ms.assetid: a2dd5098-3e58-4be5-b7a2-e4160b3b505a
topic_type:
- apiref
ms.openlocfilehash: 299787ea4eb8a5c25bdab64ad08445839c9f24d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707545"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="633d3-102">ISymUnmanagedReader::GetGlobalVariables — Metoda</span><span class="sxs-lookup"><span data-stu-id="633d3-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>

<span data-ttu-id="633d3-103">Zwraca wszystkie zmienne globalne.</span><span class="sxs-lookup"><span data-stu-id="633d3-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="633d3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="633d3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="633d3-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="633d3-105">Parameters</span></span>  

 `cVars`  
 <span data-ttu-id="633d3-106">podczas Długość buforu wskazywanego przez `pcVars` .</span><span class="sxs-lookup"><span data-stu-id="633d3-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="633d3-107">określoną Wskaźnik do obiektu `ULONG32` , który odbiera rozmiar buforu, który musi zawierać zmienne.</span><span class="sxs-lookup"><span data-stu-id="633d3-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="633d3-108">określoną Bufor zawierający zmienne.</span><span class="sxs-lookup"><span data-stu-id="633d3-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="633d3-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="633d3-109">Return Value</span></span>  

 <span data-ttu-id="633d3-110">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="633d3-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="633d3-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="633d3-111">Requirements</span></span>  

 <span data-ttu-id="633d3-112">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="633d3-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="633d3-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="633d3-113">See also</span></span>

- [<span data-ttu-id="633d3-114">ISymUnmanagedReader — Interfejs</span><span class="sxs-lookup"><span data-stu-id="633d3-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
