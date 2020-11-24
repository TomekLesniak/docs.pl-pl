---
title: GetResolutionScope — Metoda
ms.date: 03/30/2017
api_name:
- IALink.GetResolutionScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetResolutionScope
helpviewer_keywords:
- GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type:
- apiref
ms.openlocfilehash: 6318890dd6f0259d8d6a7675380684a129c14c8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684681"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="2236a-102">GetResolutionScope — Metoda</span><span class="sxs-lookup"><span data-stu-id="2236a-102">GetResolutionScope Method</span></span>

<span data-ttu-id="2236a-103">Pobiera zakres danego typu.</span><span class="sxs-lookup"><span data-stu-id="2236a-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2236a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2236a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2236a-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2236a-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="2236a-106">Identyfikator zestawu.</span><span class="sxs-lookup"><span data-stu-id="2236a-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2236a-107">Plik, który jest wymagany do odwołania.</span><span class="sxs-lookup"><span data-stu-id="2236a-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="2236a-108">Token pliku, który jest zdefiniowany w, zazwyczaj pobierany przy użyciu [metody ImportFile —](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="2236a-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="2236a-109">Odbiera odwołanie zestawu lub modułu.</span><span class="sxs-lookup"><span data-stu-id="2236a-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2236a-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="2236a-110">Return Value</span></span>  

 <span data-ttu-id="2236a-111">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="2236a-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2236a-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2236a-112">Requirements</span></span>  

 <span data-ttu-id="2236a-113">Wymaga Alink. h.</span><span class="sxs-lookup"><span data-stu-id="2236a-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2236a-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2236a-114">See also</span></span>

- [<span data-ttu-id="2236a-115">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2236a-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="2236a-116">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2236a-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="2236a-117">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="2236a-117">ALink API</span></span>](index.md)
