---
title: CoInitializeEE — Funkcja
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
ms.openlocfilehash: 707e182e62f4a7b7b813e6b288c6825b0d3d2eab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731756"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="ec7ca-102">CoInitializeEE — Funkcja</span><span class="sxs-lookup"><span data-stu-id="ec7ca-102">CoInitializeEE Function</span></span>

<span data-ttu-id="ec7ca-103">Zapewnia, że aparat wykonywania środowiska uruchomieniowego języka wspólnego jest ładowany do procesu.</span><span class="sxs-lookup"><span data-stu-id="ec7ca-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="ec7ca-104">Ta funkcja jest przestarzała w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ec7ca-104">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="ec7ca-105">Zamiast tego użyj metody [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ec7ca-105">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec7ca-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="ec7ca-106">Syntax</span></span>  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec7ca-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="ec7ca-107">Parameters</span></span>  

 `fFlags`  
 <span data-ttu-id="ec7ca-108">podczas Jedna ze stałych wyliczenia [COINITIEE —](../metadata/coinitiee-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ec7ca-108">[in] One of the [COINITIEE](../metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec7ca-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="ec7ca-109">Return Value</span></span>  

 <span data-ttu-id="ec7ca-110">Ta metoda zwraca standardowe kody błędów COM zdefiniowane w Winerror. h i wartości w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="ec7ca-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="ec7ca-111">Kod powrotu</span><span class="sxs-lookup"><span data-stu-id="ec7ca-111">Return code</span></span>|<span data-ttu-id="ec7ca-112">Opis</span><span class="sxs-lookup"><span data-stu-id="ec7ca-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ec7ca-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ec7ca-113">S_OK</span></span>|<span data-ttu-id="ec7ca-114">Aparat wykonywania został załadowany pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="ec7ca-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="ec7ca-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ec7ca-115">S_FALSE</span></span>|<span data-ttu-id="ec7ca-116">Aparat wykonywania został już załadowany.</span><span class="sxs-lookup"><span data-stu-id="ec7ca-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="ec7ca-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ec7ca-117">E_FAIL</span></span>|<span data-ttu-id="ec7ca-118">Nie można załadować aparatu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="ec7ca-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec7ca-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ec7ca-119">Remarks</span></span>  

 <span data-ttu-id="ec7ca-120">Ta metoda ładuje aparat wykonywania, jeśli nie został wcześniej załadowany.</span><span class="sxs-lookup"><span data-stu-id="ec7ca-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec7ca-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ec7ca-121">Requirements</span></span>  

 <span data-ttu-id="ec7ca-122">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec7ca-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec7ca-123">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ec7ca-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec7ca-124">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ec7ca-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec7ca-125">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec7ca-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec7ca-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ec7ca-126">See also</span></span>

- [<span data-ttu-id="ec7ca-127">Statyczne funkcje globalne metadanych</span><span class="sxs-lookup"><span data-stu-id="ec7ca-127">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
