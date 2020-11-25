---
title: ICLRRuntimeInfo::SetDefaultStartupFlags — Metoda
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
ms.openlocfilehash: 8020db491c3b66be38a9f6cbcb7551721859dcd5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723119"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="3ade2-102">ICLRRuntimeInfo::SetDefaultStartupFlags — Metoda</span><span class="sxs-lookup"><span data-stu-id="3ade2-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>

<span data-ttu-id="3ade2-103">Ustawia flagi uruchamiania i plik konfiguracji hosta, który zostanie użyty do uruchomienia środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="3ade2-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="3ade2-104">Ta metoda zastępuje użycie `startupFlags` parametru w funkcjach [CorBindToRuntimeEx](corbindtoruntimeex-function.md) i [CorBindToRuntimeHost —](corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="3ade2-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ade2-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="3ade2-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ade2-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="3ade2-106">Parameters</span></span>  

 `dwStartupFlags`  
 <span data-ttu-id="3ade2-107">podczas Flagi uruchamiania hosta do ustawienia.</span><span class="sxs-lookup"><span data-stu-id="3ade2-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="3ade2-108">Użyj tych samych flag co w przypadku funkcji [CorBindToRuntimeEx](corbindtoruntimeex-function.md) i [CorBindToRuntimeHost —](corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="3ade2-108">Use the same flags as with the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="3ade2-109">podczas Ścieżka katalogu pliku konfiguracji hosta do ustawienia.</span><span class="sxs-lookup"><span data-stu-id="3ade2-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ade2-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="3ade2-110">Return Value</span></span>  

 <span data-ttu-id="3ade2-111">Ta metoda zwraca następujące określone wartości HRESULT, a także błędy HRESULT wskazujące niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="3ade2-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3ade2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ade2-112">HRESULT</span></span>|<span data-ttu-id="3ade2-113">Opis</span><span class="sxs-lookup"><span data-stu-id="3ade2-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3ade2-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3ade2-114">S_OK</span></span>|<span data-ttu-id="3ade2-115">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="3ade2-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ade2-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3ade2-116">Remarks</span></span>  

 <span data-ttu-id="3ade2-117">Host wielowątkowy powinien synchronizować wywołania z tą metodą.</span><span class="sxs-lookup"><span data-stu-id="3ade2-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="3ade2-118">W przeciwnym razie wątek A może wywoływać `SetStartupFlags` metodę po zakończeniu wątku b zakończy wywołanie do `SetStartupFlags` i zanim wątek b uruchomi środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="3ade2-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ade2-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3ade2-119">Requirements</span></span>  

 <span data-ttu-id="3ade2-120">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ade2-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ade2-121">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="3ade2-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3ade2-122">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3ade2-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ade2-123">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ade2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ade2-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3ade2-124">See also</span></span>

- [<span data-ttu-id="3ade2-125">ICLRRuntimeInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3ade2-125">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="3ade2-126">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="3ade2-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="3ade2-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="3ade2-127">Hosting</span></span>](index.md)
