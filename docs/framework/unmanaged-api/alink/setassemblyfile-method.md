---
title: SetAssemblyFile — Metoda
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
ms.openlocfilehash: 45eed17b91f70d4188d1d89fc91a41455f3e845b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732648"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="0605c-102">SetAssemblyFile — Metoda</span><span class="sxs-lookup"><span data-stu-id="0605c-102">SetAssemblyFile Method</span></span>

<span data-ttu-id="0605c-103">Przypisuje nazwę zestawu, który ma zostać skompilowany.</span><span class="sxs-lookup"><span data-stu-id="0605c-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="0605c-104">Nie do użycia podczas tworzenia niezwiązanych modułów.</span><span class="sxs-lookup"><span data-stu-id="0605c-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0605c-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="0605c-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0605c-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="0605c-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="0605c-107">W pełni kwalifikowana nazwa pliku manifestu.</span><span class="sxs-lookup"><span data-stu-id="0605c-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="0605c-108">Wskaźnik do interfejsu [interfejsu IMetaDataEmit](../metadata/imetadataemit-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0605c-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="0605c-109">Flagi zgodnie z definicją w [wyliczeniu AssemblyFlags —](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="0605c-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="0605c-110">Wskaźnik na identyfikator tworzonego zestawu.</span><span class="sxs-lookup"><span data-stu-id="0605c-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0605c-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="0605c-111">Return Value</span></span>  

 <span data-ttu-id="0605c-112">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="0605c-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0605c-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0605c-113">Requirements</span></span>  

 <span data-ttu-id="0605c-114">Wymaga Alink. h.</span><span class="sxs-lookup"><span data-stu-id="0605c-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0605c-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0605c-115">See also</span></span>

- [<span data-ttu-id="0605c-116">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0605c-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="0605c-117">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0605c-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="0605c-118">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="0605c-118">ALink API</span></span>](index.md)
