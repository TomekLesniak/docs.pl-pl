---
title: ISymUnmanagedMethod::GetSourceStartEnd — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
ms.openlocfilehash: f53afa5f87f1502f287b25e3d9756f9a54ad6869
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699290"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="55629-102">ISymUnmanagedMethod::GetSourceStartEnd — Metoda</span><span class="sxs-lookup"><span data-stu-id="55629-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>

<span data-ttu-id="55629-103">Pobiera położenie początku i końca dokumentu dla źródła tej metody.</span><span class="sxs-lookup"><span data-stu-id="55629-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="55629-104">Pierwsza pozycja tablicy jest początkowa, a druga pozycja tablicy to koniec.</span><span class="sxs-lookup"><span data-stu-id="55629-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55629-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="55629-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55629-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="55629-106">Parameters</span></span>  

 `docs`  
 <span data-ttu-id="55629-107">podczas Początkowe i końcowe dokumenty źródłowe.</span><span class="sxs-lookup"><span data-stu-id="55629-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="55629-108">podczas Początkowy i końcowy wierszy w odpowiednich dokumentach źródłowych.</span><span class="sxs-lookup"><span data-stu-id="55629-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="55629-109">podczas Kolumny początkowe i końcowe w odpowiednich dokumentach źródłowych.</span><span class="sxs-lookup"><span data-stu-id="55629-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="55629-110">[out] `true` Jeśli pozycje zostały zdefiniowane; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="55629-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55629-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="55629-111">Return Value</span></span>  

 <span data-ttu-id="55629-112">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="55629-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55629-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="55629-113">Requirements</span></span>  

 <span data-ttu-id="55629-114">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="55629-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55629-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="55629-115">See also</span></span>

- [<span data-ttu-id="55629-116">ISymUnmanagedMethod — Interfejs</span><span class="sxs-lookup"><span data-stu-id="55629-116">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
