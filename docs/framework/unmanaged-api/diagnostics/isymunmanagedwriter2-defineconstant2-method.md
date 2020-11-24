---
title: ISymUnmanagedWriter2::DefineConstant2 — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
ms.openlocfilehash: d45ab56f081bf0a8802b17e338f7b404809f0f16
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683475"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="3ca86-102">ISymUnmanagedWriter2::DefineConstant2 — Metoda</span><span class="sxs-lookup"><span data-stu-id="3ca86-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>

<span data-ttu-id="3ca86-103">Definiuje nazwę wartości stałej.</span><span class="sxs-lookup"><span data-stu-id="3ca86-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ca86-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3ca86-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ca86-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="3ca86-105">Parameters</span></span>  

 `name`  
 <span data-ttu-id="3ca86-106">podczas Stała nazwa.</span><span class="sxs-lookup"><span data-stu-id="3ca86-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="3ca86-107">podczas Wartość stałej.</span><span class="sxs-lookup"><span data-stu-id="3ca86-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="3ca86-108">podczas Token metadanych stałej.</span><span class="sxs-lookup"><span data-stu-id="3ca86-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ca86-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="3ca86-109">Return Value</span></span>  

 <span data-ttu-id="3ca86-110">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="3ca86-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ca86-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3ca86-111">Requirements</span></span>  

 <span data-ttu-id="3ca86-112">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3ca86-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca86-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3ca86-113">See also</span></span>

- [<span data-ttu-id="3ca86-114">ISymUnmanagedWriter2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3ca86-114">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="3ca86-115">DefineConstant, metoda</span><span class="sxs-lookup"><span data-stu-id="3ca86-115">DefineConstant Method</span></span>](isymunmanagedwriter-defineconstant-method.md)
