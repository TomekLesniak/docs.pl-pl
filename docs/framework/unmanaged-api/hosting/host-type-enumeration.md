---
title: HOST_TYPE — Wyliczenie
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
ms.openlocfilehash: 31640ada28af8e35554b91d5931d427fbaa8dcbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721858"
---
# <a name="host_type-enumeration"></a><span data-ttu-id="557a9-102">HOST_TYPE — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="557a9-102">HOST_TYPE Enumeration</span></span>

<span data-ttu-id="557a9-103">Zawiera wartości określające typ hosta, który uruchamia aplikację.</span><span class="sxs-lookup"><span data-stu-id="557a9-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="557a9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="557a9-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="557a9-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="557a9-105">Members</span></span>  
  
|<span data-ttu-id="557a9-106">Członek</span><span class="sxs-lookup"><span data-stu-id="557a9-106">Member</span></span>|<span data-ttu-id="557a9-107">Opis</span><span class="sxs-lookup"><span data-stu-id="557a9-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="557a9-108">Uruchom aplikację z AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="557a9-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="557a9-109">Ta wartość jest używana w przypadku aplikacji częściowo zaufanych.</span><span class="sxs-lookup"><span data-stu-id="557a9-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="557a9-110">Uruchom aplikację bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="557a9-110">Launch the application directly.</span></span> <span data-ttu-id="557a9-111">Oznacza to, że należy uruchomić aplikację z własnego pliku. exe.</span><span class="sxs-lookup"><span data-stu-id="557a9-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="557a9-112">Ta wartość jest używana w przypadku w pełni zaufanych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="557a9-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="557a9-113">Taki sam jak HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="557a9-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="557a9-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="557a9-114">Requirements</span></span>  

 <span data-ttu-id="557a9-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="557a9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="557a9-116">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="557a9-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="557a9-117">**Biblioteka:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="557a9-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="557a9-118">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="557a9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="557a9-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="557a9-119">See also</span></span>

- [<span data-ttu-id="557a9-120">Hosting — Wyliczenia</span><span class="sxs-lookup"><span data-stu-id="557a9-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
