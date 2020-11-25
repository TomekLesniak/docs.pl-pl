---
title: ImportFileEx2 — Metoda
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
ms.openlocfilehash: 59149e79e926a0b9a3e549e013bf178e54ddf6fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705179"
---
# <a name="importfileex2-method"></a><span data-ttu-id="f4e8e-102">ImportFileEx2 — Metoda</span><span class="sxs-lookup"><span data-stu-id="f4e8e-102">ImportFileEx2 Method</span></span>

<span data-ttu-id="f4e8e-103">Importuje zestawy i niepowiązane moduły.</span><span class="sxs-lookup"><span data-stu-id="f4e8e-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="f4e8e-104">Ta metoda jest taka sama jak [Metoda ImportFile —](importfile-method.md), ale działa nawet wtedy, gdy importowany plik nie istnieje na dysku.</span><span class="sxs-lookup"><span data-stu-id="f4e8e-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4e8e-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="f4e8e-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4e8e-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="f4e8e-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="f4e8e-107">Nazwa pliku do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="f4e8e-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="f4e8e-108">Opcjonalna nazwa pliku docelowego.</span><span class="sxs-lookup"><span data-stu-id="f4e8e-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="f4e8e-109">Opcjonalny interfejs [interfejsu IMetaDataAssemblyImportgo](../metadata/imetadataassemblyimport-interface.md) zakresu importu.</span><span class="sxs-lookup"><span data-stu-id="f4e8e-109">Optional import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="f4e8e-110">Jeśli wartość jest równa TRUE, używane są wartości, w przeciwnym razie importowanie należy wykonać ręcznie.</span><span class="sxs-lookup"><span data-stu-id="f4e8e-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="f4e8e-111">Flagi do przesłania do [metody OpenScope —](../metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="f4e8e-111">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="f4e8e-112">Odbiera unikatowy identyfikator zestawu lub pliku.</span><span class="sxs-lookup"><span data-stu-id="f4e8e-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="f4e8e-113">Odbiera Interfejs [IMetaDataAssemblyImporty](../metadata/imetadataassemblyimport-interface.md) zakresu importu zestawu.</span><span class="sxs-lookup"><span data-stu-id="f4e8e-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="f4e8e-114">Może mieć wartość NULL, jeśli plik nie jest zestawem.</span><span class="sxs-lookup"><span data-stu-id="f4e8e-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="f4e8e-115">Odbiera liczbę zaimportowanych plików i/lub zakresów.</span><span class="sxs-lookup"><span data-stu-id="f4e8e-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4e8e-116">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="f4e8e-116">Return Value</span></span>  

 <span data-ttu-id="f4e8e-117">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="f4e8e-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4e8e-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f4e8e-118">Requirements</span></span>  

 <span data-ttu-id="f4e8e-119">Wymaga Alink. h.</span><span class="sxs-lookup"><span data-stu-id="f4e8e-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4e8e-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f4e8e-120">See also</span></span>

- [<span data-ttu-id="f4e8e-121">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f4e8e-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f4e8e-122">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f4e8e-122">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f4e8e-123">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="f4e8e-123">ALink API</span></span>](index.md)
