---
title: ICLRMetaHost::EnumerateInstalledRuntimes — Metoda
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateInstalledRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type:
- apiref
ms.openlocfilehash: f8f67edde7f99878429ca0bbd89aaf52336aa79c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730451"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="67ddc-102">ICLRMetaHost::EnumerateInstalledRuntimes — Metoda</span><span class="sxs-lookup"><span data-stu-id="67ddc-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>

<span data-ttu-id="67ddc-103">Zwraca Wyliczenie zawierające prawidłowy Interfejs [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) dla każdej wersji środowiska uruchomieniowego języka wspólnego (CLR), która jest zainstalowana na komputerze.</span><span class="sxs-lookup"><span data-stu-id="67ddc-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67ddc-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="67ddc-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67ddc-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="67ddc-105">Parameters</span></span>  

 `ppEnumerator`  
 <span data-ttu-id="67ddc-106">określoną Wyliczenie interfejsów [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) odpowiadających każdej wersji środowiska CLR zainstalowanej na komputerze.</span><span class="sxs-lookup"><span data-stu-id="67ddc-106">[out] An enumeration of [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67ddc-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="67ddc-107">Return Value</span></span>  

 <span data-ttu-id="67ddc-108">Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="67ddc-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="67ddc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67ddc-109">HRESULT</span></span>|<span data-ttu-id="67ddc-110">Opis</span><span class="sxs-lookup"><span data-stu-id="67ddc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67ddc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="67ddc-111">S_OK</span></span>|<span data-ttu-id="67ddc-112">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="67ddc-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="67ddc-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="67ddc-113">E_POINTER</span></span>|<span data-ttu-id="67ddc-114">`ppEnumerator` ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="67ddc-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67ddc-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="67ddc-115">Requirements</span></span>  

 <span data-ttu-id="67ddc-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67ddc-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67ddc-117">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="67ddc-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="67ddc-118">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67ddc-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67ddc-119">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67ddc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ddc-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="67ddc-120">See also</span></span>

- [<span data-ttu-id="67ddc-121">ICLRMetaHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="67ddc-121">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="67ddc-122">Hosting</span><span class="sxs-lookup"><span data-stu-id="67ddc-122">Hosting</span></span>](index.md)
