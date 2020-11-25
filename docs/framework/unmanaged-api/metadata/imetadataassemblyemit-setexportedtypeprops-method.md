---
title: IMetaDataAssemblyEmit::SetExportedTypeProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
ms.openlocfilehash: 076d027945dc27942e4b0989e14e86d829f76679
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713492"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="d6733-102">IMetaDataAssemblyEmit::SetExportedTypeProps — Metoda</span><span class="sxs-lookup"><span data-stu-id="d6733-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>

<span data-ttu-id="d6733-103">Modyfikuje określoną `ExportedType` strukturę metadanych.</span><span class="sxs-lookup"><span data-stu-id="d6733-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6733-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d6733-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6733-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d6733-105">Parameters</span></span>  

 `ct`  
 <span data-ttu-id="d6733-106">podczas Token metadanych określający `ExportedType` strukturę metadanych, która ma zostać zmodyfikowana.</span><span class="sxs-lookup"><span data-stu-id="d6733-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="d6733-107">podczas Token, typu `File` , `AssemblyRef` lub `ExportedType` , który określa sposób implementacji tego typu.</span><span class="sxs-lookup"><span data-stu-id="d6733-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="d6733-108">podczas `TypeDef` Token, do którego odwołuje się plik kodu.</span><span class="sxs-lookup"><span data-stu-id="d6733-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="d6733-109">podczas Bitowa kombinacja wartości, które określają atrybuty typu.</span><span class="sxs-lookup"><span data-stu-id="d6733-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6733-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d6733-110">Remarks</span></span>  

 <span data-ttu-id="d6733-111">Aby utworzyć `ExportedType` strukturę metadanych, użyj metody [IMetaDataAssemblyEmit::D efineexportedtype](imetadataassemblyemit-defineexportedtype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d6733-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6733-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d6733-112">Requirements</span></span>  

 <span data-ttu-id="d6733-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6733-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6733-114">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d6733-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d6733-115">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d6733-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d6733-116">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6733-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6733-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d6733-117">See also</span></span>

- [<span data-ttu-id="d6733-118">IMetaDataAssemblyEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d6733-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
