---
title: IMetaDataDispenser::OpenScopeOnMemory — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
ms.openlocfilehash: 26293e38a275ca691c7d48dceb12c1e7dd316536
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713421"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="41128-102">IMetaDataDispenser::OpenScopeOnMemory — Metoda</span><span class="sxs-lookup"><span data-stu-id="41128-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>

<span data-ttu-id="41128-103">Otwiera obszar pamięci, który zawiera istniejące metadane.</span><span class="sxs-lookup"><span data-stu-id="41128-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="41128-104">Oznacza to, że ta metoda otwiera określony obszar pamięci, w której istniejące dane są traktowane jako metadane.</span><span class="sxs-lookup"><span data-stu-id="41128-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41128-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="41128-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41128-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="41128-106">Parameters</span></span>  

 `pData`  
 <span data-ttu-id="41128-107">podczas Wskaźnik określający adres początkowy obszaru pamięci.</span><span class="sxs-lookup"><span data-stu-id="41128-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="41128-108">podczas Rozmiar obszaru pamięci (w bajtach).</span><span class="sxs-lookup"><span data-stu-id="41128-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="41128-109">podczas Wartość wyliczenia [CorOpenFlags —](coropenflags-enumeration.md) w celu określenia trybu (odczyt, zapis itd.) do otwarcia.</span><span class="sxs-lookup"><span data-stu-id="41128-109">[in] A value of the [CorOpenFlags](coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="41128-110">podczas Identyfikator IID żądanego interfejsu metadanych do zwrócenia; Obiekt wywołujący będzie używać interfejsu do importowania metadanych (odczytu) lub emisji (zapisu).</span><span class="sxs-lookup"><span data-stu-id="41128-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="41128-111">Wartość `riid` musi określać jeden z interfejsów "Import" lub "Emituj".</span><span class="sxs-lookup"><span data-stu-id="41128-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="41128-112">Prawidłowe wartości to IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 lub IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="41128-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="41128-113">określoną Wskaźnik do zwracanego interfejsu.</span><span class="sxs-lookup"><span data-stu-id="41128-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41128-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="41128-114">Remarks</span></span>  

 <span data-ttu-id="41128-115">Kopię metadanych w pamięci można zbadać przy użyciu metod z jednego z interfejsów "Import" lub dodać do metod przy użyciu metody z jednego z interfejsów "Emituj".</span><span class="sxs-lookup"><span data-stu-id="41128-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="41128-116">`OpenScopeOnMemory`Metoda jest podobna do metody [IMetaDataDispenser:: OpenScope —](imetadatadispenser-openscope-method.md) , z tą różnicą, że metadane zainteresowania już istnieją w pamięci, a nie w pliku na dysku.</span><span class="sxs-lookup"><span data-stu-id="41128-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="41128-117">Jeśli obszar docelowy pamięci nie zawiera metadanych środowiska uruchomieniowego języka wspólnego (CLR), `OpenScopeOnMemory` Metoda zakończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="41128-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41128-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="41128-118">Requirements</span></span>  

 <span data-ttu-id="41128-119">**Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41128-119">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41128-120">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="41128-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41128-121">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="41128-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="41128-122">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41128-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41128-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="41128-123">See also</span></span>

- [<span data-ttu-id="41128-124">IMetaDataDispenser — Interfejs</span><span class="sxs-lookup"><span data-stu-id="41128-124">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="41128-125">IMetaDataDispenserEx — Interfejs</span><span class="sxs-lookup"><span data-stu-id="41128-125">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="41128-126">IMetaDataAssemblyEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="41128-126">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="41128-127">IMetaDataAssemblyImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="41128-127">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="41128-128">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="41128-128">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="41128-129">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="41128-129">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="41128-130">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="41128-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="41128-131">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="41128-131">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
