---
title: ICLRStrongName::StrongNameKeyDelete — Metoda
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type:
- apiref
ms.openlocfilehash: 46345ae570673c9c9c0c58fb6edea1464ba8dd91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671697"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="a031a-102">ICLRStrongName::StrongNameKeyDelete — Metoda</span><span class="sxs-lookup"><span data-stu-id="a031a-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>

<span data-ttu-id="a031a-103">Usuwa określony kontener kluczy.</span><span class="sxs-lookup"><span data-stu-id="a031a-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a031a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a031a-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a031a-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a031a-105">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="a031a-106">podczas Nazwa kontenera kluczy do usunięcia.</span><span class="sxs-lookup"><span data-stu-id="a031a-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a031a-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="a031a-107">Return Value</span></span>  

 <span data-ttu-id="a031a-108">`S_OK` Jeśli metoda została ukończona pomyślnie; w przeciwnym razie wartość HRESULT wskazująca niepowodzenie (zobacz [typowe wartości HRESULT](/windows/win32/seccrypto/common-hresult-values) dla listy).</span><span class="sxs-lookup"><span data-stu-id="a031a-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a031a-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a031a-109">Remarks</span></span>  

 <span data-ttu-id="a031a-110">Użyj metody [ICLRStrongName:: StrongNameKeyInstall —](iclrstrongname-strongnamekeyinstall-method.md) w celu zaimportowania pary kluczy publicznych/prywatnych do kontenera.</span><span class="sxs-lookup"><span data-stu-id="a031a-110">Use the [ICLRStrongName::StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a031a-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a031a-111">Requirements</span></span>  

 <span data-ttu-id="a031a-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a031a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a031a-113">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="a031a-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a031a-114">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a031a-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a031a-115">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a031a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a031a-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a031a-116">See also</span></span>

- [<span data-ttu-id="a031a-117">StrongNameKeyInstall, metoda</span><span class="sxs-lookup"><span data-stu-id="a031a-117">StrongNameKeyInstall Method</span></span>](iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="a031a-118">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a031a-118">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
