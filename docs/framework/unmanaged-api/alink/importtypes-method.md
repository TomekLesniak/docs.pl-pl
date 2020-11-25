---
title: ImportTypes — Metoda
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
ms.openlocfilehash: 762f78900add70238971978ceecda089d0c725ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705114"
---
# <a name="importtypes-method"></a><span data-ttu-id="d578b-102">ImportTypes — Metoda</span><span class="sxs-lookup"><span data-stu-id="d578b-102">ImportTypes Method</span></span>

<span data-ttu-id="d578b-103">Inicjuje importowanie typów z każdego zakresu zaimportowanego za pomocą [metody ImportFile —](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="d578b-103">Initiates the importing of types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d578b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d578b-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d578b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d578b-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="d578b-106">Identyfikator zestawu do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="d578b-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d578b-107">Identyfikator pliku do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="d578b-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="d578b-108">Zakres od zera do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="d578b-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="d578b-109">Odbiera dojście modułu wyliczającego dla typów w tym zakresie.</span><span class="sxs-lookup"><span data-stu-id="d578b-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="d578b-110">Opcjonalnie odbiera Interfejs [interfejsu IMetaDataImport](../metadata/imetadataimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d578b-110">Optionally receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="d578b-111">Opcjonalnie otrzymuje liczbę typów we wskazanym zakresie.</span><span class="sxs-lookup"><span data-stu-id="d578b-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d578b-112">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="d578b-112">Return Value</span></span>  

 <span data-ttu-id="d578b-113">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="d578b-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d578b-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d578b-114">Requirements</span></span>  

 <span data-ttu-id="d578b-115">Wymaga Alink. h</span><span class="sxs-lookup"><span data-stu-id="d578b-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d578b-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d578b-116">See also</span></span>

- [<span data-ttu-id="d578b-117">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d578b-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d578b-118">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d578b-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="d578b-119">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="d578b-119">ALink API</span></span>](index.md)
