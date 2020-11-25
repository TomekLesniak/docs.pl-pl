---
title: ISymUnmanagedWriter::DefineConstant — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
ms.openlocfilehash: 7c4589c3371d2c66279684a365cde102bef58c6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727591"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="b5767-102">ISymUnmanagedWriter::DefineConstant — Metoda</span><span class="sxs-lookup"><span data-stu-id="b5767-102">ISymUnmanagedWriter::DefineConstant Method</span></span>

<span data-ttu-id="b5767-103">Definiuje nazwę wartości stałej.</span><span class="sxs-lookup"><span data-stu-id="b5767-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5767-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b5767-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5767-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b5767-105">Parameters</span></span>  

 `name`  
 <span data-ttu-id="b5767-106">podczas Wskaźnik do elementu `WCHAR` , który definiuje stałą nazwę.</span><span class="sxs-lookup"><span data-stu-id="b5767-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="b5767-107">podczas Wartość stałej.</span><span class="sxs-lookup"><span data-stu-id="b5767-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="b5767-108">podczas Rozmiar `signature` tablicy.</span><span class="sxs-lookup"><span data-stu-id="b5767-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="b5767-109">podczas Podpis typu dla stałej.</span><span class="sxs-lookup"><span data-stu-id="b5767-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5767-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="b5767-110">Return Value</span></span>  

 <span data-ttu-id="b5767-111">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="b5767-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5767-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b5767-112">Requirements</span></span>  

 <span data-ttu-id="b5767-113">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b5767-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5767-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b5767-114">See also</span></span>

- [<span data-ttu-id="b5767-115">ISymUnmanagedWriter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b5767-115">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="b5767-116">DefineConstant2, metoda</span><span class="sxs-lookup"><span data-stu-id="b5767-116">DefineConstant2 Method</span></span>](isymunmanagedwriter2-defineconstant2-method.md)
