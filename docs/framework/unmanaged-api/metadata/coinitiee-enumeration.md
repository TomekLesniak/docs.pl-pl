---
title: COINITIEE — Wyliczenie
ms.date: 03/30/2017
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
ms.openlocfilehash: 673450bb8209abede15e3cb65dd764b418073bc2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724198"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="5a1fa-102">COINITIEE — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5a1fa-102">COINITIEE Enumeration</span></span>

<span data-ttu-id="5a1fa-103">Określa stałe używane przez [CoInitializeEE —](../hosting/coinitializeee-function.md) podczas inicjowania środowiska uruchomieniowego języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="5a1fa-103">Specifies constants used by [CoInitializeEE](../hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a1fa-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5a1fa-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="5a1fa-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="5a1fa-105">Members</span></span>  
  
|<span data-ttu-id="5a1fa-106">Członek</span><span class="sxs-lookup"><span data-stu-id="5a1fa-106">Member</span></span>|<span data-ttu-id="5a1fa-107">Opis</span><span class="sxs-lookup"><span data-stu-id="5a1fa-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="5a1fa-108">Domyślny tryb inicjalizacji.</span><span class="sxs-lookup"><span data-stu-id="5a1fa-108">Default initialization mode.</span></span> <span data-ttu-id="5a1fa-109">Spowoduje to zainicjowanie środowiska uruchomieniowego i utworzenie domyślnego <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="5a1fa-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="5a1fa-110">Inicjuje się uruchamianie zarządzanej biblioteki DLL.</span><span class="sxs-lookup"><span data-stu-id="5a1fa-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="5a1fa-111">Jest inicjowany do uruchamiania zarządzanego pliku EXE.</span><span class="sxs-lookup"><span data-stu-id="5a1fa-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="5a1fa-112">Spowoduje to zainicjowanie środowiska uruchomieniowego, ale nie spowoduje utworzenia wartości domyślnej <xref:System.AppDomain> , która jest tworzona po wprowadzeniu głównej procedury pliku exe.</span><span class="sxs-lookup"><span data-stu-id="5a1fa-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a1fa-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5a1fa-113">Requirements</span></span>  

 <span data-ttu-id="5a1fa-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a1fa-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a1fa-115">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5a1fa-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a1fa-116">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a1fa-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a1fa-117">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a1fa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a1fa-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5a1fa-118">See also</span></span>

- [<span data-ttu-id="5a1fa-119">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="5a1fa-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
