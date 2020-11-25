---
title: IMetaDataImport::FindField — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
ms.openlocfilehash: 9b42f0f7c8e2878ee3ec140344f51517a24247c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729866"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="883bd-102">IMetaDataImport::FindField — Metoda</span><span class="sxs-lookup"><span data-stu-id="883bd-102">IMetaDataImport::FindField Method</span></span>

<span data-ttu-id="883bd-103">Pobiera wskaźnik do tokenu FieldDef dla pola, które jest ujęte w określonym <xref:System.Type> i który ma określoną nazwę i sygnaturę metadanych.</span><span class="sxs-lookup"><span data-stu-id="883bd-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="883bd-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="883bd-104">Syntax</span></span>  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="883bd-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="883bd-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="883bd-106">podczas Token TypeDef dla klasy lub interfejsu, który obejmuje pole, które ma zostać wyszukane.</span><span class="sxs-lookup"><span data-stu-id="883bd-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="883bd-107">Jeśli ta wartość jest `mdTokenNil` , wyszukiwanie jest wykonywane dla zmiennej globalnej.</span><span class="sxs-lookup"><span data-stu-id="883bd-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="883bd-108">podczas Nazwa pola, które ma zostać wyszukane.</span><span class="sxs-lookup"><span data-stu-id="883bd-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="883bd-109">podczas Wskaźnik do binarnego podpisu metadanych pola.</span><span class="sxs-lookup"><span data-stu-id="883bd-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="883bd-110">podczas Rozmiar w bajtach `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="883bd-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="883bd-111">określoną Wskaźnik do zgodnego tokenu FieldDef.</span><span class="sxs-lookup"><span data-stu-id="883bd-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="883bd-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="883bd-112">Remarks</span></span>  

 <span data-ttu-id="883bd-113">Należy określić pole przy użyciu jego klasy lub interfejsu ( `td` ), jego nazwy ( `szName` ) i opcjonalnie jego sygnatury ( `pvSigBlob` ).</span><span class="sxs-lookup"><span data-stu-id="883bd-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="883bd-114">Sygnatura przekazano do `FindField` musi być wygenerowana w bieżącym zakresie, ponieważ sygnatury są powiązane z konkretnym zakresem.</span><span class="sxs-lookup"><span data-stu-id="883bd-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="883bd-115">Podpis może osadzić token, który identyfikuje otaczającą klasę lub typ wartości.</span><span class="sxs-lookup"><span data-stu-id="883bd-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="883bd-116">(Token jest indeksem w lokalnej tabeli TypeDef).</span><span class="sxs-lookup"><span data-stu-id="883bd-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="883bd-117">Nie można utworzyć podpisu w czasie wykonywania poza kontekstem bieżącego zakresu i użyć tej sygnatury jako danych wejściowych `FindField` .</span><span class="sxs-lookup"><span data-stu-id="883bd-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="883bd-118">`FindField` znajduje tylko pola, które zostały zdefiniowane bezpośrednio w klasie lub interfejsie; nie znajdują się w nim dziedziczone pola.</span><span class="sxs-lookup"><span data-stu-id="883bd-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="883bd-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="883bd-119">Requirements</span></span>  

 <span data-ttu-id="883bd-120">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="883bd-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="883bd-121">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="883bd-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="883bd-122">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="883bd-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="883bd-123">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="883bd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="883bd-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="883bd-124">See also</span></span>

- [<span data-ttu-id="883bd-125">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="883bd-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="883bd-126">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="883bd-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
