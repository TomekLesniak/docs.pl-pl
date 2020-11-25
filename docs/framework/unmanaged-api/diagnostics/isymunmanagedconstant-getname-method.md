---
title: ISymUnmanagedConstant::GetName — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
ms.openlocfilehash: fca7b11a83b5a695feae82fe5f25218f87afbce2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732895"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="72f42-102">ISymUnmanagedConstant::GetName — Metoda</span><span class="sxs-lookup"><span data-stu-id="72f42-102">ISymUnmanagedConstant::GetName Method</span></span>

<span data-ttu-id="72f42-103">Pobiera nazwę stałej.</span><span class="sxs-lookup"><span data-stu-id="72f42-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72f42-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="72f42-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72f42-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="72f42-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="72f42-106">podczas Długość buforu, `szName` do którego wskazuje parametr.</span><span class="sxs-lookup"><span data-stu-id="72f42-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="72f42-107">określoną Wskaźnik do obiektu, `ULONG32` który odbiera rozmiar (w znakach) bufora, który musi zawierać nazwę, łącznie z zakończeniem o wartości null.</span><span class="sxs-lookup"><span data-stu-id="72f42-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="72f42-108">określoną Bufor przechowujący nazwę.</span><span class="sxs-lookup"><span data-stu-id="72f42-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72f42-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="72f42-109">Return Value</span></span>  

 <span data-ttu-id="72f42-110">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="72f42-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72f42-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="72f42-111">Requirements</span></span>  

 <span data-ttu-id="72f42-112">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="72f42-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72f42-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="72f42-113">See also</span></span>

- [<span data-ttu-id="72f42-114">ISymUnmanagedConstant — Interfejs</span><span class="sxs-lookup"><span data-stu-id="72f42-114">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="72f42-115">GetSignature — Metoda</span><span class="sxs-lookup"><span data-stu-id="72f42-115">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="72f42-116">GetValue — Metoda</span><span class="sxs-lookup"><span data-stu-id="72f42-116">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)
