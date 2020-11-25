---
title: IMetaDataDispenserEx — Interfejs
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx
helpviewer_keywords:
- IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type:
- apiref
ms.openlocfilehash: 60d321c1a87a5da433437c9d4587fa9f8947acf4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713382"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="83975-102">IMetaDataDispenserEx — Interfejs</span><span class="sxs-lookup"><span data-stu-id="83975-102">IMetaDataDispenserEx Interface</span></span>

<span data-ttu-id="83975-103">Rozszerza interfejs [interfejsu IMetaDataDispenser](imetadatadispenser-interface.md) , aby zapewnić możliwość sterowania sposobem działania interfejsów API metadanych w bieżącym zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="83975-103">Extends the [IMetaDataDispenser Interface](imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83975-104">Metody</span><span class="sxs-lookup"><span data-stu-id="83975-104">Methods</span></span>  
  
|<span data-ttu-id="83975-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="83975-105">Method</span></span>|<span data-ttu-id="83975-106">Opis</span><span class="sxs-lookup"><span data-stu-id="83975-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83975-107">FindAssembly, metoda</span><span class="sxs-lookup"><span data-stu-id="83975-107">FindAssembly Method</span></span>](imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="83975-108">Ta metoda nie jest zaimplementowana.</span><span class="sxs-lookup"><span data-stu-id="83975-108">This method is not implemented.</span></span> <span data-ttu-id="83975-109">Jeśli zostanie wywołana, zwraca E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="83975-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="83975-110">FindAssemblyModule, metoda</span><span class="sxs-lookup"><span data-stu-id="83975-110">FindAssemblyModule Method</span></span>](imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="83975-111">Ta metoda nie jest zaimplementowana.</span><span class="sxs-lookup"><span data-stu-id="83975-111">This method is not implemented.</span></span> <span data-ttu-id="83975-112">Jeśli zostanie wywołana, zwraca E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="83975-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="83975-113">GetCORSystemDirectory, metoda</span><span class="sxs-lookup"><span data-stu-id="83975-113">GetCORSystemDirectory Method</span></span>](imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="83975-114">Pobiera katalog, który przechowuje bieżące środowisko uruchomieniowe języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="83975-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="83975-115">Ta metoda jest obsługiwana tylko dla debugerów out-of-process.</span><span class="sxs-lookup"><span data-stu-id="83975-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="83975-116">Jeśli wywoływana z innego składnika, zwróci E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="83975-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="83975-117">GetOption, metoda</span><span class="sxs-lookup"><span data-stu-id="83975-117">GetOption Method</span></span>](imetadatadispenserex-getoption-method.md)|<span data-ttu-id="83975-118">Pobiera wartość określonej opcji dla bieżącego zakresu metadanych.</span><span class="sxs-lookup"><span data-stu-id="83975-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="83975-119">Opcja określa, jak są obsługiwane wywołania bieżącego zakresu metadanych.</span><span class="sxs-lookup"><span data-stu-id="83975-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="83975-120">OpenScopeOnITypeInfo, metoda</span><span class="sxs-lookup"><span data-stu-id="83975-120">OpenScopeOnITypeInfo Method</span></span>](imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="83975-121">Ta metoda nie jest zaimplementowana.</span><span class="sxs-lookup"><span data-stu-id="83975-121">This method is not implemented.</span></span> <span data-ttu-id="83975-122">Jeśli zostanie wywołana, zwraca E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="83975-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="83975-123">SetOption, metoda</span><span class="sxs-lookup"><span data-stu-id="83975-123">SetOption Method</span></span>](imetadatadispenserex-setoption-method.md)|<span data-ttu-id="83975-124">Ustawia określoną opcję na daną wartość dla bieżącego zakresu metadanych.</span><span class="sxs-lookup"><span data-stu-id="83975-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="83975-125">Opcja określa, jak są obsługiwane wywołania bieżącego zakresu metadanych.</span><span class="sxs-lookup"><span data-stu-id="83975-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="83975-126">Wymagania</span><span class="sxs-lookup"><span data-stu-id="83975-126">Requirements</span></span>  

 <span data-ttu-id="83975-127">**Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83975-127">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83975-128">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="83975-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83975-129">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="83975-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="83975-130">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83975-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83975-131">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="83975-131">See also</span></span>

- [<span data-ttu-id="83975-132">Interfejsy metadanych</span><span class="sxs-lookup"><span data-stu-id="83975-132">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="83975-133">IMetaDataDispenser — Interfejs</span><span class="sxs-lookup"><span data-stu-id="83975-133">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="83975-134">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="83975-134">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="83975-135">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="83975-135">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
