---
title: ISymENCUnmanagedMethod::GetLineFromOffset — Metoda
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
ms.openlocfilehash: 196993df9058d3eb8167e0144255c5fe366c54f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707363"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="af62e-102">ISymENCUnmanagedMethod::GetLineFromOffset — Metoda</span><span class="sxs-lookup"><span data-stu-id="af62e-102">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>

<span data-ttu-id="af62e-103">Pobiera informacje o wierszu skojarzone z przesunięciem.</span><span class="sxs-lookup"><span data-stu-id="af62e-103">Gets the line information associated with an offset.</span></span> <span data-ttu-id="af62e-104">Jeśli parametr offset ( `dwOffset` ) nie jest punktem sekwencji, ta metoda pobiera informacje o wierszu skojarzone z poprzednim przesunięcia.</span><span class="sxs-lookup"><span data-stu-id="af62e-104">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af62e-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="af62e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af62e-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="af62e-106">Parameters</span></span>  

 `dwOffset`  
 <span data-ttu-id="af62e-107">podczas A `ULONG32` , który zawiera przesunięcie.</span><span class="sxs-lookup"><span data-stu-id="af62e-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="af62e-108">określoną Wskaźnik do elementu `ULONG32` , który otrzymuje wiersz.</span><span class="sxs-lookup"><span data-stu-id="af62e-108">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="af62e-109">określoną Wskaźnik do elementu `ULONG32` , który odbiera kolumnę.</span><span class="sxs-lookup"><span data-stu-id="af62e-109">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="af62e-110">określoną Wskaźnik do elementu `ULONG32` , który odbiera linię końcową.</span><span class="sxs-lookup"><span data-stu-id="af62e-110">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="af62e-111">określoną Wskaźnik do elementu `ULONG32` , który odbiera kolumnę końcową.</span><span class="sxs-lookup"><span data-stu-id="af62e-111">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="af62e-112">określoną Wskaźnik do elementu `ULONG32` , który odbiera skojarzony punkt sekwencji.</span><span class="sxs-lookup"><span data-stu-id="af62e-112">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af62e-113">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="af62e-113">Return Value</span></span>  

 <span data-ttu-id="af62e-114">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="af62e-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af62e-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="af62e-115">Requirements</span></span>  

 <span data-ttu-id="af62e-116">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="af62e-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af62e-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="af62e-117">See also</span></span>

- [<span data-ttu-id="af62e-118">ISymENCUnmanagedMethod — Interfejs</span><span class="sxs-lookup"><span data-stu-id="af62e-118">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
