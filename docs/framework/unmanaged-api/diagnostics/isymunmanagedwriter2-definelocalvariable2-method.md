---
title: ISymUnmanagedWriter2::DefineLocalVariable2 — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
ms.openlocfilehash: cdbb09d25f51e479a8a8ddfc23348305ba7c0a71
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683423"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="a777d-102">ISymUnmanagedWriter2::DefineLocalVariable2 — Metoda</span><span class="sxs-lookup"><span data-stu-id="a777d-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>

<span data-ttu-id="a777d-103">Definiuje pojedynczą zmienną w bieżącym zakresie leksykalnym.</span><span class="sxs-lookup"><span data-stu-id="a777d-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="a777d-104">Tę metodę można wywołać wiele razy dla zmiennej o tej samej nazwie, która ma wiele domów w całym zakresie.</span><span class="sxs-lookup"><span data-stu-id="a777d-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="a777d-105">Jednak w takim przypadku wartości `startOffset` `endOffset` parametrów i nie mogą nakładać się na siebie.</span><span class="sxs-lookup"><span data-stu-id="a777d-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a777d-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="a777d-106">Syntax</span></span>  
  
```cpp  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a777d-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="a777d-107">Parameters</span></span>  

 `name`  
 <span data-ttu-id="a777d-108">podczas Nazwa zmiennej lokalnej.</span><span class="sxs-lookup"><span data-stu-id="a777d-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="a777d-109">podczas Atrybuty zmiennej lokalnej.</span><span class="sxs-lookup"><span data-stu-id="a777d-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="a777d-110">podczas Token metadanych sygnatury.</span><span class="sxs-lookup"><span data-stu-id="a777d-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="a777d-111">podczas Typ adresu.</span><span class="sxs-lookup"><span data-stu-id="a777d-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="a777d-112">podczas Pierwszy adres dla specyfikacji parametru.</span><span class="sxs-lookup"><span data-stu-id="a777d-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="a777d-113">podczas Drugi adres dla specyfikacji parametru.</span><span class="sxs-lookup"><span data-stu-id="a777d-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="a777d-114">podczas Trzeci adres dla specyfikacji parametru.</span><span class="sxs-lookup"><span data-stu-id="a777d-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="a777d-115">podczas Przesunięcie początkowe dla zmiennej.</span><span class="sxs-lookup"><span data-stu-id="a777d-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="a777d-116">Ten parametr jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="a777d-116">This parameter is optional.</span></span> <span data-ttu-id="a777d-117">Jeśli wartość jest równa 0, ten parametr jest ignorowany, a zmienna jest zdefiniowana w całym zakresie.</span><span class="sxs-lookup"><span data-stu-id="a777d-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="a777d-118">Jeśli jest to wartość różna od zera, zmienna znajduje się w przesunięciach bieżącego zakresu.</span><span class="sxs-lookup"><span data-stu-id="a777d-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="a777d-119">podczas Przesunięcie końcowe dla zmiennej.</span><span class="sxs-lookup"><span data-stu-id="a777d-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="a777d-120">Ten parametr jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="a777d-120">This parameter is optional.</span></span> <span data-ttu-id="a777d-121">Jeśli wartość jest równa 0, ten parametr jest ignorowany, a zmienna jest zdefiniowana w całym zakresie.</span><span class="sxs-lookup"><span data-stu-id="a777d-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="a777d-122">Jeśli jest to wartość różna od zera, zmienna znajduje się w przesunięciach bieżącego zakresu.</span><span class="sxs-lookup"><span data-stu-id="a777d-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a777d-123">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="a777d-123">Return Value</span></span>  

 <span data-ttu-id="a777d-124">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="a777d-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a777d-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a777d-125">Requirements</span></span>  

 <span data-ttu-id="a777d-126">**Nagłówek:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="a777d-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a777d-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a777d-127">See also</span></span>

- [<span data-ttu-id="a777d-128">ISymUnmanagedWriter2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a777d-128">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="a777d-129">DefineLocalVariable, metoda</span><span class="sxs-lookup"><span data-stu-id="a777d-129">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
