---
title: FreeWin32ResBlob — Metoda
ms.date: 03/30/2017
api_name:
- IALink.FreeWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- FreeWin32ResBlob
helpviewer_keywords:
- FreeWin32ResBlob method
ms.assetid: d941102b-2679-4c49-b15e-c0fc9c53e11f
topic_type:
- apiref
ms.openlocfilehash: 44c5228f7ee467abd02a9ec09590d0352fc82036
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684762"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="c22a9-102">FreeWin32ResBlob — Metoda</span><span class="sxs-lookup"><span data-stu-id="c22a9-102">FreeWin32ResBlob Method</span></span>

<span data-ttu-id="c22a9-103">Zwalnia obiekt BLOB zasobów Win32 i skojarzone zasoby.</span><span class="sxs-lookup"><span data-stu-id="c22a9-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c22a9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c22a9-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c22a9-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c22a9-105">Parameters</span></span>  

 `ppResBlob`  
 <span data-ttu-id="c22a9-106">Obiekt BLOB zasobu do zwolnienia.</span><span class="sxs-lookup"><span data-stu-id="c22a9-106">The resource blob to be released.</span></span> <span data-ttu-id="c22a9-107">Ta metoda przypisuje wskaźnik obiektu BLOB do wartości NULL.</span><span class="sxs-lookup"><span data-stu-id="c22a9-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c22a9-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="c22a9-108">Return Value</span></span>  

 <span data-ttu-id="c22a9-109">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="c22a9-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c22a9-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c22a9-110">Requirements</span></span>  

 <span data-ttu-id="c22a9-111">Wymaga Alink. h</span><span class="sxs-lookup"><span data-stu-id="c22a9-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c22a9-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c22a9-112">See also</span></span>

- [<span data-ttu-id="c22a9-113">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c22a9-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c22a9-114">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c22a9-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c22a9-115">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="c22a9-115">ALink API</span></span>](index.md)
