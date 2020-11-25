---
title: IMetaDataImport::FindMethod — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
ms.openlocfilehash: 111e42a6d8f413c616779bc44e0722ab38781588
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711341"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="21a1f-102">IMetaDataImport::FindMethod — Metoda</span><span class="sxs-lookup"><span data-stu-id="21a1f-102">IMetaDataImport::FindMethod Method</span></span>

<span data-ttu-id="21a1f-103">Pobiera wskaźnik do tokenu MethodDef dla metody, która jest ujęta w określonym <xref:System.Type> i która ma określoną nazwę i sygnaturę metadanych.</span><span class="sxs-lookup"><span data-stu-id="21a1f-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21a1f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="21a1f-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21a1f-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="21a1f-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="21a1f-106">podczas `mdTypeDef` Token dla typu (klasy lub interfejsu), który obejmuje element członkowski do wyszukania.</span><span class="sxs-lookup"><span data-stu-id="21a1f-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="21a1f-107">Jeśli ta wartość jest `mdTokenNil` , wyszukiwanie jest wykonywane dla funkcji globalnej.</span><span class="sxs-lookup"><span data-stu-id="21a1f-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="21a1f-108">podczas Nazwa metody do wyszukania.</span><span class="sxs-lookup"><span data-stu-id="21a1f-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="21a1f-109">podczas Wskaźnik do binarnego podpisu metadanych metody.</span><span class="sxs-lookup"><span data-stu-id="21a1f-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="21a1f-110">podczas Rozmiar w bajtach `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="21a1f-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="21a1f-111">określoną Wskaźnik do zgodnego tokenu MethodDef.</span><span class="sxs-lookup"><span data-stu-id="21a1f-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21a1f-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="21a1f-112">Remarks</span></span>  

 <span data-ttu-id="21a1f-113">Należy określić metodę przy użyciu jej klasy lub interfejsu ( `td` ), jej nazwy ( `szName` ) i opcjonalnie jej sygnatury ( `pvSigBlob` ).</span><span class="sxs-lookup"><span data-stu-id="21a1f-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="21a1f-114">Może istnieć wiele metod o tej samej nazwie w klasie lub interfejsie.</span><span class="sxs-lookup"><span data-stu-id="21a1f-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="21a1f-115">W takim przypadku Przekaż podpis metody, aby znaleźć unikatowe dopasowanie.</span><span class="sxs-lookup"><span data-stu-id="21a1f-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="21a1f-116">Sygnatura przekazano do `FindMethod` musi być wygenerowana w bieżącym zakresie, ponieważ sygnatury są powiązane z konkretnym zakresem.</span><span class="sxs-lookup"><span data-stu-id="21a1f-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="21a1f-117">Podpis może osadzić token, który identyfikuje otaczającą klasę lub typ wartości.</span><span class="sxs-lookup"><span data-stu-id="21a1f-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="21a1f-118">Token jest indeksem tabeli lokalnych TypeDef.</span><span class="sxs-lookup"><span data-stu-id="21a1f-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="21a1f-119">Nie można utworzyć podpisu w czasie wykonywania poza kontekstem bieżącego zakresu i użyć tej sygnatury jako danych wejściowych do `FindMethod` .</span><span class="sxs-lookup"><span data-stu-id="21a1f-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="21a1f-120">`FindMethod` znajduje tylko metody, które zostały zdefiniowane bezpośrednio w klasie lub interfejsie; nie znaleziono dziedziczonych metod.</span><span class="sxs-lookup"><span data-stu-id="21a1f-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21a1f-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="21a1f-121">Requirements</span></span>  

 <span data-ttu-id="21a1f-122">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21a1f-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21a1f-123">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="21a1f-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="21a1f-124">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="21a1f-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="21a1f-125">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21a1f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21a1f-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="21a1f-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="21a1f-127">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="21a1f-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="21a1f-128">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="21a1f-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
