---
title: INotifySource2::SetNotifyFilter — Metoda
ms.date: 03/30/2017
api_name:
- INotifySource2.SetNotifyFilter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type:
- apiref
ms.openlocfilehash: 99bce831405d722f1f1ca0ae56e60f95f2d905e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719934"
---
# <a name="inotifysource2setnotifyfilter-method"></a><span data-ttu-id="7ba7b-102">INotifySource2::SetNotifyFilter — Metoda</span><span class="sxs-lookup"><span data-stu-id="7ba7b-102">INotifySource2::SetNotifyFilter Method</span></span>

<span data-ttu-id="7ba7b-103">Przypisuje filtr powiadomień do użycia z tym źródłem.</span><span class="sxs-lookup"><span data-stu-id="7ba7b-103">Assigns a notification filter for use with this source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ba7b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7ba7b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ba7b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7ba7b-105">Parameters</span></span>  

 `in_NotifyFilter`  
 <span data-ttu-id="7ba7b-106">podczas Bitowa kombinacja [NOTIFY_FILTER](notify-filter-enumeration.md) wartości wyliczenia, które identyfikują wywołania zwrotne dla interfejsu API debugera.</span><span class="sxs-lookup"><span data-stu-id="7ba7b-106">[in] A bitwise combination of the [NOTIFY_FILTER](notify-filter-enumeration.md) enumeration values that identify callbacks for the debugger API.</span></span>  
  
 `in_pUserThreadFilter`  
 <span data-ttu-id="7ba7b-107">podczas Wskaźnik do struktury [USER_THREAD](user-thread-structure.md) , który identyfikuje wątki dla interfejsu API debugera.</span><span class="sxs-lookup"><span data-stu-id="7ba7b-107">[in] A pointer to a [USER_THREAD](user-thread-structure.md) structure that identifies threads for the debugger API.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ba7b-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="7ba7b-108">Return Value</span></span>  

 <span data-ttu-id="7ba7b-109">S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="7ba7b-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ba7b-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7ba7b-110">Requirements</span></span>  

 <span data-ttu-id="7ba7b-111">**Nagłówek:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="7ba7b-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ba7b-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7ba7b-112">See also</span></span>

- [<span data-ttu-id="7ba7b-113">INotifySource2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7ba7b-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="7ba7b-114">INotifyConnection2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7ba7b-114">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="7ba7b-115">INotifySink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7ba7b-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
