---
title: Init — Metoda
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
ms.openlocfilehash: 25a1c29ab94a785304b83d5b1bcb2d7176742a68
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726021"
---
# <a name="init-method"></a><span data-ttu-id="5764a-102">Init — Metoda</span><span class="sxs-lookup"><span data-stu-id="5764a-102">Init Method</span></span>

<span data-ttu-id="5764a-103">Przygotowuje obiekty implementujące [interfejs IALink —](ialink-interface.md) do użytku.</span><span class="sxs-lookup"><span data-stu-id="5764a-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5764a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5764a-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5764a-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="5764a-105">Parameters</span></span>  

 `pDispenser`  
 <span data-ttu-id="5764a-106">Wskaźnik [interfejsu IMetaDataDispenserEx](../metadata/imetadatadispenserex-interface.md) do rozdzielacza metadanych.</span><span class="sxs-lookup"><span data-stu-id="5764a-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="5764a-107">Wskaźnik [interfejsu IMetaDataError](../metadata/imetadataerror-interface.md) do opcjonalnego interfejsu obsługi błędów.</span><span class="sxs-lookup"><span data-stu-id="5764a-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5764a-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="5764a-108">Return Value</span></span>  

 <span data-ttu-id="5764a-109">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="5764a-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5764a-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5764a-110">Requirements</span></span>  

 <span data-ttu-id="5764a-111">Wymaga Alink. h</span><span class="sxs-lookup"><span data-stu-id="5764a-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5764a-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5764a-112">See also</span></span>

- [<span data-ttu-id="5764a-113">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5764a-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="5764a-114">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5764a-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="5764a-115">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="5764a-115">ALink API</span></span>](index.md)
