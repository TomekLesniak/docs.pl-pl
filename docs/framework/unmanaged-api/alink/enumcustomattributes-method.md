---
title: EnumCustomAttributes — Metoda
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
ms.openlocfilehash: 445c833d10631341ef7ad579eaff8ddd96be3428
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684853"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="3558a-102">EnumCustomAttributes — Metoda</span><span class="sxs-lookup"><span data-stu-id="3558a-102">EnumCustomAttributes Method</span></span>

<span data-ttu-id="3558a-103">Pobiera niestandardowe atrybuty na poziomie zestawu.</span><span class="sxs-lookup"><span data-stu-id="3558a-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3558a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3558a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3558a-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="3558a-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="3558a-106">Uchwyt modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="3558a-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="3558a-107">Typ atrybutów do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="3558a-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="3558a-108">Używać `mdTokenNill` dla wszystkich atrybutów.</span><span class="sxs-lookup"><span data-stu-id="3558a-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="3558a-109">Odbiera tokeny atrybutów niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="3558a-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3558a-110">Określa rozmiar `rCustomValues` tablicy.</span><span class="sxs-lookup"><span data-stu-id="3558a-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="3558a-111">Opcjonalnie otrzymuje liczbę wartości tokenu.</span><span class="sxs-lookup"><span data-stu-id="3558a-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3558a-112">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="3558a-112">Return Value</span></span>  

 <span data-ttu-id="3558a-113">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="3558a-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3558a-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3558a-114">Requirements</span></span>  

 <span data-ttu-id="3558a-115">Wymaga Alink. h</span><span class="sxs-lookup"><span data-stu-id="3558a-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3558a-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3558a-116">See also</span></span>

- [<span data-ttu-id="3558a-117">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3558a-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3558a-118">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3558a-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3558a-119">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="3558a-119">ALink API</span></span>](index.md)
