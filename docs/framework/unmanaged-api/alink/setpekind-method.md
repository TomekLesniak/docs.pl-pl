---
title: SetPEKind — Metoda
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: be8a11cbf70e2c6f19ace67648b124515c1fb3c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680043"
---
# <a name="setpekind-method"></a><span data-ttu-id="3c464-102">SetPEKind — Metoda</span><span class="sxs-lookup"><span data-stu-id="3c464-102">SetPEKind Method</span></span>

<span data-ttu-id="3c464-103">Określa przenośny typ pliku wykonywalnego, dla maszyn lub maszyn-niezależny od.</span><span class="sxs-lookup"><span data-stu-id="3c464-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c464-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3c464-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="3c464-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="3c464-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="3c464-106">Identyfikator zestawu.</span><span class="sxs-lookup"><span data-stu-id="3c464-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3c464-107">Token pliku, dla którego ma zostać ustawiony typ PE.</span><span class="sxs-lookup"><span data-stu-id="3c464-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="3c464-108">Może mieć wartość NULL `AssemblyID` , jeśli nie wskazuje niepowiązanego modułu.</span><span class="sxs-lookup"><span data-stu-id="3c464-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="3c464-109">Typ środowiska PE określony przez [Wyliczenie CorPEKind —](../metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="3c464-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="3c464-110">Architektura komputera docelowego, jak wskazano w nagłówku NT.</span><span class="sxs-lookup"><span data-stu-id="3c464-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c464-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="3c464-111">Return Value</span></span>  

 <span data-ttu-id="3c464-112">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="3c464-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c464-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3c464-113">Requirements</span></span>  

 <span data-ttu-id="3c464-114">Wymaga Alink. h.</span><span class="sxs-lookup"><span data-stu-id="3c464-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c464-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3c464-115">See also</span></span>

- [<span data-ttu-id="3c464-116">GetPEKind, metoda</span><span class="sxs-lookup"><span data-stu-id="3c464-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="3c464-117">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3c464-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3c464-118">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3c464-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3c464-119">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="3c464-119">ALink API</span></span>](index.md)
