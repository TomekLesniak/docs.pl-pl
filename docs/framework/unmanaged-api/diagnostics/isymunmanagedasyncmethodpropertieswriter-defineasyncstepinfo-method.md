---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo — Metoda
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: f8c77e44183fd92704aa91ca1cfd7e3fa68aa27f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719622"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="ad967-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo — Metoda</span><span class="sxs-lookup"><span data-stu-id="ad967-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>

<span data-ttu-id="ad967-103">Zdefiniuj grupę asynchronicznych operacji await w bieżącej metodzie.</span><span class="sxs-lookup"><span data-stu-id="ad967-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="ad967-104">Każde przesunięcie Yield pasuje do instrukcji return oczekującej, identyfikując potencjalną rentowność.</span><span class="sxs-lookup"><span data-stu-id="ad967-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="ad967-105">Każda `breakpointMethod` / `breakpointOffset` para informuje nas, gdzie zostanie wznowiona operacja asynchroniczna, która może znajdować się w innej metodzie.</span><span class="sxs-lookup"><span data-stu-id="ad967-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad967-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="ad967-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad967-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="ad967-107">Parameters</span></span>  
  
|<span data-ttu-id="ad967-108">Parametr</span><span class="sxs-lookup"><span data-stu-id="ad967-108">Parameter</span></span>|<span data-ttu-id="ad967-109">Opis</span><span class="sxs-lookup"><span data-stu-id="ad967-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="ad967-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="ad967-110">Return Value</span></span>  

 <span data-ttu-id="ad967-111">Zwraca wartość `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="ad967-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad967-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ad967-112">Requirements</span></span>  

 <span data-ttu-id="ad967-113">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ad967-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad967-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ad967-114">See also</span></span>

- [<span data-ttu-id="ad967-115">ISymUnmanagedAsyncMethodPropertiesWriter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ad967-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
