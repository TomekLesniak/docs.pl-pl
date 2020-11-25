---
title: ICorDebugModule::GetToken — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
ms.openlocfilehash: 6ffc74247a4ecafcc3744923c0def99220b5ca6f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709885"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="195a2-102">ICorDebugModule::GetToken — Metoda</span><span class="sxs-lookup"><span data-stu-id="195a2-102">ICorDebugModule::GetToken Method</span></span>

<span data-ttu-id="195a2-103">Pobiera token dla wpisu tabeli dla tego modułu.</span><span class="sxs-lookup"><span data-stu-id="195a2-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="195a2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="195a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="195a2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="195a2-105">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="195a2-106">określoną Wskaźnik do `mdModule` tokenu, który odwołuje się do metadanych modułu.</span><span class="sxs-lookup"><span data-stu-id="195a2-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="195a2-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="195a2-107">Remarks</span></span>  

 <span data-ttu-id="195a2-108">Token może być przesłany do interfejsów importu metadanych [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md)i [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="195a2-108">The token can be passed to the [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="195a2-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="195a2-109">Requirements</span></span>  

 <span data-ttu-id="195a2-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="195a2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="195a2-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="195a2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="195a2-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="195a2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="195a2-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="195a2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195a2-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="195a2-114">See also</span></span>

- [<span data-ttu-id="195a2-115">Metadane</span><span class="sxs-lookup"><span data-stu-id="195a2-115">Metadata</span></span>](../metadata/index.md)
