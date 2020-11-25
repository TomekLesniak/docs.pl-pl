---
title: IMetaDataAssemblyEmit::SetFileProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
ms.openlocfilehash: 9cf5f3d926c1e742dd9134e7bf292df53e1a4909
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720181"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="44f3e-102">IMetaDataAssemblyEmit::SetFileProps — Metoda</span><span class="sxs-lookup"><span data-stu-id="44f3e-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>

<span data-ttu-id="44f3e-103">Modyfikuje określoną `File` strukturę metadanych.</span><span class="sxs-lookup"><span data-stu-id="44f3e-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44f3e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="44f3e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44f3e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="44f3e-105">Parameters</span></span>  

 `file`  
 <span data-ttu-id="44f3e-106">podczas Token metadanych określający `File` strukturę metadanych, która ma zostać zmodyfikowana.</span><span class="sxs-lookup"><span data-stu-id="44f3e-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="44f3e-107">podczas Wskaźnik do danych skrótu skojarzonych z plikiem.</span><span class="sxs-lookup"><span data-stu-id="44f3e-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="44f3e-108">podczas Rozmiar w bajtach `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="44f3e-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="44f3e-109">podczas Bitowa kombinacja wartości [CorFileFlags —](corfileflags-enumeration.md) , które określają różne atrybuty pliku.</span><span class="sxs-lookup"><span data-stu-id="44f3e-109">[in] A bitwise combination of [CorFileFlags](corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44f3e-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="44f3e-110">Remarks</span></span>  

 <span data-ttu-id="44f3e-111">Aby utworzyć `File` strukturę metadanych, użyj metody [IMetaDataAssemblyEmit::D efinefile](imetadataassemblyemit-definefile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="44f3e-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44f3e-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="44f3e-112">Requirements</span></span>  

 <span data-ttu-id="44f3e-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44f3e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44f3e-114">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="44f3e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44f3e-115">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="44f3e-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="44f3e-116">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44f3e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44f3e-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="44f3e-117">See also</span></span>

- [<span data-ttu-id="44f3e-118">IMetaDataAssemblyEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="44f3e-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
