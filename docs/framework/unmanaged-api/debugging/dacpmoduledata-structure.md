---
title: DacpModuleData, struktura
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 5d27ba2de9ff6ed184b6ddf50a517d0dae7715f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723054"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="54f7d-102">DacpModuleData, struktura</span><span class="sxs-lookup"><span data-stu-id="54f7d-102">DacpModuleData Structure</span></span>

<span data-ttu-id="54f7d-103">Definiuje bufor transportu dla informacji o środowisku uruchomieniowym modułu.</span><span class="sxs-lookup"><span data-stu-id="54f7d-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="54f7d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="54f7d-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="54f7d-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="54f7d-105">Members</span></span>

| <span data-ttu-id="54f7d-106">Członek</span><span class="sxs-lookup"><span data-stu-id="54f7d-106">Member</span></span>    | <span data-ttu-id="54f7d-107">Opis</span><span class="sxs-lookup"><span data-stu-id="54f7d-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="54f7d-108">Adres obiektu modułu.</span><span class="sxs-lookup"><span data-stu-id="54f7d-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="54f7d-109">Wskaźnik do przenośnego pliku wykonywalnego (PE).</span><span class="sxs-lookup"><span data-stu-id="54f7d-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="54f7d-110">Adres bazy załadowanego obrazu.</span><span class="sxs-lookup"><span data-stu-id="54f7d-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="54f7d-111">Bufor ładunku dla dodatkowych informacji modułu używanych przez środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="54f7d-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="54f7d-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="54f7d-112">Remarks</span></span>

<span data-ttu-id="54f7d-113">Ta struktura jest w czasie wykonywania i nie jest udostępniana za pomocą żadnych plików nagłówkowych ani bibliotek.</span><span class="sxs-lookup"><span data-stu-id="54f7d-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="54f7d-114">Aby go użyć, Zdefiniuj strukturę zgodnie z powyższym opisem.</span><span class="sxs-lookup"><span data-stu-id="54f7d-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="54f7d-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="54f7d-115">Requirements</span></span>

<span data-ttu-id="54f7d-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54f7d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="54f7d-117">**Nagłówek:** Dawaj</span><span class="sxs-lookup"><span data-stu-id="54f7d-117">**Header:** None</span></span>  
<span data-ttu-id="54f7d-118">**Biblioteka:** Dawaj</span><span class="sxs-lookup"><span data-stu-id="54f7d-118">**Library:** None</span></span>  
<span data-ttu-id="54f7d-119">**.NET Framework wersje:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="54f7d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="54f7d-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="54f7d-120">See also</span></span>

- [<span data-ttu-id="54f7d-121">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="54f7d-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="54f7d-122">Struktury debugowania</span><span class="sxs-lookup"><span data-stu-id="54f7d-122">Debugging Structures</span></span>](debugging-structures.md)
