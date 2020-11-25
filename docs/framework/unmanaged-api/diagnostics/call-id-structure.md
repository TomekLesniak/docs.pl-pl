---
title: CALL_ID — Struktura
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
ms.openlocfilehash: 3f41dd969e25f7a42308ff0b7b2d617344284b38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725251"
---
# <a name="call_id-structure"></a><span data-ttu-id="4a6ba-102">CALL_ID — Struktura</span><span class="sxs-lookup"><span data-stu-id="4a6ba-102">CALL_ID Structure</span></span>

<span data-ttu-id="4a6ba-103">Dostarcza informacje do debugera dotyczące funkcji, która jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="4a6ba-104">Aby uzyskać więcej informacji, zobacz Interfejs [INotifySink2](inotifysink2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4a6ba-104">See the [INotifySink2](inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a6ba-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="4a6ba-105">Syntax</span></span>  
  
```cpp  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a><span data-ttu-id="4a6ba-106">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="4a6ba-106">Members</span></span>  
  
|<span data-ttu-id="4a6ba-107">Członek</span><span class="sxs-lookup"><span data-stu-id="4a6ba-107">Member</span></span>|<span data-ttu-id="4a6ba-108">Opis</span><span class="sxs-lookup"><span data-stu-id="4a6ba-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="4a6ba-109">Identyfikuje maszynę, która wywołuje wywołanie.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="4a6ba-110">Identyfikuje procesor maszyny.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="4a6ba-111">Identyfikuje wątek wykonujący wywołanie.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="4a6ba-112">Określa adres stosu wywołań.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="4a6ba-113">Określa adres wywołania.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="4a6ba-114">Identyfikuje maszynę, która będzie wykonywać wywołanie.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a6ba-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4a6ba-115">Requirements</span></span>  

 <span data-ttu-id="4a6ba-116">**Nagłówek:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="4a6ba-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a6ba-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4a6ba-117">See also</span></span>

- [<span data-ttu-id="4a6ba-118">INotifySink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4a6ba-118">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="4a6ba-119">Struktury magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="4a6ba-119">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
