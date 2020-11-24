---
title: ISymUnmanagedWriter2::DefineGlobalVariable2 — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
ms.openlocfilehash: e417854f5f82ba2e0f16848f53b2b605dccf9eb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683462"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="178dd-102">ISymUnmanagedWriter2::DefineGlobalVariable2 — Metoda</span><span class="sxs-lookup"><span data-stu-id="178dd-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>

<span data-ttu-id="178dd-103">Definiuje pojedynczą zmienną globalną.</span><span class="sxs-lookup"><span data-stu-id="178dd-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="178dd-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="178dd-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="178dd-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="178dd-105">Parameters</span></span>  

 `name`  
 <span data-ttu-id="178dd-106">podczas Nazwa zmiennej globalnej.</span><span class="sxs-lookup"><span data-stu-id="178dd-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="178dd-107">podczas Atrybuty zmiennej globalnej.</span><span class="sxs-lookup"><span data-stu-id="178dd-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="178dd-108">podczas Token metadanych sygnatury.</span><span class="sxs-lookup"><span data-stu-id="178dd-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="178dd-109">podczas Typ adresu.</span><span class="sxs-lookup"><span data-stu-id="178dd-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="178dd-110">podczas Pierwszy adres dla specyfikacji parametru.</span><span class="sxs-lookup"><span data-stu-id="178dd-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="178dd-111">podczas Drugi adres dla specyfikacji parametru.</span><span class="sxs-lookup"><span data-stu-id="178dd-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="178dd-112">podczas Trzeci adres dla specyfikacji parametru.</span><span class="sxs-lookup"><span data-stu-id="178dd-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="178dd-113">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="178dd-113">Return Value</span></span>  

 <span data-ttu-id="178dd-114">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="178dd-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="178dd-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="178dd-115">Requirements</span></span>  

 <span data-ttu-id="178dd-116">**Nagłówek:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="178dd-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="178dd-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="178dd-117">See also</span></span>

- [<span data-ttu-id="178dd-118">ISymUnmanagedWriter2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="178dd-118">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="178dd-119">DefineGlobalVariable, metoda</span><span class="sxs-lookup"><span data-stu-id="178dd-119">DefineGlobalVariable Method</span></span>](isymunmanagedwriter-defineglobalvariable-method.md)
