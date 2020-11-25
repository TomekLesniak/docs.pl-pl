---
title: COUNINITIEE — Wyliczenie
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
ms.openlocfilehash: b0f8c7e6d2acf4d4c080cc147bf6d42bf13cb51b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723834"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="d981b-102">COUNINITIEE — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="d981b-102">COUNINITIEE Enumeration</span></span>

<span data-ttu-id="d981b-103">Określa stałe używane przez [CoUninitializeEE —](../hosting/couninitializeee-function.md) podczas inicjowania środowiska uruchomieniowego języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="d981b-103">Specifies constants used by [CoUninitializeEE](../hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d981b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d981b-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="d981b-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="d981b-105">Members</span></span>  
  
|<span data-ttu-id="d981b-106">Członek</span><span class="sxs-lookup"><span data-stu-id="d981b-106">Member</span></span>|<span data-ttu-id="d981b-107">Opis</span><span class="sxs-lookup"><span data-stu-id="d981b-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="d981b-108">Wskazuje domyślny tryb uninicjującym.</span><span class="sxs-lookup"><span data-stu-id="d981b-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="d981b-109">Wskazuje tryb odinicjowania w przypadku zwalniania zestawu.</span><span class="sxs-lookup"><span data-stu-id="d981b-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d981b-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d981b-110">Requirements</span></span>  

 <span data-ttu-id="d981b-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d981b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d981b-112">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d981b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d981b-113">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d981b-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d981b-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d981b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d981b-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d981b-115">See also</span></span>

- [<span data-ttu-id="d981b-116">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="d981b-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
