---
title: ExportType — Metoda
ms.date: 03/30/2017
api_name:
- IALink.ExportType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportType
helpviewer_keywords:
- ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type:
- apiref
ms.openlocfilehash: b8db08b22765bac0ed2fe058db49d6882b8d22df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684801"
---
# <a name="exporttype-method"></a><span data-ttu-id="62a48-102">ExportType — Metoda</span><span class="sxs-lookup"><span data-stu-id="62a48-102">ExportType Method</span></span>

<span data-ttu-id="62a48-103">Określa, że typ jest eksportowalny.</span><span class="sxs-lookup"><span data-stu-id="62a48-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62a48-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="62a48-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="62a48-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="62a48-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="62a48-106">Identyfikator zestawu do wyeksportowania.</span><span class="sxs-lookup"><span data-stu-id="62a48-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="62a48-107">Token pliku lub identyfikator zestawu pliku, który definiuje typ możliwy do eksportu.</span><span class="sxs-lookup"><span data-stu-id="62a48-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="62a48-108">Token typu, który ma być możliwy do eksportu.</span><span class="sxs-lookup"><span data-stu-id="62a48-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="62a48-109">W pełni kwalifikowana nazwa typu, która ma zostać wyeksportowana.</span><span class="sxs-lookup"><span data-stu-id="62a48-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="62a48-110">`ComType` flagi takie jak `tdPublic` lub `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="62a48-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="62a48-111">Ten parametr może być przesłany do [metody DefineExportedType —](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="62a48-111">This parameter may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="62a48-112">Odbiera token dla wyeksportowanego typu.</span><span class="sxs-lookup"><span data-stu-id="62a48-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62a48-113">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="62a48-113">Return Value</span></span>  

 <span data-ttu-id="62a48-114">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="62a48-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62a48-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="62a48-115">Requirements</span></span>  

 <span data-ttu-id="62a48-116">Wymaga Alink. h</span><span class="sxs-lookup"><span data-stu-id="62a48-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62a48-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="62a48-117">See also</span></span>

- [<span data-ttu-id="62a48-118">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="62a48-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="62a48-119">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="62a48-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="62a48-120">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="62a48-120">ALink API</span></span>](index.md)
