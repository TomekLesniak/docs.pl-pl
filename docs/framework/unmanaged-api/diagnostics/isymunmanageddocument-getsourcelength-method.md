---
title: ISymUnmanagedDocument::GetSourceLength — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
ms.openlocfilehash: c384fe6c4357c63bc56f9f9b1cc907dea64fddf7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700941"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="f0ce1-102">ISymUnmanagedDocument::GetSourceLength — Metoda</span><span class="sxs-lookup"><span data-stu-id="f0ce1-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>

<span data-ttu-id="f0ce1-103">Pobiera długość (w bajtach) osadzonego źródła.</span><span class="sxs-lookup"><span data-stu-id="f0ce1-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0ce1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f0ce1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0ce1-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f0ce1-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="f0ce1-106">określoną Wskaźnik do zmiennej, która wskazuje długość (w bajtach) osadzonego źródła.</span><span class="sxs-lookup"><span data-stu-id="f0ce1-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0ce1-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="f0ce1-107">Return Value</span></span>  

 <span data-ttu-id="f0ce1-108">S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="f0ce1-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0ce1-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f0ce1-109">See also</span></span>

- [<span data-ttu-id="f0ce1-110">ISymUnmanagedDocument — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f0ce1-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
