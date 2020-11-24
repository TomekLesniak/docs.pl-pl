---
title: ISymUnmanagedReader::Initialize — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
ms.openlocfilehash: 6193d91c8cbe0efa7cd68b97b9262acf72c9ea0b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675883"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="6a3c8-102">ISymUnmanagedReader::Initialize — Metoda</span><span class="sxs-lookup"><span data-stu-id="6a3c8-102">ISymUnmanagedReader::Initialize Method</span></span>

<span data-ttu-id="6a3c8-103">Inicjuje czytnik symboli z interfejsem importera metadanych, z którym zostanie skojarzony ten czytnik, wraz z nazwą pliku modułu.</span><span class="sxs-lookup"><span data-stu-id="6a3c8-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a3c8-104">Tę metodę można wywołać tylko raz i muszą one zostać wywołane przed innymi metodami czytnika.</span><span class="sxs-lookup"><span data-stu-id="6a3c8-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a3c8-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="6a3c8-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a3c8-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="6a3c8-106">Parameters</span></span>  

 `importer`  
 <span data-ttu-id="6a3c8-107">podczas Interfejs programu do importowania metadanych, z którym ten czytnik zostanie skojarzony.</span><span class="sxs-lookup"><span data-stu-id="6a3c8-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="6a3c8-108">podczas Nazwa pliku modułu.</span><span class="sxs-lookup"><span data-stu-id="6a3c8-108">[in] The file name of the module.</span></span> <span data-ttu-id="6a3c8-109">Zamiast tego można użyć `pIStream` parametru.</span><span class="sxs-lookup"><span data-stu-id="6a3c8-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="6a3c8-110">podczas Ścieżka do wyszukania.</span><span class="sxs-lookup"><span data-stu-id="6a3c8-110">[in] The path to search.</span></span> <span data-ttu-id="6a3c8-111">Ten parametr jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="6a3c8-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="6a3c8-112">podczas Strumień pliku używany jako alternatywa dla parametru filename.</span><span class="sxs-lookup"><span data-stu-id="6a3c8-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a3c8-113">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="6a3c8-113">Return Value</span></span>  

 <span data-ttu-id="6a3c8-114">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="6a3c8-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a3c8-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6a3c8-115">Remarks</span></span>  

 <span data-ttu-id="6a3c8-116">Należy określić tylko jeden z `filename` `pIStream` parametrów lub.</span><span class="sxs-lookup"><span data-stu-id="6a3c8-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="6a3c8-117">`searchPath`Parametr jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="6a3c8-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a3c8-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6a3c8-118">Requirements</span></span>  

 <span data-ttu-id="6a3c8-119">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="6a3c8-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a3c8-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6a3c8-120">See also</span></span>

- [<span data-ttu-id="6a3c8-121">ISymUnmanagedReader — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6a3c8-121">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
