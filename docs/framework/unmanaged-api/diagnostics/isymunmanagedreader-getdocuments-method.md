---
title: ISymUnmanagedReader::GetDocuments — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocuments
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocuments
helpviewer_keywords:
- GetDocuments method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocuments method [.NET Framework debugging]
ms.assetid: e3b73a3f-d089-4101-a9a9-5e0765d05b61
topic_type:
- apiref
ms.openlocfilehash: 757b7fecbbb187da079c8a5c51462ec58431966f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707623"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="45d0f-102">ISymUnmanagedReader::GetDocuments — Metoda</span><span class="sxs-lookup"><span data-stu-id="45d0f-102">ISymUnmanagedReader::GetDocuments Method</span></span>

<span data-ttu-id="45d0f-103">Zwraca tablicę wszystkich dokumentów zdefiniowanych w magazynie symboli.</span><span class="sxs-lookup"><span data-stu-id="45d0f-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45d0f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="45d0f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45d0f-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="45d0f-105">Parameters</span></span>  

 `cDocs`  
 <span data-ttu-id="45d0f-106">podczas Rozmiar `pDocs` tablicy.</span><span class="sxs-lookup"><span data-stu-id="45d0f-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="45d0f-107">określoną Wskaźnik do zmiennej, która otrzymuje długość tablicy.</span><span class="sxs-lookup"><span data-stu-id="45d0f-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="45d0f-108">określoną Wskaźnik do zmiennej, która otrzymuje tablicę dokumentu.</span><span class="sxs-lookup"><span data-stu-id="45d0f-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45d0f-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="45d0f-109">Return Value</span></span>  

 <span data-ttu-id="45d0f-110">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="45d0f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45d0f-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="45d0f-111">Requirements</span></span>  

 <span data-ttu-id="45d0f-112">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="45d0f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d0f-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="45d0f-113">See also</span></span>

- [<span data-ttu-id="45d0f-114">ISymUnmanagedReader — Interfejs</span><span class="sxs-lookup"><span data-stu-id="45d0f-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
