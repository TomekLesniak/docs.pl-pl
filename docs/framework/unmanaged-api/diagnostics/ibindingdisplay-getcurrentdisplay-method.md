---
title: IBindingDisplay::GetCurrentDisplay — Metoda
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
ms.openlocfilehash: db2474741012c4fd1734adafed112821c42c099c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541711"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="007e9-102">IBindingDisplay::GetCurrentDisplay — Metoda</span><span class="sxs-lookup"><span data-stu-id="007e9-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="007e9-103">Zwraca bieżące informacje o wyświetlaniu powiązania.</span><span class="sxs-lookup"><span data-stu-id="007e9-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="007e9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="007e9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="007e9-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="007e9-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="007e9-106">[out, retval] Wskaźnik do elementu SAFEARRAY zawierającego informacje o wyświetlaniu powiązania.</span><span class="sxs-lookup"><span data-stu-id="007e9-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="007e9-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="007e9-107">Remarks</span></span>  
 <span data-ttu-id="007e9-108">Metoda [IBindingDisplay:: InitializeForProcess —](ibindingdisplay-initializeforprocess-method.md) musi być wcześniej zakończona pomyślnie, a program musi być zatrzymany przez debuger.</span><span class="sxs-lookup"><span data-stu-id="007e9-108">The [IBindingDisplay::InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="007e9-109">Obiekt wywołujący musi cofnąć alokację zwróconej `SAFEARRAY` pamięci za pomocą [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span><span class="sxs-lookup"><span data-stu-id="007e9-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="007e9-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="007e9-110">Requirements</span></span>  
 <span data-ttu-id="007e9-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="007e9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="007e9-112">**Nagłówek:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="007e9-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="007e9-113">**Biblioteka:** BindingDisplay. idl</span><span class="sxs-lookup"><span data-stu-id="007e9-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="007e9-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="007e9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="007e9-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="007e9-115">See also</span></span>

- [<span data-ttu-id="007e9-116">IBindingDisplay — Interfejs</span><span class="sxs-lookup"><span data-stu-id="007e9-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
- [<span data-ttu-id="007e9-117">InitializeForProcess, metoda</span><span class="sxs-lookup"><span data-stu-id="007e9-117">InitializeForProcess Method</span></span>](ibindingdisplay-initializeforprocess-method.md)
