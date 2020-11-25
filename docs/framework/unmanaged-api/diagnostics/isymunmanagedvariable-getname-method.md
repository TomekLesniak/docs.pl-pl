---
title: ISymUnmanagedVariable::GetName — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type:
- apiref
ms.openlocfilehash: f9da3ca8684da3bbc87146b3b52effdc4f91393d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726889"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="5cd13-102">ISymUnmanagedVariable::GetName — Metoda</span><span class="sxs-lookup"><span data-stu-id="5cd13-102">ISymUnmanagedVariable::GetName Method</span></span>

<span data-ttu-id="5cd13-103">Pobiera nazwę tej zmiennej.</span><span class="sxs-lookup"><span data-stu-id="5cd13-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cd13-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5cd13-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cd13-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="5cd13-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="5cd13-106">podczas Długość buforu, `pcchName` do którego wskazuje parametr.</span><span class="sxs-lookup"><span data-stu-id="5cd13-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5cd13-107">określoną Wskaźnik do obiektu, `ULONG32` który odbiera rozmiar (w znakach) bufora, który musi zawierać nazwę, łącznie z zakończeniem o wartości null.</span><span class="sxs-lookup"><span data-stu-id="5cd13-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="5cd13-108">określoną Bufor przechowujący nazwę.</span><span class="sxs-lookup"><span data-stu-id="5cd13-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5cd13-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="5cd13-109">Return Value</span></span>  

 <span data-ttu-id="5cd13-110">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="5cd13-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cd13-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5cd13-111">Requirements</span></span>  

 <span data-ttu-id="5cd13-112">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5cd13-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cd13-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5cd13-113">See also</span></span>

- [<span data-ttu-id="5cd13-114">ISymUnmanagedVariable — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5cd13-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
