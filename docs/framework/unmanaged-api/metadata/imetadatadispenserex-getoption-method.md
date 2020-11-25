---
title: IMetaDataDispenserEx::GetOption — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
ms.openlocfilehash: 0ceadf42ac49fd3fc89c78a6a26b2f529afeeaf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700565"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="01877-102">IMetaDataDispenserEx::GetOption — Metoda</span><span class="sxs-lookup"><span data-stu-id="01877-102">IMetaDataDispenserEx::GetOption Method</span></span>

<span data-ttu-id="01877-103">Pobiera wartość określonej opcji dla bieżącego zakresu metadanych.</span><span class="sxs-lookup"><span data-stu-id="01877-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="01877-104">Opcja określa, jak są obsługiwane wywołania bieżącego zakresu metadanych.</span><span class="sxs-lookup"><span data-stu-id="01877-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01877-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="01877-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01877-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="01877-106">Parameters</span></span>  

 `optionId`  
 <span data-ttu-id="01877-107">podczas Wskaźnik do identyfikatora GUID, który określa opcję do pobrania.</span><span class="sxs-lookup"><span data-stu-id="01877-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="01877-108">Zobacz sekcję Uwagi, aby zapoznać się z listą obsługiwanych identyfikatorów GUID.</span><span class="sxs-lookup"><span data-stu-id="01877-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="01877-109">określoną Wartość zwracanej opcji.</span><span class="sxs-lookup"><span data-stu-id="01877-109">[out] The value of the returned option.</span></span> <span data-ttu-id="01877-110">Typ tej wartości będzie wariantem typu określonej opcji.</span><span class="sxs-lookup"><span data-stu-id="01877-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01877-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="01877-111">Remarks</span></span>  

 <span data-ttu-id="01877-112">Poniższa lista zawiera identyfikatory GUID, które są obsługiwane dla tej metody.</span><span class="sxs-lookup"><span data-stu-id="01877-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="01877-113">Aby uzyskać opis, zobacz metodę [IMetaDataDispenserEx:: SetOption](imetadatadispenserex-setoption-method.md) .</span><span class="sxs-lookup"><span data-stu-id="01877-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="01877-114">Jeśli `optionId` nie znajduje się na tej liście, ta metoda zwraca wartość HRESULT `E_INVALIDARG` , wskazującą nieprawidłowy parametr.</span><span class="sxs-lookup"><span data-stu-id="01877-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="01877-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="01877-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="01877-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="01877-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="01877-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="01877-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="01877-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="01877-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="01877-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="01877-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="01877-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="01877-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="01877-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="01877-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01877-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="01877-122">Requirements</span></span>  

 <span data-ttu-id="01877-123">**Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01877-123">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01877-124">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="01877-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="01877-125">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="01877-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="01877-126">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01877-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01877-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="01877-127">See also</span></span>

- [<span data-ttu-id="01877-128">IMetaDataDispenserEx — Interfejs</span><span class="sxs-lookup"><span data-stu-id="01877-128">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="01877-129">IMetaDataDispenser — Interfejs</span><span class="sxs-lookup"><span data-stu-id="01877-129">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
