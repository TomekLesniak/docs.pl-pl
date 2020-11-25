---
title: IMetaDataImport2::GetPEKind — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type:
- apiref
ms.openlocfilehash: d335beecc12e0c1c895e42888ad7172f78062ff7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702542"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="936b2-102">IMetaDataImport2::GetPEKind — Metoda</span><span class="sxs-lookup"><span data-stu-id="936b2-102">IMetaDataImport2::GetPEKind Method</span></span>

<span data-ttu-id="936b2-103">Pobiera wartość określającą charakter kodu w przenośnym pliku wykonywalnym (PE), zazwyczaj plik DLL lub EXE, który jest zdefiniowany w bieżącym zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="936b2-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="936b2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="936b2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="936b2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="936b2-105">Parameters</span></span>  

 `pdwPEKind`  
 <span data-ttu-id="936b2-106">określoną Wskaźnik do wartości wyliczenia [CorPEKind —](corpekind-enumeration.md) , który OPISUJE plik PE.</span><span class="sxs-lookup"><span data-stu-id="936b2-106">[out] A pointer to a value of the [CorPEKind](corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="936b2-107">określoną Wskaźnik do wartości, która identyfikuje architekturę maszyny.</span><span class="sxs-lookup"><span data-stu-id="936b2-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="936b2-108">Więcej wartości można znaleźć w następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="936b2-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="936b2-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="936b2-109">Remarks</span></span>  

 <span data-ttu-id="936b2-110">Wartość, do której odwołuje się `pdwMachine` parametr może być jedną z następujących.</span><span class="sxs-lookup"><span data-stu-id="936b2-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="936b2-111">Wartość</span><span class="sxs-lookup"><span data-stu-id="936b2-111">Value</span></span>|<span data-ttu-id="936b2-112">Architektura komputera</span><span class="sxs-lookup"><span data-stu-id="936b2-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="936b2-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="936b2-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="936b2-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="936b2-114">0x014C</span></span>|<span data-ttu-id="936b2-115">x86</span><span class="sxs-lookup"><span data-stu-id="936b2-115">x86</span></span>|  
|<span data-ttu-id="936b2-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="936b2-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="936b2-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="936b2-117">0x0200</span></span>|<span data-ttu-id="936b2-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="936b2-118">Intel IPF</span></span>|  
|<span data-ttu-id="936b2-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="936b2-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="936b2-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="936b2-120">0x8664</span></span>|<span data-ttu-id="936b2-121">x64</span><span class="sxs-lookup"><span data-stu-id="936b2-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="936b2-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="936b2-122">Requirements</span></span>  

 <span data-ttu-id="936b2-123">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="936b2-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="936b2-124">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="936b2-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="936b2-125">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="936b2-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="936b2-126">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="936b2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="936b2-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="936b2-127">See also</span></span>

- [<span data-ttu-id="936b2-128">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="936b2-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="936b2-129">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="936b2-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="936b2-130">CorPEKind — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="936b2-130">CorPEKind Enumeration</span></span>](corpekind-enumeration.md)
