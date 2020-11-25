---
title: IMetaDataImport2 — Interfejs
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: a845ecfde6583d625d2a8f165443344ff9e40d05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702553"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="280a3-102">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="280a3-102">IMetaDataImport2 Interface</span></span>

<span data-ttu-id="280a3-103">Rozszerza interfejs [IMetaDataImport](imetadataimport-interface.md) w celu zapewnienia możliwości pracy z typami ogólnymi.</span><span class="sxs-lookup"><span data-stu-id="280a3-103">Extends the [IMetaDataImport](imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="280a3-104">Metody</span><span class="sxs-lookup"><span data-stu-id="280a3-104">Methods</span></span>  
  
|<span data-ttu-id="280a3-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="280a3-105">Method</span></span>|<span data-ttu-id="280a3-106">Opis</span><span class="sxs-lookup"><span data-stu-id="280a3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="280a3-107">EnumGenericParamConstraints, metoda</span><span class="sxs-lookup"><span data-stu-id="280a3-107">EnumGenericParamConstraints Method</span></span>](imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="280a3-108">Pobiera moduł wyliczający dla tablicy ograniczeń parametrów ogólnych skojarzonych z parametrem ogólnym reprezentowanym przez określony token.</span><span class="sxs-lookup"><span data-stu-id="280a3-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="280a3-109">EnumGenericParams, metoda</span><span class="sxs-lookup"><span data-stu-id="280a3-109">EnumGenericParams Method</span></span>](imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="280a3-110">Pobiera moduł wyliczający dla tablicy tokenów parametrów ogólnych skojarzonych z określonym tokenem TypeDef lub MethodDef.</span><span class="sxs-lookup"><span data-stu-id="280a3-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="280a3-111">EnumMethodSpecs, metoda</span><span class="sxs-lookup"><span data-stu-id="280a3-111">EnumMethodSpecs Method</span></span>](imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="280a3-112">Pobiera moduł wyliczający dla tablicy tokenów elementu MethodSpec skojarzonych z określonym tokenem MethodDef lub MemberRef.</span><span class="sxs-lookup"><span data-stu-id="280a3-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="280a3-113">GetGenericParamConstraintProps, metoda</span><span class="sxs-lookup"><span data-stu-id="280a3-113">GetGenericParamConstraintProps Method</span></span>](imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="280a3-114">Pobiera metadane skojarzone z ograniczeniem parametru generycznego reprezentowane przez określony token ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="280a3-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="280a3-115">GetGenericParamProps, metoda</span><span class="sxs-lookup"><span data-stu-id="280a3-115">GetGenericParamProps Method</span></span>](imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="280a3-116">Pobiera metadane skojarzone z parametrem ogólnym reprezentowanym przez określony token.</span><span class="sxs-lookup"><span data-stu-id="280a3-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="280a3-117">GetMethodSpecProps, metoda</span><span class="sxs-lookup"><span data-stu-id="280a3-117">GetMethodSpecProps Method</span></span>](imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="280a3-118">Pobiera sygnaturę metadanych metody przywoływanej przez określony token elementu MethodSpec.</span><span class="sxs-lookup"><span data-stu-id="280a3-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="280a3-119">GetPEKind, metoda</span><span class="sxs-lookup"><span data-stu-id="280a3-119">GetPEKind Method</span></span>](imetadataimport2-getpekind-method.md)|<span data-ttu-id="280a3-120">Pobiera wartość identyfikującą charakter kodu w przenośnym pliku wykonywalnym (PE), zazwyczaj plik DLL lub EXE, zdefiniowany w bieżącym zakresie metadanych</span><span class="sxs-lookup"><span data-stu-id="280a3-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="280a3-121">GetVersionString, metoda</span><span class="sxs-lookup"><span data-stu-id="280a3-121">GetVersionString Method</span></span>](imetadataimport2-getversionstring-method.md)|<span data-ttu-id="280a3-122">Pobiera numer wersji środowiska uruchomieniowego, który został użyty do skompilowania zestawu.</span><span class="sxs-lookup"><span data-stu-id="280a3-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="280a3-123">Wymagania</span><span class="sxs-lookup"><span data-stu-id="280a3-123">Requirements</span></span>  

 <span data-ttu-id="280a3-124">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="280a3-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="280a3-125">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="280a3-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="280a3-126">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="280a3-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="280a3-127">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="280a3-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="280a3-128">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="280a3-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="280a3-129">Interfejsy metadanych</span><span class="sxs-lookup"><span data-stu-id="280a3-129">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="280a3-130">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="280a3-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
