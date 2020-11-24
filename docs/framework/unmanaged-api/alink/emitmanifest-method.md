---
title: EmitManifest — Metoda
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
ms.openlocfilehash: b1c005e58f18b03a7da5f3836f719b95c41bca95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684944"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="a20e5-102">EmitManifest — Metoda</span><span class="sxs-lookup"><span data-stu-id="a20e5-102">EmitManifest Method</span></span>

<span data-ttu-id="a20e5-103">Emituje końcowy manifest.</span><span class="sxs-lookup"><span data-stu-id="a20e5-103">Emits the final manifest.</span></span> <span data-ttu-id="a20e5-104">Wywołaj tę metodę po zaimportowaniu wszystkich pozostałych plików i ustawieniu wszystkich opcji.</span><span class="sxs-lookup"><span data-stu-id="a20e5-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="a20e5-105">Nie wywołuj tej metody dla modułów niepowiązanych.</span><span class="sxs-lookup"><span data-stu-id="a20e5-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a20e5-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="a20e5-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a20e5-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="a20e5-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="a20e5-108">Identyfikator zestawu.</span><span class="sxs-lookup"><span data-stu-id="a20e5-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="a20e5-109">Odbiera rozmiar do zarezerwowania w pliku zestawu pobranym z [funkcji StrongNameSignatureSize —](../strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="a20e5-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="a20e5-110">Opcjonalnie odbiera token manifestu zestawu.</span><span class="sxs-lookup"><span data-stu-id="a20e5-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a20e5-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="a20e5-111">Return Value</span></span>  

 <span data-ttu-id="a20e5-112">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="a20e5-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a20e5-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a20e5-113">Requirements</span></span>  

 <span data-ttu-id="a20e5-114">Wymaga Alink. h.</span><span class="sxs-lookup"><span data-stu-id="a20e5-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a20e5-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a20e5-115">See also</span></span>

- [<span data-ttu-id="a20e5-116">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a20e5-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a20e5-117">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a20e5-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a20e5-118">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="a20e5-118">ALink API</span></span>](index.md)
