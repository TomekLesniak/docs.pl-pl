---
title: ISymUnmanagedNamespace::GetName — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
ms.openlocfilehash: eca1137fb607d64e8645de5b0afc7ca391eac763
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699264"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="0e1f9-102">ISymUnmanagedNamespace::GetName — Metoda</span><span class="sxs-lookup"><span data-stu-id="0e1f9-102">ISymUnmanagedNamespace::GetName Method</span></span>

<span data-ttu-id="0e1f9-103">Pobiera nazwę tej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="0e1f9-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e1f9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0e1f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e1f9-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="0e1f9-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="0e1f9-106">podczas `ULONG32` Wskazuje rozmiar `szName` buforu.</span><span class="sxs-lookup"><span data-stu-id="0e1f9-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0e1f9-107">określoną Wskaźnik do obiektu, `ULONG32` który odbiera rozmiar (w znakach) bufora, który musi zawierać nazwę przestrzeni nazw, łącznie z zakończeniem o wartości null.</span><span class="sxs-lookup"><span data-stu-id="0e1f9-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="0e1f9-108">określoną Wskaźnik do buforu, który zawiera nazwę przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="0e1f9-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e1f9-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="0e1f9-109">Return Value</span></span>  

 <span data-ttu-id="0e1f9-110">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="0e1f9-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e1f9-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0e1f9-111">Requirements</span></span>  

 <span data-ttu-id="0e1f9-112">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0e1f9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e1f9-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0e1f9-113">See also</span></span>

- [<span data-ttu-id="0e1f9-114">ISymUnmanagedNamespace — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0e1f9-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
