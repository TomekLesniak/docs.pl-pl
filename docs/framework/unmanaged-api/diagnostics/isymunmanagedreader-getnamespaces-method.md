---
title: ISymUnmanagedReader::GetNamespaces — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type:
- apiref
ms.openlocfilehash: c90cd0d21eca6875d3dae32e4ca80cf42e6140b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720597"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="9b2d0-102">ISymUnmanagedReader::GetNamespaces — Metoda</span><span class="sxs-lookup"><span data-stu-id="9b2d0-102">ISymUnmanagedReader::GetNamespaces Method</span></span>

<span data-ttu-id="9b2d0-103">Pobiera przestrzenie nazw zdefiniowane w globalnym zakresie w ramach tego magazynu symboli.</span><span class="sxs-lookup"><span data-stu-id="9b2d0-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b2d0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9b2d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b2d0-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="9b2d0-105">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="9b2d0-106">podczas Rozmiar tablicy przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="9b2d0-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="9b2d0-107">określoną Wskaźnik do zmiennej, która otrzymuje długość listy przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="9b2d0-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="9b2d0-108">określoną Wskaźnik do zmiennej, która otrzymuje listę przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="9b2d0-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b2d0-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="9b2d0-109">Return Value</span></span>  

 <span data-ttu-id="9b2d0-110">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="9b2d0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b2d0-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9b2d0-111">Requirements</span></span>  

 <span data-ttu-id="9b2d0-112">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="9b2d0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b2d0-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9b2d0-113">See also</span></span>

- [<span data-ttu-id="9b2d0-114">ISymUnmanagedReader — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9b2d0-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
