---
title: CloseAssembly — Metoda
ms.date: 03/30/2017
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
ms.openlocfilehash: 4e8aeef3520c4d5c9735b2c8975ac1e39470ba93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717024"
---
# <a name="closeassembly-method"></a><span data-ttu-id="da9c7-102">CloseAssembly — Metoda</span><span class="sxs-lookup"><span data-stu-id="da9c7-102">CloseAssembly Method</span></span>

<span data-ttu-id="da9c7-103">Kończy operacje zestawu.</span><span class="sxs-lookup"><span data-stu-id="da9c7-103">Finalizes assembly operations.</span></span> <span data-ttu-id="da9c7-104">Wywołaj tę metodę przed rozpoczęciem nowego zestawu lub niepowiązanego modułu.</span><span class="sxs-lookup"><span data-stu-id="da9c7-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da9c7-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="da9c7-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="da9c7-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="da9c7-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="da9c7-107">Identyfikator zestawu.</span><span class="sxs-lookup"><span data-stu-id="da9c7-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da9c7-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="da9c7-108">Return Value</span></span>  

 <span data-ttu-id="da9c7-109">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="da9c7-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da9c7-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="da9c7-110">Requirements</span></span>  

 <span data-ttu-id="da9c7-111">Wymaga Alink. h.</span><span class="sxs-lookup"><span data-stu-id="da9c7-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da9c7-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="da9c7-112">See also</span></span>

- [<span data-ttu-id="da9c7-113">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="da9c7-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="da9c7-114">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="da9c7-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="da9c7-115">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="da9c7-115">ALink API</span></span>](index.md)
