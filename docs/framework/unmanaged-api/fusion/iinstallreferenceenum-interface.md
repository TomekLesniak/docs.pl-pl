---
title: IInstallReferenceEnum — Interfejs
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum
helpviewer_keywords:
- IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type:
- apiref
ms.openlocfilehash: f56a9049cd4b503124abe9dd4866dc91779e268e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721066"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="3027d-102">IInstallReferenceEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3027d-102">IInstallReferenceEnum Interface</span></span>

<span data-ttu-id="3027d-103">Reprezentuje moduł wyliczający dla zestawów, do których istnieją odwołania zainstalowane w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="3027d-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3027d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3027d-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3027d-105">Metody</span><span class="sxs-lookup"><span data-stu-id="3027d-105">Methods</span></span>  
  
|<span data-ttu-id="3027d-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="3027d-106">Method</span></span>|<span data-ttu-id="3027d-107">Opis</span><span class="sxs-lookup"><span data-stu-id="3027d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3027d-108">GetNextInstallReferenceItem, metoda</span><span class="sxs-lookup"><span data-stu-id="3027d-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="3027d-109">Pobiera wskaźnik do następnego elementu `IInstallReferenceItem` zawartego w tym elemencie `IInstallReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="3027d-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3027d-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3027d-110">Requirements</span></span>  

 <span data-ttu-id="3027d-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3027d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3027d-112">**Nagłówek:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3027d-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3027d-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3027d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3027d-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3027d-114">See also</span></span>

- [<span data-ttu-id="3027d-115">Interfejsy łączenia</span><span class="sxs-lookup"><span data-stu-id="3027d-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="3027d-116">IInstallReferenceItem — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3027d-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
