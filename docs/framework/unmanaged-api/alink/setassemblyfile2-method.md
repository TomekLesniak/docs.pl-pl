---
title: SetAssemblyFile2 — Metoda
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
ms.openlocfilehash: 131f5d951e524ef48f2cfe1e3e88ef80ac21c452
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703684"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="c874e-102">SetAssemblyFile2 — Metoda</span><span class="sxs-lookup"><span data-stu-id="c874e-102">SetAssemblyFile2 Method</span></span>

<span data-ttu-id="c874e-103">Ustawia nazwę i opcje dla nowego zestawu.</span><span class="sxs-lookup"><span data-stu-id="c874e-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="c874e-104">Nie wywołuj tej metody podczas tworzenia niezwiązanych modułów.</span><span class="sxs-lookup"><span data-stu-id="c874e-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c874e-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="c874e-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c874e-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="c874e-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="c874e-107">Nazwa pliku manifestu.</span><span class="sxs-lookup"><span data-stu-id="c874e-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="c874e-108">Interfejs [IMetaDataEmit2 interfejsu](../metadata/imetadataemit2-interface.md) dla tego pliku.</span><span class="sxs-lookup"><span data-stu-id="c874e-108">[IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="c874e-109">Opcje reprezentowane przez [Wyliczenie AssemblyFlags —](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="c874e-109">Options represented by [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="c874e-110">Odbiera unikatowy identyfikator konstruowanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="c874e-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c874e-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="c874e-111">Return Value</span></span>  

 <span data-ttu-id="c874e-112">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="c874e-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c874e-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c874e-113">Requirements</span></span>  

 <span data-ttu-id="c874e-114">Wymaga Alink. h.</span><span class="sxs-lookup"><span data-stu-id="c874e-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c874e-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c874e-115">See also</span></span>

- [<span data-ttu-id="c874e-116">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c874e-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c874e-117">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c874e-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c874e-118">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="c874e-118">ALink API</span></span>](index.md)
