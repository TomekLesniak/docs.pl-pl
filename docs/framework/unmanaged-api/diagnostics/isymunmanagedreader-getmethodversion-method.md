---
title: ISymUnmanagedReader::GetMethodVersion — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
ms.openlocfilehash: b0590f93c6a4c5ef28e03fc909c1f6a1474e5fad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720610"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="c4b1a-102">ISymUnmanagedReader::GetMethodVersion — Metoda</span><span class="sxs-lookup"><span data-stu-id="c4b1a-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>

<span data-ttu-id="c4b1a-103">Pobiera wersję metody.</span><span class="sxs-lookup"><span data-stu-id="c4b1a-103">Gets the method version.</span></span> <span data-ttu-id="c4b1a-104">Wersja metody zaczyna się od 1 i jest zwiększana za każdym razem, gdy metoda jest ponownie kompilowana.</span><span class="sxs-lookup"><span data-stu-id="c4b1a-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="c4b1a-105">Ponowna kompilacja może wystąpić bez zmian w metodzie.</span><span class="sxs-lookup"><span data-stu-id="c4b1a-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4b1a-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="c4b1a-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4b1a-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="c4b1a-107">Parameters</span></span>  

 `pMethod`  
 <span data-ttu-id="c4b1a-108">podczas Metoda, dla której ma zostać uzyskana wersja.</span><span class="sxs-lookup"><span data-stu-id="c4b1a-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="c4b1a-109">określoną Wskaźnik do zmiennej, która otrzymuje wersję metody.</span><span class="sxs-lookup"><span data-stu-id="c4b1a-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4b1a-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="c4b1a-110">Return Value</span></span>  

 <span data-ttu-id="c4b1a-111">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="c4b1a-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4b1a-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c4b1a-112">Requirements</span></span>  

 <span data-ttu-id="c4b1a-113">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c4b1a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b1a-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c4b1a-114">See also</span></span>

- [<span data-ttu-id="c4b1a-115">ISymUnmanagedReader — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c4b1a-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
