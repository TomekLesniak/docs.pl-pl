---
title: ITypeName::GetTypeArguments — Metoda
ms.date: 03/30/2017
api_name:
- ITypeName.GetTypeArguments
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArguments
helpviewer_keywords:
- ITypeName::GetTypeArguments method [.NET Framework hosting]
- GetTypeArguments method [.NET Framework hosting]
ms.assetid: 638d77df-ff9c-40d9-88ee-930f5f87ada1
topic_type:
- apiref
ms.openlocfilehash: bcc1cb2755c4c0a2beb0829ce58b921f073f63d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727786"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="35847-102">ITypeName::GetTypeArguments — Metoda</span><span class="sxs-lookup"><span data-stu-id="35847-102">ITypeName::GetTypeArguments Method</span></span>

<span data-ttu-id="35847-103">Ta metoda obsługuje infrastrukturę .NET Framework i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="35847-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35847-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="35847-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="35847-105">Wymagania</span><span class="sxs-lookup"><span data-stu-id="35847-105">Requirements</span></span>  

 <span data-ttu-id="35847-106">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35847-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35847-107">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="35847-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35847-108">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35847-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35847-109">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35847-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35847-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="35847-110">See also</span></span>

- [<span data-ttu-id="35847-111">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="35847-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
