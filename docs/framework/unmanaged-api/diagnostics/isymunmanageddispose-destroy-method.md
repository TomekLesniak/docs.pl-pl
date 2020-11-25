---
title: ISymUnmanagedDispose::Destroy — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose.Destroy
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type:
- apiref
ms.openlocfilehash: 6a31026f5b1669c0c29762048dc2c5c1c7bbb6a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732830"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="940f8-102">ISymUnmanagedDispose::Destroy — Metoda</span><span class="sxs-lookup"><span data-stu-id="940f8-102">ISymUnmanagedDispose::Destroy Method</span></span>

<span data-ttu-id="940f8-103">Powoduje, że obiekt źródłowy zwolni wszystkie odwołania wewnętrzne i zwróci niepowodzenie dla każdego kolejnego wywołania metody.</span><span class="sxs-lookup"><span data-stu-id="940f8-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="940f8-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="940f8-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="940f8-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="940f8-105">Return Value</span></span>  

 <span data-ttu-id="940f8-106">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="940f8-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="940f8-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="940f8-107">Requirements</span></span>  

 <span data-ttu-id="940f8-108">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="940f8-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="940f8-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="940f8-109">See also</span></span>

- [<span data-ttu-id="940f8-110">ISymUnmanagedDispose — Interfejs</span><span class="sxs-lookup"><span data-stu-id="940f8-110">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)
