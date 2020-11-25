---
title: ISymUnmanagedVariable::GetAddressKind — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressKind
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressKind
helpviewer_keywords:
- GetAddressKind method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressKind method [.NET Framework debugging]
ms.assetid: a71563c0-62f2-4eb4-970c-825d61827613
topic_type:
- apiref
ms.openlocfilehash: 6a7824949edc905a3edcd58f60d40f8b1a40c53c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726915"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="6a5c3-102">ISymUnmanagedVariable::GetAddressKind — Metoda</span><span class="sxs-lookup"><span data-stu-id="6a5c3-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>

<span data-ttu-id="6a5c3-103">Pobiera rodzaj adresu tej zmiennej.</span><span class="sxs-lookup"><span data-stu-id="6a5c3-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a5c3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6a5c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a5c3-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="6a5c3-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="6a5c3-106">określoną Wskaźnik do elementu `ULONG32` , który otrzymuje wartość.</span><span class="sxs-lookup"><span data-stu-id="6a5c3-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="6a5c3-107">Możliwe wartości są zdefiniowane w wyliczeniu [CorSymAddrKind —](corsymaddrkind-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="6a5c3-107">The possible values are defined in the [CorSymAddrKind](corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a5c3-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="6a5c3-108">Return Value</span></span>  

 <span data-ttu-id="6a5c3-109">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="6a5c3-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a5c3-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6a5c3-110">Requirements</span></span>  

 <span data-ttu-id="6a5c3-111">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="6a5c3-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a5c3-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6a5c3-112">See also</span></span>

- [<span data-ttu-id="6a5c3-113">ISymUnmanagedVariable — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6a5c3-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
