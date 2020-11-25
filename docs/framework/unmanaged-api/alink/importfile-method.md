---
title: ImportFile — Metoda
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
ms.openlocfilehash: f30307884a268008fd4d1a8de31ec5a49b6ab92d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705244"
---
# <a name="importfile-method"></a><span data-ttu-id="38728-102">ImportFile — Metoda</span><span class="sxs-lookup"><span data-stu-id="38728-102">ImportFile Method</span></span>

<span data-ttu-id="38728-103">Importuje zestawy i niepowiązane moduły.</span><span class="sxs-lookup"><span data-stu-id="38728-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38728-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="38728-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="38728-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="38728-105">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="38728-106">W pełni kwalifikowana nazwa pliku do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="38728-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="38728-107">Opcjonalna nazwa pliku wyjściowego, która może zostać użyta do zmiany nazwy pliku, ponieważ jest on połączony z zestawem.</span><span class="sxs-lookup"><span data-stu-id="38728-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="38728-108">Jeśli wartość jest równa TRUE, używane są wartości, w przeciwnym razie importowanie należy wykonać ręcznie.</span><span class="sxs-lookup"><span data-stu-id="38728-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="38728-109">Wskaźnik do tokenu, w którym będzie przechowywany unikatowy identyfikator pliku.</span><span class="sxs-lookup"><span data-stu-id="38728-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="38728-110">Plik może być zestawem lub plikiem.</span><span class="sxs-lookup"><span data-stu-id="38728-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="38728-111">Odbiera wskaźnik do [interfejsu IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md).</span><span class="sxs-lookup"><span data-stu-id="38728-111">Receives pointer to [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="38728-112">Może mieć wartość NULL, jeśli plik nie jest zestawem.</span><span class="sxs-lookup"><span data-stu-id="38728-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="38728-113">Wskaźnik do liczby zaimportowanych plików i/lub zakresów.</span><span class="sxs-lookup"><span data-stu-id="38728-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38728-114">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="38728-114">Return Value</span></span>  

 <span data-ttu-id="38728-115">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="38728-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38728-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="38728-116">Requirements</span></span>  

 <span data-ttu-id="38728-117">Wymaga Alink. h</span><span class="sxs-lookup"><span data-stu-id="38728-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38728-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="38728-118">See also</span></span>

- [<span data-ttu-id="38728-119">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="38728-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="38728-120">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="38728-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="38728-121">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="38728-121">ALink API</span></span>](index.md)
