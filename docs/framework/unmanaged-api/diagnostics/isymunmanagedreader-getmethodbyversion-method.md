---
title: ISymUnmanagedReader::GetMethodByVersion — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
ms.openlocfilehash: 64e6b9a1942e9a69e43de3d2f09564814328ec08
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689618"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="d817e-102">ISymUnmanagedReader::GetMethodByVersion — Metoda</span><span class="sxs-lookup"><span data-stu-id="d817e-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>

<span data-ttu-id="d817e-103">Pobiera metodę czytnika symboli, uwzględniając token metody i numer wersji do edycji i kopiowania.</span><span class="sxs-lookup"><span data-stu-id="d817e-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="d817e-104">Numery wersji zaczynają się od 1 i zwiększają się za każdym razem, gdy metoda zostanie zmieniona w wyniku operacji edycji i kopiowania.</span><span class="sxs-lookup"><span data-stu-id="d817e-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d817e-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="d817e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d817e-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="d817e-106">Parameters</span></span>  

 `token`  
 <span data-ttu-id="d817e-107">podczas Token metody.</span><span class="sxs-lookup"><span data-stu-id="d817e-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="d817e-108">podczas Wersja metody.</span><span class="sxs-lookup"><span data-stu-id="d817e-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d817e-109">określoną Wskaźnik do zwracanego interfejsu.</span><span class="sxs-lookup"><span data-stu-id="d817e-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d817e-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="d817e-110">Return Value</span></span>  

 <span data-ttu-id="d817e-111">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="d817e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d817e-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d817e-112">Requirements</span></span>  

 <span data-ttu-id="d817e-113">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d817e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d817e-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d817e-114">See also</span></span>

- [<span data-ttu-id="d817e-115">ISymUnmanagedReader — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d817e-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
