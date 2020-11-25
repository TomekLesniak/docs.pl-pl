---
title: ISymUnmanagedMethod::GetRanges — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
ms.openlocfilehash: 8ed492b573215736c82ab6c231cc5f2e188ea013
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732154"
---
# <a name="isymunmanagedmethodgetranges-method"></a><span data-ttu-id="eb7de-102">ISymUnmanagedMethod::GetRanges — Metoda</span><span class="sxs-lookup"><span data-stu-id="eb7de-102">ISymUnmanagedMethod::GetRanges Method</span></span>

<span data-ttu-id="eb7de-103">Nadana pozycja w dokumencie zwraca tablicę par przesunięć początkowych i końcowych odpowiadających zakresom języka pośredniego firmy Microsoft (MSIL), który znajduje się w tej metodzie.</span><span class="sxs-lookup"><span data-stu-id="eb7de-103">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span> <span data-ttu-id="eb7de-104">Tablica jest tablicą liczb całkowitych i ma format [początkowy, końcowy, początkowy, końcowy].</span><span class="sxs-lookup"><span data-stu-id="eb7de-104">The array is an array of integers and has the format [start, end, start, end].</span></span> <span data-ttu-id="eb7de-105">Liczba par zakresów jest długością tablicy podzieloną przez 2.</span><span class="sxs-lookup"><span data-stu-id="eb7de-105">The number of range pairs is the length of the array divided by 2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb7de-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="eb7de-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb7de-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="eb7de-107">Parameters</span></span>  

 `document`  
 <span data-ttu-id="eb7de-108">podczas Dokument, dla którego zażądano przesunięcia.</span><span class="sxs-lookup"><span data-stu-id="eb7de-108">[in] The document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="eb7de-109">podczas Wiersz dokumentu odpowiadający zakresom.</span><span class="sxs-lookup"><span data-stu-id="eb7de-109">[in] The document line corresponding to the ranges.</span></span>  
  
 `column`  
 <span data-ttu-id="eb7de-110">podczas Kolumna dokumentu odpowiadająca zakresom.</span><span class="sxs-lookup"><span data-stu-id="eb7de-110">[in] The document column corresponding to the ranges.</span></span>  
  
 `cRanges`  
 <span data-ttu-id="eb7de-111">podczas Rozmiar `ranges` tablicy.</span><span class="sxs-lookup"><span data-stu-id="eb7de-111">[in] The size of the `ranges` array.</span></span>  
  
 `pcRanges`  
 <span data-ttu-id="eb7de-112">określoną Wskaźnik do obiektu `ULONG32` , który odbiera rozmiar buforu wymaganego do przechowywania zakresów.</span><span class="sxs-lookup"><span data-stu-id="eb7de-112">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the ranges.</span></span>  
  
 `ranges`  
 <span data-ttu-id="eb7de-113">określoną Wskaźnik do buforu, który odbiera zakresy.</span><span class="sxs-lookup"><span data-stu-id="eb7de-113">[out] A pointer to the buffer that receives the ranges.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb7de-114">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="eb7de-114">Return Value</span></span>  

 <span data-ttu-id="eb7de-115">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="eb7de-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb7de-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="eb7de-116">Requirements</span></span>  

 <span data-ttu-id="eb7de-117">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="eb7de-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb7de-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="eb7de-118">See also</span></span>

- [<span data-ttu-id="eb7de-119">ISymUnmanagedMethod — Interfejs</span><span class="sxs-lookup"><span data-stu-id="eb7de-119">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
