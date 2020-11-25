---
title: ImportFileEx — Metoda
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
ms.openlocfilehash: 9e373f133830a5bc1f3cf7bdc8034cb67725d797
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705205"
---
# <a name="importfileex-method"></a><span data-ttu-id="a1316-102">ImportFileEx — Metoda</span><span class="sxs-lookup"><span data-stu-id="a1316-102">ImportFileEx Method</span></span>

<span data-ttu-id="a1316-103">Importuje wskazany zestaw lub niezwiązany moduł.</span><span class="sxs-lookup"><span data-stu-id="a1316-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1316-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a1316-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1316-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a1316-105">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="a1316-106">W pełni kwalifikowana nazwa pliku, z którego ma zostać zaimportowana.</span><span class="sxs-lookup"><span data-stu-id="a1316-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="a1316-107">Opcjonalna nazwa pliku docelowego.</span><span class="sxs-lookup"><span data-stu-id="a1316-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="a1316-108">Jeśli wartość jest równa TRUE, używane są wartości, w przeciwnym razie importowanie należy wykonać ręcznie.</span><span class="sxs-lookup"><span data-stu-id="a1316-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="a1316-109">Flagi do przesłania do [metody OpenScope —](../metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="a1316-109">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="a1316-110">Odbiera identyfikator importowanego pliku.</span><span class="sxs-lookup"><span data-stu-id="a1316-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="a1316-111">Odbiera Interfejs [IMetaDataAssemblyImporty](../metadata/imetadataassemblyimport-interface.md) zakresu importu zestawu.</span><span class="sxs-lookup"><span data-stu-id="a1316-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="a1316-112">Jest ustawiona na wartość NULL, jeśli plik nie jest zestawem.</span><span class="sxs-lookup"><span data-stu-id="a1316-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="a1316-113">Odbiera liczbę zaimportowanych plików i/lub zakresów.</span><span class="sxs-lookup"><span data-stu-id="a1316-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1316-114">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="a1316-114">Return Value</span></span>  

 <span data-ttu-id="a1316-115">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="a1316-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1316-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a1316-116">Requirements</span></span>  

 <span data-ttu-id="a1316-117">Wymaga Alink. h.</span><span class="sxs-lookup"><span data-stu-id="a1316-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1316-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a1316-118">See also</span></span>

- [<span data-ttu-id="a1316-119">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a1316-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a1316-120">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a1316-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a1316-121">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="a1316-121">ALink API</span></span>](index.md)
