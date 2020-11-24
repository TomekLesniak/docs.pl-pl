---
title: NOTIFY_FILTER — Wyliczenie
ms.date: 03/30/2017
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
ms.openlocfilehash: 365bc0dc73b04d3afd171c40f336432f77552b6d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690957"
---
# <a name="notify_filter-enumeration"></a><span data-ttu-id="0a5db-102">NOTIFY_FILTER — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="0a5db-102">NOTIFY_FILTER Enumeration</span></span>

<span data-ttu-id="0a5db-103">Identyfikuje wywołania zwrotne dla funkcji debugera.</span><span class="sxs-lookup"><span data-stu-id="0a5db-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="0a5db-104">Aby uzyskać więcej informacji, zobacz metodę [INotifySource2:: SetNotifyFilter —](inotifysource2-setnotifyfilter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0a5db-104">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a5db-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="0a5db-105">Syntax</span></span>  
  
```cpp  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a><span data-ttu-id="0a5db-106">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="0a5db-106">Members</span></span>  
  
|<span data-ttu-id="0a5db-107">Członek</span><span class="sxs-lookup"><span data-stu-id="0a5db-107">Member</span></span>|<span data-ttu-id="0a5db-108">Opis</span><span class="sxs-lookup"><span data-stu-id="0a5db-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="0a5db-109">Wskazuje, że metoda [INotifySink2:: OnSyncCallOut —](inotifysink2-onsynccallout-method.md) powinna być wywoływana.</span><span class="sxs-lookup"><span data-stu-id="0a5db-109">Indicates that the [INotifySink2::OnSyncCallOut](inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="0a5db-110">Wskazuje, że metoda [INotifySink2:: OnSyncCallEnter —](inotifysink2-onsynccallenter-method.md) powinna być wywoływana.</span><span class="sxs-lookup"><span data-stu-id="0a5db-110">Indicates that the [INotifySink2::OnSyncCallEnter](inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="0a5db-111">Wskazuje, że metoda [INotifySink2:: OnSyncCallExit —](inotifysink2-onsynccallexit-method.md) powinna być wywoływana.</span><span class="sxs-lookup"><span data-stu-id="0a5db-111">Indicates that the [INotifySink2::OnSyncCallExit](inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="0a5db-112">Wskazuje, że metoda [INotifySink2:: OnSyncCallReturn —](inotifysink2-onsynccallreturn-method.md) powinna być wywoływana.</span><span class="sxs-lookup"><span data-stu-id="0a5db-112">Indicates that the [INotifySink2::OnSyncCallReturn](inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="0a5db-113">Wskazuje, że wszystkie metody [INotifySink2](inotifysink2-interface.md) powinny być wywoływane.</span><span class="sxs-lookup"><span data-stu-id="0a5db-113">Indicates that all of the [INotifySink2](inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="0a5db-114">Aktywuje wszystkie istniejące i przyszłe powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="0a5db-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="0a5db-115">Wskazuje, że nie powinny być wywoływane żadne metody powiadamiania.</span><span class="sxs-lookup"><span data-stu-id="0a5db-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0a5db-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0a5db-116">Requirements</span></span>  

 <span data-ttu-id="0a5db-117">**Nagłówek:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="0a5db-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a5db-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0a5db-118">See also</span></span>

- [<span data-ttu-id="0a5db-119">Wyliczenia magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="0a5db-119">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
