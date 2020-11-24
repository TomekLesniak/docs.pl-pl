---
title: ECustomDumpFlavor — Wyliczenie
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
ms.openlocfilehash: 1b8440ed6e878aac3dd08d9f8ed528c93739a724
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686322"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="acb92-102">ECustomDumpFlavor — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="acb92-102">ECustomDumpFlavor Enumeration</span></span>

<span data-ttu-id="acb92-103">Zawiera wartości wskazujące, które elementy mają być uwzględnione w niestandardowym podzestawie zrzutu sterty podczas raportowania błędów.</span><span class="sxs-lookup"><span data-stu-id="acb92-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acb92-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="acb92-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="acb92-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="acb92-105">Members</span></span>  
  
|<span data-ttu-id="acb92-106">Członek</span><span class="sxs-lookup"><span data-stu-id="acb92-106">Member</span></span>|<span data-ttu-id="acb92-107">Opis</span><span class="sxs-lookup"><span data-stu-id="acb92-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="acb92-108">Określa, że niestandardowy zrzut sterty powinien rozpoczynać się jako minizrzutu i dołączać dodatkowe dane określone przez wystąpienia [CustomDumpItem —](customdumpitem-structure.md) przesłane do tej samej metody.</span><span class="sxs-lookup"><span data-stu-id="acb92-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="acb92-109">Określa, że zrzut sterty niestandardowej ma zbierać wszystkie dane stanu czasu wykonywania, które nie były przydzielane dynamicznie.</span><span class="sxs-lookup"><span data-stu-id="acb92-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acb92-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="acb92-110">Remarks</span></span>  

 <span data-ttu-id="acb92-111">Parametr typu `ECustomDumpFlavor` jest przesyłany do metody [ICLRErrorReportingManager:: BeginCustomDump —](iclrerrorreportingmanager-begincustomdump-method.md) .</span><span class="sxs-lookup"><span data-stu-id="acb92-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acb92-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="acb92-112">Requirements</span></span>  

 <span data-ttu-id="acb92-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acb92-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acb92-114">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="acb92-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="acb92-115">**Biblioteka:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="acb92-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acb92-116">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acb92-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb92-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="acb92-117">See also</span></span>

- [<span data-ttu-id="acb92-118">ECustomDumpItemKind — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="acb92-118">ECustomDumpItemKind Enumeration</span></span>](ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="acb92-119">ICLRErrorReportingManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="acb92-119">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="acb92-120">Hosting — Wyliczenia</span><span class="sxs-lookup"><span data-stu-id="acb92-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
