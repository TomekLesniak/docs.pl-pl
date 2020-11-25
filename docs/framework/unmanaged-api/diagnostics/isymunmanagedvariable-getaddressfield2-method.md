---
title: ISymUnmanagedVariable::GetAddressField2 — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField2
helpviewer_keywords:
- GetAddressField2 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField2 method [.NET Framework debugging]
ms.assetid: 1f25b294-72b6-4882-a49b-6c9d364b6008
topic_type:
- apiref
ms.openlocfilehash: 858341d5b8b1b3ecbe9dd5bd39a38f9cfd0d08dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714175"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="2a535-102">ISymUnmanagedVariable::GetAddressField2 — Metoda</span><span class="sxs-lookup"><span data-stu-id="2a535-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>

<span data-ttu-id="2a535-103">Pobiera drugie pole adresu dla tej zmiennej.</span><span class="sxs-lookup"><span data-stu-id="2a535-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="2a535-104">Jego znaczenie zależy od rodzaju adresu.</span><span class="sxs-lookup"><span data-stu-id="2a535-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a535-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="2a535-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a535-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="2a535-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="2a535-107">określoną Wskaźnik do elementu `ULONG32` , który odbiera drugie pole adresu.</span><span class="sxs-lookup"><span data-stu-id="2a535-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a535-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="2a535-108">Return Value</span></span>  

 <span data-ttu-id="2a535-109">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="2a535-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a535-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2a535-110">Requirements</span></span>  

 <span data-ttu-id="2a535-111">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="2a535-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a535-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2a535-112">See also</span></span>

- [<span data-ttu-id="2a535-113">ISymUnmanagedVariable — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2a535-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="2a535-114">GetAddressField1, metoda</span><span class="sxs-lookup"><span data-stu-id="2a535-114">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="2a535-115">GetAddressField3, metoda</span><span class="sxs-lookup"><span data-stu-id="2a535-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="2a535-116">GetAddressKind, metoda</span><span class="sxs-lookup"><span data-stu-id="2a535-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
