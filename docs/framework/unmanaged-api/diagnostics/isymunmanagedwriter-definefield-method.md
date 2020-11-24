---
title: ISymUnmanagedWriter::DefineField — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
ms.openlocfilehash: 5683c10938873821cbe998dbf13937a6a7d24d7c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675090"
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="23781-102">ISymUnmanagedWriter::DefineField — Metoda</span><span class="sxs-lookup"><span data-stu-id="23781-102">ISymUnmanagedWriter::DefineField Method</span></span>

<span data-ttu-id="23781-103">Definiuje pojedynczą zmienną, która nie znajduje się w metodzie.</span><span class="sxs-lookup"><span data-stu-id="23781-103">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="23781-104">Ta metoda jest używana w przypadku niektórych pól klas, pól bitowych i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="23781-104">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23781-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="23781-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23781-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="23781-106">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="23781-107">podczas Typ metadanych lub token metody.</span><span class="sxs-lookup"><span data-stu-id="23781-107">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="23781-108">podczas Nazwa pola.</span><span class="sxs-lookup"><span data-stu-id="23781-108">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="23781-109">podczas Atrybuty pola.</span><span class="sxs-lookup"><span data-stu-id="23781-109">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="23781-110">podczas `ULONG32` Jest to rozmiar (w znakach) bufora, który musi zawierać sygnaturę pola.</span><span class="sxs-lookup"><span data-stu-id="23781-110">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="23781-111">podczas Tablica sygnatur pól.</span><span class="sxs-lookup"><span data-stu-id="23781-111">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="23781-112">podczas Typ adresu.</span><span class="sxs-lookup"><span data-stu-id="23781-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="23781-113">podczas Pierwszy adres dla specyfikacji pola.</span><span class="sxs-lookup"><span data-stu-id="23781-113">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="23781-114">podczas Drugi adres dla specyfikacji pola.</span><span class="sxs-lookup"><span data-stu-id="23781-114">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="23781-115">podczas Trzeci adres dla specyfikacji pola.</span><span class="sxs-lookup"><span data-stu-id="23781-115">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23781-116">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="23781-116">Return Value</span></span>  

 <span data-ttu-id="23781-117">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="23781-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23781-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="23781-118">Requirements</span></span>  

 <span data-ttu-id="23781-119">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="23781-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23781-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="23781-120">See also</span></span>

- [<span data-ttu-id="23781-121">ISymUnmanagedWriter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="23781-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
