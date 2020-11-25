---
title: PreBindAssemblyEx — Funkcja
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
ms.openlocfilehash: a729249f7b0681941a0b1a478dbe2c0d9d6cd01c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723964"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="26fca-102">PreBindAssemblyEx — Funkcja</span><span class="sxs-lookup"><span data-stu-id="26fca-102">PreBindAssemblyEx Function</span></span>

<span data-ttu-id="26fca-103">Pobiera nazwę wyświetlaną dla zestawu.</span><span class="sxs-lookup"><span data-stu-id="26fca-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="26fca-104">Ta funkcja obsługuje infrastrukturę .NET Framework i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="26fca-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26fca-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="26fca-105">Syntax</span></span>  
  
```cpp  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="26fca-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="26fca-106">Parameters</span></span>  

 `pAppCtx`  
 <span data-ttu-id="26fca-107">podczas Identyfikuje kontekst aplikacji.</span><span class="sxs-lookup"><span data-stu-id="26fca-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="26fca-108">podczas Identyfikuje nazwę zestawu.</span><span class="sxs-lookup"><span data-stu-id="26fca-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="26fca-109">podczas Identyfikuje zestaw nadrzędny.</span><span class="sxs-lookup"><span data-stu-id="26fca-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="26fca-110">Ten parametr jest ignorowany.</span><span class="sxs-lookup"><span data-stu-id="26fca-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="26fca-111">podczas Identyfikuje wersję środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="26fca-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="26fca-112">określoną Zawiera nazwę wyświetlaną po wprowadzeniu zasad.</span><span class="sxs-lookup"><span data-stu-id="26fca-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="26fca-113">podczas Zarezerwowane do użytku w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="26fca-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="26fca-114">`pvReserved` musi być odwołaniem o wartości null.</span><span class="sxs-lookup"><span data-stu-id="26fca-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26fca-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="26fca-115">Remarks</span></span>  

 <span data-ttu-id="26fca-116">`ppNamePostPolicy`Parametr Output jest ustawiany tylko wtedy, gdy funkcja zwraca wartość HRESULT FUSION_E_REF_DEF_MISMATCH.</span><span class="sxs-lookup"><span data-stu-id="26fca-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="26fca-117">W przeciwnym razie ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="26fca-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26fca-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="26fca-118">Requirements</span></span>  

 <span data-ttu-id="26fca-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26fca-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26fca-120">**Nagłówek:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="26fca-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="26fca-121">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="26fca-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="26fca-122">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26fca-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26fca-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="26fca-123">See also</span></span>

- [<span data-ttu-id="26fca-124">Łączenie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="26fca-124">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
