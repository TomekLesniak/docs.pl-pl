---
title: CreateAssemblyNameObject — Funkcja
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
ms.openlocfilehash: 995f1064c2f40005c4a19ef034d7edfd668b5d51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704165"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="cefd0-102">CreateAssemblyNameObject — Funkcja</span><span class="sxs-lookup"><span data-stu-id="cefd0-102">CreateAssemblyNameObject Function</span></span>

<span data-ttu-id="cefd0-103">Pobiera wskaźnik interfejsu do wystąpienia [IAssemblyName](iassemblyname-interface.md) , które reprezentuje unikatową tożsamość zestawu o określonej nazwie.</span><span class="sxs-lookup"><span data-stu-id="cefd0-103">Gets an interface pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cefd0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cefd0-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="cefd0-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="cefd0-105">Parameters</span></span>  

 `ppAssemblyNameObj`  
 <span data-ttu-id="cefd0-106">określoną Zwracana wartość `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="cefd0-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="cefd0-107">podczas Nazwa zestawu, dla którego ma zostać utworzone nowe `IAssemblyName` wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="cefd0-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="cefd0-108">podczas Flagi do przekazania do konstruktora obiektów.</span><span class="sxs-lookup"><span data-stu-id="cefd0-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="cefd0-109">podczas Zarezerwowane do użytku w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="cefd0-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="cefd0-110">`pvReserved` musi być odwołaniem o wartości null.</span><span class="sxs-lookup"><span data-stu-id="cefd0-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cefd0-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cefd0-111">Requirements</span></span>  

 <span data-ttu-id="cefd0-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cefd0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cefd0-113">**Nagłówek:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="cefd0-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cefd0-114">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cefd0-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cefd0-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cefd0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cefd0-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cefd0-116">See also</span></span>

- [<span data-ttu-id="cefd0-117">IAssemblyName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cefd0-117">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="cefd0-118">Łączenie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="cefd0-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
