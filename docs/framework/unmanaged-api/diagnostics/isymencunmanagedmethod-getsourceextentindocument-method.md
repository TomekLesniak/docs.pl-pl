---
title: ISymENCUnmanagedMethod::GetSourceExtentInDocument — Metoda
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
ms.openlocfilehash: 2cd362279f5c5ff281b9674fe3d1e293ddbab5f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707298"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="74ec7-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument — Metoda</span><span class="sxs-lookup"><span data-stu-id="74ec7-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>

<span data-ttu-id="74ec7-103">Pobiera najmniejszą linię początkową i największą linię końcową dla metody w określonym dokumencie.</span><span class="sxs-lookup"><span data-stu-id="74ec7-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74ec7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="74ec7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74ec7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="74ec7-105">Parameters</span></span>  

 `document`  
 <span data-ttu-id="74ec7-106">podczas Wskaźnik do dokumentu.</span><span class="sxs-lookup"><span data-stu-id="74ec7-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="74ec7-107">określoną Wskaźnik do elementu `ULONG32` , który odbiera linię początkową.</span><span class="sxs-lookup"><span data-stu-id="74ec7-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="74ec7-108">określoną Wskaźnik do elementu `ULONG32` , który odbiera linię końcową.</span><span class="sxs-lookup"><span data-stu-id="74ec7-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74ec7-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="74ec7-109">Return Value</span></span>  

 <span data-ttu-id="74ec7-110">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="74ec7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74ec7-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="74ec7-111">Requirements</span></span>  

 <span data-ttu-id="74ec7-112">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="74ec7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74ec7-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="74ec7-113">See also</span></span>

- [<span data-ttu-id="74ec7-114">ISymENCUnmanagedMethod — Interfejs</span><span class="sxs-lookup"><span data-stu-id="74ec7-114">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
