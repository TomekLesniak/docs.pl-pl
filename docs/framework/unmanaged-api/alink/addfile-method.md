---
title: AddFile — Metoda
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
ms.openlocfilehash: 53ca4005f5681cfc5d550301d8aad1406aceb3a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717204"
---
# <a name="addfile-method"></a><span data-ttu-id="dfdba-102">AddFile — Metoda</span><span class="sxs-lookup"><span data-stu-id="dfdba-102">AddFile Method</span></span>

<span data-ttu-id="dfdba-103">Dodaje pliki do zestawu.</span><span class="sxs-lookup"><span data-stu-id="dfdba-103">Adds files to the assembly.</span></span> <span data-ttu-id="dfdba-104">Może również służyć do tworzenia niezwiązanych modułów.</span><span class="sxs-lookup"><span data-stu-id="dfdba-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfdba-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="dfdba-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfdba-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="dfdba-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="dfdba-107">Unikatowy identyfikator zestawu, który ma zostać rozszerzony.</span><span class="sxs-lookup"><span data-stu-id="dfdba-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="dfdba-108">W pełni kwalifikowana nazwa pliku, który ma zostać dodany.</span><span class="sxs-lookup"><span data-stu-id="dfdba-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="dfdba-109">Flagi FileDef modelu COM+, takie jak `ffContainsNoMetaData` i `ffWriteable` .</span><span class="sxs-lookup"><span data-stu-id="dfdba-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="dfdba-110">`dwFlags` jest przenoszona do [metody DefineFile —](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="dfdba-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="dfdba-111">Interfejs [interfejsu IMetaDataEmit](../metadata/imetadataemit-interface.md) , który ma być używany do emitowania metadanych, w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="dfdba-111">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="dfdba-112">Wskaźnik do lokalizacji, w której będzie przechowywany unikatowy identyfikator dodanego pliku.</span><span class="sxs-lookup"><span data-stu-id="dfdba-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dfdba-113">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="dfdba-113">Return Value</span></span>  

 <span data-ttu-id="dfdba-114">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="dfdba-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfdba-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="dfdba-115">Requirements</span></span>  

 <span data-ttu-id="dfdba-116">Wymaga Alink. h.</span><span class="sxs-lookup"><span data-stu-id="dfdba-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfdba-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="dfdba-117">See also</span></span>

- [<span data-ttu-id="dfdba-118">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="dfdba-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="dfdba-119">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="dfdba-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="dfdba-120">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="dfdba-120">ALink API</span></span>](index.md)
