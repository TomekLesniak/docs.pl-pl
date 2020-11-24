---
title: ISymUnmanagedDocument::GetDocumentType — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetDocumentType
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetDocumentType
helpviewer_keywords:
- ISymUnmanagedDocument::GetDocumentType method [.NET Framework debugging]
- GetDocumentType method [.NET Framework debugging]
ms.assetid: 2d381ab1-7e7c-4281-af2b-e54d879b3ef8
topic_type:
- apiref
ms.openlocfilehash: d30ee9318d76aaf3ad2cde789ae292aed54f457e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689683"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="e6113-102">ISymUnmanagedDocument::GetDocumentType — Metoda</span><span class="sxs-lookup"><span data-stu-id="e6113-102">ISymUnmanagedDocument::GetDocumentType Method</span></span>

<span data-ttu-id="e6113-103">Pobiera typ dokumentu tego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="e6113-103">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6113-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e6113-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6113-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e6113-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="e6113-106">określoną Wskaźnik do zmiennej, która otrzymuje typ dokumentu.</span><span class="sxs-lookup"><span data-stu-id="e6113-106">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6113-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="e6113-107">Return Value</span></span>  

 <span data-ttu-id="e6113-108">S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="e6113-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6113-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e6113-109">See also</span></span>

- [<span data-ttu-id="e6113-110">ISymUnmanagedDocument — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e6113-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
