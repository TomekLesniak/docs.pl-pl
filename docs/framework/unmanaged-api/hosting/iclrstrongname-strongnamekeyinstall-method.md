---
title: ICLRStrongName::StrongNameKeyInstall — Metoda
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type:
- apiref
ms.openlocfilehash: 7e0c689dad0c288e3af3a3d64ee1bba1c44053c1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674531"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="3b926-102">ICLRStrongName::StrongNameKeyInstall — Metoda</span><span class="sxs-lookup"><span data-stu-id="3b926-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>

<span data-ttu-id="3b926-103">Importuje parę kluczy publiczny/prywatny do kontenera.</span><span class="sxs-lookup"><span data-stu-id="3b926-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b926-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3b926-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b926-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="3b926-105">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="3b926-106">podczas Nazwa kontenera kluczy.</span><span class="sxs-lookup"><span data-stu-id="3b926-106">[in] The name of the key container.</span></span> <span data-ttu-id="3b926-107">`wszKeyContainer` nie może być pustym ciągiem.</span><span class="sxs-lookup"><span data-stu-id="3b926-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="3b926-108">podczas Para kluczy binarnych.</span><span class="sxs-lookup"><span data-stu-id="3b926-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="3b926-109">podczas Rozmiar, w bajtach, z `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="3b926-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b926-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="3b926-110">Return Value</span></span>  

 <span data-ttu-id="3b926-111">`S_OK` Jeśli metoda została ukończona pomyślnie; w przeciwnym razie wartość HRESULT wskazująca niepowodzenie (zobacz [typowe wartości HRESULT](/windows/win32/seccrypto/common-hresult-values) dla listy).</span><span class="sxs-lookup"><span data-stu-id="3b926-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b926-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3b926-112">Remarks</span></span>  

 <span data-ttu-id="3b926-113">Aby usunąć kontener kluczy, użyj metody [ICLRStrongName:: StrongNameKeyDelete —](iclrstrongname-strongnamekeydelete-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3b926-113">Use the [ICLRStrongName::StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b926-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3b926-114">Requirements</span></span>  

 <span data-ttu-id="3b926-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b926-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b926-116">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="3b926-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3b926-117">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3b926-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b926-118">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b926-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b926-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3b926-119">See also</span></span>

- [<span data-ttu-id="3b926-120">StrongNameKeyDelete, metoda</span><span class="sxs-lookup"><span data-stu-id="3b926-120">StrongNameKeyDelete Method</span></span>](iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="3b926-121">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3b926-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
