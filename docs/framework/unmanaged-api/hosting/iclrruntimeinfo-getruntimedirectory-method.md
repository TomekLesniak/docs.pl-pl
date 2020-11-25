---
title: ICLRRuntimeInfo::GetRuntimeDirectory — Metoda
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
ms.openlocfilehash: 24679118e4255282f7da3ff8be2ce9c08250e181
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732050"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="ac9b7-102">ICLRRuntimeInfo::GetRuntimeDirectory — Metoda</span><span class="sxs-lookup"><span data-stu-id="ac9b7-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>

<span data-ttu-id="ac9b7-103">Pobiera katalog instalacyjny środowiska uruchomieniowego języka wspólnego (CLR) skojarzonego z tym interfejsem.</span><span class="sxs-lookup"><span data-stu-id="ac9b7-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="ac9b7-104">Ta metoda zastępuje funkcję [GetCORSystemDirectory —](getcorsystemdirectory-function.md) w .NET Framework wersje 2,0, 3,0 i 3,5.</span><span class="sxs-lookup"><span data-stu-id="ac9b7-104">This method supersedes the [GetCORSystemDirectory](getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac9b7-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="ac9b7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac9b7-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="ac9b7-106">Parameters</span></span>  

 `pwzBuffer`  
 <span data-ttu-id="ac9b7-107">określoną Zwraca katalog instalacji środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="ac9b7-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="ac9b7-108">Ścieżka instalacji jest w pełni kwalifikowana; na przykład "c:\Windows\Microsoft.NET\Framework\v1.0.3705 \\ ".</span><span class="sxs-lookup"><span data-stu-id="ac9b7-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="ac9b7-109">[in. out] Określa rozmiar, `pwzBuffer` Aby zapobiec przekroczeniu buforu.</span><span class="sxs-lookup"><span data-stu-id="ac9b7-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="ac9b7-110">Jeśli `pwzBuffer` ma wartość null, `pchBuffer` zwraca wymagany rozmiar `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="ac9b7-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac9b7-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="ac9b7-111">Return Value</span></span>  

 <span data-ttu-id="ac9b7-112">Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="ac9b7-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ac9b7-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac9b7-113">HRESULT</span></span>|<span data-ttu-id="ac9b7-114">Opis</span><span class="sxs-lookup"><span data-stu-id="ac9b7-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac9b7-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac9b7-115">S_OK</span></span>|<span data-ttu-id="ac9b7-116">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="ac9b7-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="ac9b7-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ac9b7-117">E_POINTER</span></span>|<span data-ttu-id="ac9b7-118">`pwzBuffer` lub `pchBuffer` ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="ac9b7-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac9b7-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ac9b7-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac9b7-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ac9b7-120">Requirements</span></span>  

 <span data-ttu-id="ac9b7-121">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac9b7-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac9b7-122">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="ac9b7-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ac9b7-123">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac9b7-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac9b7-124">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac9b7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac9b7-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ac9b7-125">See also</span></span>

- [<span data-ttu-id="ac9b7-126">ICLRRuntimeInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ac9b7-126">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="ac9b7-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="ac9b7-127">Hosting</span></span>](index.md)
