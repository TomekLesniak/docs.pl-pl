---
title: IMetaDataAssemblyImport::GetAssemblyRefProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
ms.openlocfilehash: 25aefff46f7557f89f27d1eccab58c9c70d2d13e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722118"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="70467-102">IMetaDataAssemblyImport::GetAssemblyRefProps — Metoda</span><span class="sxs-lookup"><span data-stu-id="70467-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>

<span data-ttu-id="70467-103">Pobiera zestaw właściwości dla odwołania do zestawu z określonym podpisem metadanych.</span><span class="sxs-lookup"><span data-stu-id="70467-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70467-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="70467-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,
    [out] const void          **ppbPublicKeyOrToken,
    [out] ULONG                *pcbPublicKeyOrToken,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] ASSEMBLYMETADATA     *pMetaData,
    [out] const void           **ppbHashValue,
    [out] ULONG                *pcbHashValue,
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70467-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="70467-105">Parameters</span></span>  

 `mdar`  
 <span data-ttu-id="70467-106">podczas `mdAssemblyRef` Token metadanych reprezentujący odwołanie do zestawu, dla którego mają zostać pobrane właściwości.</span><span class="sxs-lookup"><span data-stu-id="70467-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="70467-107">określoną Wskaźnik do klucza publicznego lub tokenu metadanych.</span><span class="sxs-lookup"><span data-stu-id="70467-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="70467-108">określoną Liczba bajtów w zwracanym kluczu publicznym lub tokenie.</span><span class="sxs-lookup"><span data-stu-id="70467-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="70467-109">określoną Prosta nazwa zestawu.</span><span class="sxs-lookup"><span data-stu-id="70467-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="70467-110">podczas Rozmiar, w postaci szerokich znaków, z `szName` .</span><span class="sxs-lookup"><span data-stu-id="70467-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="70467-111">określoną Wskaźnik do liczby znaków dwubajtowych faktycznie zwróconych w `szName` .</span><span class="sxs-lookup"><span data-stu-id="70467-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="70467-112">określoną Wskaźnik do struktury ASSEMBLYMETADATA, która zawiera metadane zestawu.</span><span class="sxs-lookup"><span data-stu-id="70467-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="70467-113">określoną Wskaźnik do wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="70467-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="70467-114">Jest to skrót, przy użyciu algorytmu SHA-1 `PublicKey` Właściwości zestawu, którego dotyczy odwołanie, chyba że ustawiona jest flaga arfFullOriginator wyliczenia [AssemblyRefFlags —](assemblyrefflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="70467-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="70467-115">określoną Liczba znaków dwubajtowych w zwracanej wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="70467-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="70467-116">określoną Wskaźnik do flag, które opisują metadane zastosowane do zestawu.</span><span class="sxs-lookup"><span data-stu-id="70467-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="70467-117">Wartość flags jest kombinacją co najmniej jednej wartości [CorAssemblyFlags —](corassemblyflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="70467-117">The flags value is a combination of one or more [CorAssemblyFlags](corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70467-118">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="70467-118">Return Value</span></span>  

 <span data-ttu-id="70467-119">Ta metoda zwraca S_OK, jeśli zakończy się pomyślnie; w przeciwnym razie zwraca jeden z kodów błędów zdefiniowanych w pliku nagłówkowym Winerror. h.</span><span class="sxs-lookup"><span data-stu-id="70467-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70467-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="70467-120">Requirements</span></span>  

 <span data-ttu-id="70467-121">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70467-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70467-122">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="70467-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="70467-123">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="70467-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="70467-124">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70467-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70467-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="70467-125">See also</span></span>

- [<span data-ttu-id="70467-126">IMetaDataAssemblyImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="70467-126">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
