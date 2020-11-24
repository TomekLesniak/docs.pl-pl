---
title: DestroyICeeFileGen — Funkcja
ms.date: 03/30/2017
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
ms.openlocfilehash: 495d84470c559df13ea64b63dd00582f4335d4e3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673197"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="2fa8b-102">DestroyICeeFileGen — Funkcja</span><span class="sxs-lookup"><span data-stu-id="2fa8b-102">DestroyICeeFileGen Function</span></span>

<span data-ttu-id="2fa8b-103">Niszczy obiekt [ICeeFileGen](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="2fa8b-103">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="2fa8b-104">Ta funkcja jest przestarzała w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="2fa8b-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fa8b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="2fa8b-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fa8b-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="2fa8b-106">Parameters</span></span>  

 `ceeFileGen`  
 <span data-ttu-id="2fa8b-107">podczas `ICeeFileGen` Obiekt do zniszczenia.</span><span class="sxs-lookup"><span data-stu-id="2fa8b-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fa8b-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="2fa8b-108">Return Value</span></span>  

 <span data-ttu-id="2fa8b-109">Ta metoda zwraca standardowe kody błędów COM.</span><span class="sxs-lookup"><span data-stu-id="2fa8b-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fa8b-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2fa8b-110">Remarks</span></span>  

 <span data-ttu-id="2fa8b-111">`DestroyICeeFileGen` niszczy `ICeeFileGen` obiekt utworzony przez funkcję [CreateICeeFileGen —](createiceefilegen-function.md) .</span><span class="sxs-lookup"><span data-stu-id="2fa8b-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fa8b-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2fa8b-112">Requirements</span></span>  

 <span data-ttu-id="2fa8b-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fa8b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fa8b-114">**Nagłówek:** ICeeFileGen. h</span><span class="sxs-lookup"><span data-stu-id="2fa8b-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="2fa8b-115">**Biblioteka:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="2fa8b-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="2fa8b-116">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fa8b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fa8b-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2fa8b-117">See also</span></span>

- [<span data-ttu-id="2fa8b-118">Przestarzałe funkcje hostingu środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="2fa8b-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
