---
title: EmbedResource — Metoda
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
ms.openlocfilehash: 34439b7c01dee7d7789d989b58e8944c6282b71b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676390"
---
# <a name="embedresource-method"></a><span data-ttu-id="88775-102">EmbedResource — Metoda</span><span class="sxs-lookup"><span data-stu-id="88775-102">EmbedResource Method</span></span>

<span data-ttu-id="88775-103">Deklaruje zasób osadzony.</span><span class="sxs-lookup"><span data-stu-id="88775-103">Declares an embedded resource.</span></span> <span data-ttu-id="88775-104">Ta metoda nie osadza zasobów w rzeczywistości.</span><span class="sxs-lookup"><span data-stu-id="88775-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88775-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="88775-105">Syntax</span></span>  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="88775-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="88775-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="88775-107">Identyfikator zestawu.</span><span class="sxs-lookup"><span data-stu-id="88775-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="88775-108">Token pliku lub identyfikator zestawu pliku zawierającego zasób.</span><span class="sxs-lookup"><span data-stu-id="88775-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="88775-109">Nazwa zasobu.</span><span class="sxs-lookup"><span data-stu-id="88775-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="88775-110">Przesunięcie zasobu z adresu RVA.</span><span class="sxs-lookup"><span data-stu-id="88775-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="88775-111">Flagi dostępności, takie jak `mrPublic` i `mrPrivate` .</span><span class="sxs-lookup"><span data-stu-id="88775-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="88775-112">Flagi te mogą być przesyłane do [metody DefineExportedType —](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="88775-112">These flags may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88775-113">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="88775-113">Return Value</span></span>  

 <span data-ttu-id="88775-114">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="88775-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88775-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="88775-115">Requirements</span></span>  

 <span data-ttu-id="88775-116">Wymaga Alink. h.</span><span class="sxs-lookup"><span data-stu-id="88775-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88775-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="88775-117">See also</span></span>

- [<span data-ttu-id="88775-118">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="88775-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="88775-119">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="88775-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="88775-120">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="88775-120">ALink API</span></span>](index.md)
