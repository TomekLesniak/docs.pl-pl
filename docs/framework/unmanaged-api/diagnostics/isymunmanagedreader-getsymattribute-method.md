---
title: ISymUnmanagedReader::GetSymAttribute — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
ms.openlocfilehash: aa3b742babe4a94a43e4e6168dea67c0a0245eb0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720584"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="72a17-102">ISymUnmanagedReader::GetSymAttribute — Metoda</span><span class="sxs-lookup"><span data-stu-id="72a17-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>

<span data-ttu-id="72a17-103">Pobiera atrybut niestandardowy na podstawie jego nazwy.</span><span class="sxs-lookup"><span data-stu-id="72a17-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="72a17-104">W przeciwieństwie do atrybutów niestandardowych metadanych, te atrybuty niestandardowe są przechowywane w magazynie symboli.</span><span class="sxs-lookup"><span data-stu-id="72a17-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72a17-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="72a17-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72a17-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="72a17-106">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="72a17-107">podczas Token metadanych dla obiektu, dla którego żądany jest atrybut.</span><span class="sxs-lookup"><span data-stu-id="72a17-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="72a17-108">podczas Wskaźnik do zmiennej, która wskazuje atrybut do pobrania.</span><span class="sxs-lookup"><span data-stu-id="72a17-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="72a17-109">podczas Rozmiar `buffer` tablicy.</span><span class="sxs-lookup"><span data-stu-id="72a17-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="72a17-110">określoną Wskaźnik do zmiennej, która otrzymuje długość danych atrybutów.</span><span class="sxs-lookup"><span data-stu-id="72a17-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="72a17-111">określoną Wskaźnik do zmiennej, która otrzymuje dane atrybutu.</span><span class="sxs-lookup"><span data-stu-id="72a17-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72a17-112">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="72a17-112">Return Value</span></span>  

 <span data-ttu-id="72a17-113">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="72a17-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72a17-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="72a17-114">Requirements</span></span>  

 <span data-ttu-id="72a17-115">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="72a17-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72a17-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="72a17-116">See also</span></span>

- [<span data-ttu-id="72a17-117">ISymUnmanagedReader — Interfejs</span><span class="sxs-lookup"><span data-stu-id="72a17-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
