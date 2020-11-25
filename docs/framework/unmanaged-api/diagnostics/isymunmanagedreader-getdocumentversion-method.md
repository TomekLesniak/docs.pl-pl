---
title: ISymUnmanagedReader::GetDocumentVersion — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
ms.openlocfilehash: fc38c167b47ea72c7bc7ad81074f9cb1a0d217d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707571"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="2994c-102">ISymUnmanagedReader::GetDocumentVersion — Metoda</span><span class="sxs-lookup"><span data-stu-id="2994c-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>

<span data-ttu-id="2994c-103">Pobiera określoną wersję określonego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="2994c-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="2994c-104">Wersja dokumentu zaczyna się od 1 i jest zwiększana za każdym razem, gdy dokument zostanie zaktualizowany przy użyciu metody [UpdateSymbolStore —](isymunmanagedreader-updatesymbolstore-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2994c-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="2994c-105">Jeśli `pbCurrent` parametr jest `true` , jest to Najnowsza wersja dokumentu.</span><span class="sxs-lookup"><span data-stu-id="2994c-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2994c-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="2994c-106">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2994c-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="2994c-107">Parameters</span></span>  

 `pDoc`  
 <span data-ttu-id="2994c-108">podczas Określony dokument.</span><span class="sxs-lookup"><span data-stu-id="2994c-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="2994c-109">określoną Wskaźnik do zmiennej, która otrzymuje wersję określonego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="2994c-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="2994c-110">określoną Wskaźnik do zmiennej, która otrzymuje `true` , jeśli jest to Najnowsza wersja dokumentu lub jeśli nie jest to `false` Najnowsza wersja.</span><span class="sxs-lookup"><span data-stu-id="2994c-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2994c-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="2994c-111">Return Value</span></span>  

 <span data-ttu-id="2994c-112">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="2994c-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2994c-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2994c-113">Requirements</span></span>  

 <span data-ttu-id="2994c-114">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="2994c-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2994c-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2994c-115">See also</span></span>

- [<span data-ttu-id="2994c-116">ISymUnmanagedReader — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2994c-116">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
