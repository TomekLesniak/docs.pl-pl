---
title: RUNTIME_INFO_FLAGS — Wyliczenie
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
ms.openlocfilehash: 6f4fbb40053628d60ba7f094fcb5d50a94d63e1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729944"
---
# <a name="runtime_info_flags-enumeration"></a><span data-ttu-id="4f36d-102">RUNTIME_INFO_FLAGS — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="4f36d-102">RUNTIME_INFO_FLAGS Enumeration</span></span>

<span data-ttu-id="4f36d-103">Zawiera wartości wskazujące, które informacje o środowisku uruchomieniowym języka wspólnego (CLR) powinny zostać zwrócone.</span><span class="sxs-lookup"><span data-stu-id="4f36d-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f36d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4f36d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="4f36d-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="4f36d-105">Members</span></span>  
  
|<span data-ttu-id="4f36d-106">Członek</span><span class="sxs-lookup"><span data-stu-id="4f36d-106">Member</span></span>|<span data-ttu-id="4f36d-107">Opis</span><span class="sxs-lookup"><span data-stu-id="4f36d-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="4f36d-108">Wskazuje, że informacje o katalogu nie powinny być uwzględniane.</span><span class="sxs-lookup"><span data-stu-id="4f36d-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="4f36d-109">Wskazuje, że informacja o wersji nie powinna być uwzględniona.</span><span class="sxs-lookup"><span data-stu-id="4f36d-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="4f36d-110">Wskazuje, że w przypadku błędu nie powinno być wyświetlane okno dialogowe błędu.</span><span class="sxs-lookup"><span data-stu-id="4f36d-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="4f36d-111">Wskazuje, że efekty wywołania funkcji [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) z flagą SEM_FAILCRITICALERRORS powinny zostać zastąpione.</span><span class="sxs-lookup"><span data-stu-id="4f36d-111">Indicates that the effects of calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="4f36d-112">Oznacza to, że w przypadku awarii zamiast pomijania należy wyświetlić okno dialogowe instalacji.</span><span class="sxs-lookup"><span data-stu-id="4f36d-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="4f36d-113">Wskazuje żądanie informacji o wersji środowiska uruchomieniowego zgodnej z AMD-64.</span><span class="sxs-lookup"><span data-stu-id="4f36d-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="4f36d-114">Wskazuje żądanie informacji o wersji środowiska uruchomieniowego zgodnej z systemem IA-64.</span><span class="sxs-lookup"><span data-stu-id="4f36d-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="4f36d-115">Wskazuje żądanie informacji o wersji środowiska uruchomieniowego zgodnej z architekturą x86.</span><span class="sxs-lookup"><span data-stu-id="4f36d-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="4f36d-116">Wskazuje, że należy uwzględnić informacje o uaktualnianiu wersji.</span><span class="sxs-lookup"><span data-stu-id="4f36d-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f36d-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4f36d-117">Remarks</span></span>  

 <span data-ttu-id="4f36d-118">Poniższe flagi architektury platformy można określić tylko po jednej naraz i nie można ich łączyć:</span><span class="sxs-lookup"><span data-stu-id="4f36d-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
- <span data-ttu-id="4f36d-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="4f36d-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="4f36d-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="4f36d-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="4f36d-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="4f36d-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f36d-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4f36d-122">Requirements</span></span>  

 <span data-ttu-id="4f36d-123">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f36d-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f36d-124">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4f36d-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f36d-125">**Biblioteka:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f36d-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f36d-126">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f36d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f36d-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4f36d-127">See also</span></span>

- [<span data-ttu-id="4f36d-128">Hosting — Wyliczenia</span><span class="sxs-lookup"><span data-stu-id="4f36d-128">Hosting Enumerations</span></span>](hosting-enumerations.md)
