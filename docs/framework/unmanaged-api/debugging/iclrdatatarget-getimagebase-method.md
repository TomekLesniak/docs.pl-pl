---
title: ICLRDataTarget::GetImageBase — Metoda
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
ms.openlocfilehash: f1b9f55a383f1deb867c6b3e2fa385a82158d1e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703580"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="e64ba-102">ICLRDataTarget::GetImageBase — Metoda</span><span class="sxs-lookup"><span data-stu-id="e64ba-102">ICLRDataTarget::GetImageBase Method</span></span>

<span data-ttu-id="e64ba-103">Pobiera adres pamięci podstawowej określonego obrazu.</span><span class="sxs-lookup"><span data-stu-id="e64ba-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e64ba-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e64ba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e64ba-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e64ba-105">Parameters</span></span>  

 `imagePath`  
 <span data-ttu-id="e64ba-106">podczas Nazwa pliku obrazu, łącznie z jego ścieżką.</span><span class="sxs-lookup"><span data-stu-id="e64ba-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="e64ba-107">określoną Wskaźnik do CLRDATA_ADDRESS, w którym przechowywany jest podstawowy adres obrazu.</span><span class="sxs-lookup"><span data-stu-id="e64ba-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e64ba-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e64ba-108">Remarks</span></span>  

 <span data-ttu-id="e64ba-109">Nazwa pliku obrazu może być nieścieżką lub nie może mieć ścieżki.</span><span class="sxs-lookup"><span data-stu-id="e64ba-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="e64ba-110">Jeśli ścieżka jest określona, dopasowywanie jest wykonywane na całej ścieżce; w przeciwnym razie dopasowanie jest wykonywane tylko na nazwie pliku.</span><span class="sxs-lookup"><span data-stu-id="e64ba-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e64ba-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e64ba-111">Requirements</span></span>  

 <span data-ttu-id="e64ba-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e64ba-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e64ba-113">**Nagłówek:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="e64ba-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e64ba-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e64ba-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e64ba-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e64ba-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e64ba-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e64ba-116">See also</span></span>

- [<span data-ttu-id="e64ba-117">ICLRDataTarget — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e64ba-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
