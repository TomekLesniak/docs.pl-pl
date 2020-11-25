---
title: USER_THREAD — Struktura
ms.date: 03/30/2017
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
ms.openlocfilehash: 409651aa69e957418ad46f61e1bd57add0eb10a6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722898"
---
# <a name="user_thread-structure"></a><span data-ttu-id="01bce-102">USER_THREAD — Struktura</span><span class="sxs-lookup"><span data-stu-id="01bce-102">USER_THREAD Structure</span></span>

<span data-ttu-id="01bce-103">Zawiera informacje dotyczące debugera wątku.</span><span class="sxs-lookup"><span data-stu-id="01bce-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="01bce-104">Aby uzyskać więcej informacji, zobacz metodę [INotifySource2:: SetNotifyFilter —](inotifysource2-setnotifyfilter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="01bce-104">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01bce-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="01bce-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="01bce-106">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="01bce-106">Members</span></span>  
  
|<span data-ttu-id="01bce-107">Członek</span><span class="sxs-lookup"><span data-stu-id="01bce-107">Member</span></span>|<span data-ttu-id="01bce-108">Opis</span><span class="sxs-lookup"><span data-stu-id="01bce-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="01bce-109">Adres buforu wątku.</span><span class="sxs-lookup"><span data-stu-id="01bce-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="01bce-110">Długość buforu wątku w bajtach.</span><span class="sxs-lookup"><span data-stu-id="01bce-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="01bce-111">Identyfikator wątku.</span><span class="sxs-lookup"><span data-stu-id="01bce-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01bce-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="01bce-112">Requirements</span></span>  

 <span data-ttu-id="01bce-113">**Nagłówek:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="01bce-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01bce-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="01bce-114">See also</span></span>

- [<span data-ttu-id="01bce-115">SetNotifyFilter, metoda</span><span class="sxs-lookup"><span data-stu-id="01bce-115">SetNotifyFilter Method</span></span>](inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="01bce-116">Struktury magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="01bce-116">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
