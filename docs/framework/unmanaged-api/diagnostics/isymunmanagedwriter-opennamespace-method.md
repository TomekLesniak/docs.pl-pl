---
title: ISymUnmanagedWriter::OpenNamespace — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
ms.openlocfilehash: 2f64f9f4bde3119f9f089becec5a36d69ed43596
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730064"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="328d8-102">ISymUnmanagedWriter::OpenNamespace — Metoda</span><span class="sxs-lookup"><span data-stu-id="328d8-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>

<span data-ttu-id="328d8-103">Otwiera nową przestrzeń nazw.</span><span class="sxs-lookup"><span data-stu-id="328d8-103">Opens a new namespace.</span></span> <span data-ttu-id="328d8-104">Wywołaj tę metodę przed zdefiniowaniem metod lub zmiennych, które zajmują przestrzeń nazw.</span><span class="sxs-lookup"><span data-stu-id="328d8-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="328d8-105">Przestrzenie nazw mogą być zagnieżdżane.</span><span class="sxs-lookup"><span data-stu-id="328d8-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="328d8-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="328d8-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="328d8-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="328d8-107">Parameters</span></span>  

 `name`  
 <span data-ttu-id="328d8-108">podczas Wskaźnik do nazwy nowej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="328d8-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="328d8-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="328d8-109">Return Value</span></span>  

 <span data-ttu-id="328d8-110">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="328d8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="328d8-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="328d8-111">Requirements</span></span>  

 <span data-ttu-id="328d8-112">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="328d8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="328d8-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="328d8-113">See also</span></span>

- [<span data-ttu-id="328d8-114">ISymUnmanagedWriter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="328d8-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="328d8-115">CloseNamespace, metoda</span><span class="sxs-lookup"><span data-stu-id="328d8-115">CloseNamespace Method</span></span>](isymunmanagedwriter-closenamespace-method.md)
