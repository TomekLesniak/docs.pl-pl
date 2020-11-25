---
title: ICorDebugILFrame2::EnumerateTypeParameters — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
ms.openlocfilehash: 73c17864047270302dbc115667eec4bf5ea1569d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725050"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="b925d-102">ICorDebugILFrame2::EnumerateTypeParameters — Metoda</span><span class="sxs-lookup"><span data-stu-id="b925d-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>

<span data-ttu-id="b925d-103">Pobiera obiekt ICorDebugTypeEnum, który zawiera <xref:System.Type> Parametry w tej ramce.</span><span class="sxs-lookup"><span data-stu-id="b925d-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b925d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b925d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b925d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b925d-105">Parameters</span></span>  

 `ppTyParEnum`  
 <span data-ttu-id="b925d-106">Wskaźnik do adresu obiektu interfejsu ICorDebugTypeEnum, który umożliwia Wyliczenie parametrów typu.</span><span class="sxs-lookup"><span data-stu-id="b925d-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="b925d-107">Lista parametrów typu zawiera parametry typu klasy (jeśli istnieją), a następnie parametry typu metody (jeśli istnieją).</span><span class="sxs-lookup"><span data-stu-id="b925d-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b925d-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b925d-108">Remarks</span></span>  

 <span data-ttu-id="b925d-109">Użyj metody [IMetaDataImport2:: EnumGenericParams —](../metadata/imetadataimport2-enumgenericparams-method.md) , aby określić, ile parametrów typu klasy i parametrów typu metody ta lista zawiera.</span><span class="sxs-lookup"><span data-stu-id="b925d-109">Use the [IMetaDataImport2::EnumGenericParams](../metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="b925d-110">Parametry typu nie są zawsze dostępne.</span><span class="sxs-lookup"><span data-stu-id="b925d-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b925d-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b925d-111">Requirements</span></span>  

 <span data-ttu-id="b925d-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b925d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b925d-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="b925d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b925d-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b925d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b925d-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b925d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
