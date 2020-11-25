---
title: ISymUnmanagedDocument::GetLanguageVendor — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
ms.openlocfilehash: bac0f187409a191dda1ef635ec9b2da1aee25981
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700954"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="ac775-102">ISymUnmanagedDocument::GetLanguageVendor — Metoda</span><span class="sxs-lookup"><span data-stu-id="ac775-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>

<span data-ttu-id="ac775-103">Pobiera dostawcę języka tego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="ac775-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac775-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ac775-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac775-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ac775-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="ac775-106">określoną Wskaźnik do zmiennej, która otrzymuje dostawcę języka.</span><span class="sxs-lookup"><span data-stu-id="ac775-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac775-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="ac775-107">Return Value</span></span>  

 <span data-ttu-id="ac775-108">S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="ac775-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac775-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ac775-109">See also</span></span>

- [<span data-ttu-id="ac775-110">ISymUnmanagedDocument — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ac775-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
