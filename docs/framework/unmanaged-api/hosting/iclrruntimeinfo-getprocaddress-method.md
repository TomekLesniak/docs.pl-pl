---
title: ICLRRuntimeInfo::GetProcAddress — Metoda
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
ms.openlocfilehash: 028cfd51a713d8598598566a5b1edcf3fc70ecfc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732063"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="84f08-102">ICLRRuntimeInfo::GetProcAddress — Metoda</span><span class="sxs-lookup"><span data-stu-id="84f08-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>

<span data-ttu-id="84f08-103">Pobiera adres określonej funkcji, która została wyeksportowana z aparatu plików wykonywalnych języka wspólnego (CLR) skojarzonego z tym interfejsem.</span><span class="sxs-lookup"><span data-stu-id="84f08-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="84f08-104">Ta metoda zastępuje funkcję [GetRealProcAddress —](getrealprocaddress-function.md) .</span><span class="sxs-lookup"><span data-stu-id="84f08-104">This method supersedes the [GetRealProcAddress](getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84f08-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="84f08-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84f08-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="84f08-106">Parameters</span></span>  

 `pszProcName`  
 <span data-ttu-id="84f08-107">podczas Nazwa funkcji wyeksportowanej.</span><span class="sxs-lookup"><span data-stu-id="84f08-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="84f08-108">określoną Adres wyeksportowanej funkcji.</span><span class="sxs-lookup"><span data-stu-id="84f08-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84f08-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="84f08-109">Return Value</span></span>  

 <span data-ttu-id="84f08-110">Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="84f08-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="84f08-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84f08-111">HRESULT</span></span>|<span data-ttu-id="84f08-112">Opis</span><span class="sxs-lookup"><span data-stu-id="84f08-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84f08-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="84f08-113">S_OK</span></span>|<span data-ttu-id="84f08-114">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="84f08-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="84f08-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="84f08-115">E_POINTER</span></span>|<span data-ttu-id="84f08-116">`pszProcName` lub `ppProc` ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="84f08-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="84f08-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="84f08-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="84f08-118">Określona funkcja nie jest wyeksportowaną funkcją.</span><span class="sxs-lookup"><span data-stu-id="84f08-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84f08-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="84f08-119">Remarks</span></span>  

 <span data-ttu-id="84f08-120">Ta metoda powoduje załadowanie środowiska CLR, ale nie jego inicjalizację.</span><span class="sxs-lookup"><span data-stu-id="84f08-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84f08-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="84f08-121">Requirements</span></span>  

 <span data-ttu-id="84f08-122">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84f08-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84f08-123">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="84f08-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="84f08-124">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="84f08-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84f08-125">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84f08-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84f08-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="84f08-126">See also</span></span>

- [<span data-ttu-id="84f08-127">ICLRRuntimeInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="84f08-127">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="84f08-128">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="84f08-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="84f08-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="84f08-129">Hosting</span></span>](index.md)
