---
title: ICeeGen::ComputePointer — Metoda
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
ms.openlocfilehash: 41a3b9c77fc766b2fa39b406dedbb3203cc97ad9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715475"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="9fd05-102">ICeeGen::ComputePointer — Metoda</span><span class="sxs-lookup"><span data-stu-id="9fd05-102">ICeeGen::ComputePointer Method</span></span>

<span data-ttu-id="9fd05-103">Określa bufor dla określonej sekcji kodu.</span><span class="sxs-lookup"><span data-stu-id="9fd05-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="9fd05-104">Ta metoda jest przestarzała i nie powinna być używana.</span><span class="sxs-lookup"><span data-stu-id="9fd05-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fd05-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="9fd05-105">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fd05-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="9fd05-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="9fd05-107">podczas Sekcja kodu, dla której ma zostać zwrócony bufor.</span><span class="sxs-lookup"><span data-stu-id="9fd05-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="9fd05-108">podczas Względny adres wirtualny metody, dla której ma zostać pobrany wskaźnik.</span><span class="sxs-lookup"><span data-stu-id="9fd05-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="9fd05-109">określoną Wskaźnik do zwróconego buforu.</span><span class="sxs-lookup"><span data-stu-id="9fd05-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fd05-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9fd05-110">Requirements</span></span>  

 <span data-ttu-id="9fd05-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fd05-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fd05-112">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9fd05-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9fd05-113">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9fd05-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9fd05-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fd05-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fd05-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9fd05-115">See also</span></span>

- [<span data-ttu-id="9fd05-116">ICeeGen — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9fd05-116">ICeeGen Interface</span></span>](iceegen-interface.md)
