---
title: IMetaDataImport::GetParamForMethodIndex — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamForMethodIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type:
- apiref
ms.openlocfilehash: d4d3ba5713398876b55c072f0cda7eb5d599c4d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729290"
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="cb95b-102">IMetaDataImport::GetParamForMethodIndex — Metoda</span><span class="sxs-lookup"><span data-stu-id="cb95b-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>

<span data-ttu-id="cb95b-103">Pobiera token reprezentujący określony parametr metody reprezentowanej przez określony token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="cb95b-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb95b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cb95b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb95b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="cb95b-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="cb95b-106">podczas Token reprezentujący metodę zwracającą token parametru dla.</span><span class="sxs-lookup"><span data-stu-id="cb95b-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="cb95b-107">podczas Pozycja porządkowa na liście parametrów, w której występuje żądany parametr.</span><span class="sxs-lookup"><span data-stu-id="cb95b-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="cb95b-108">Parametry są numerowane Zaczynając od jednej, z wartością zwracaną metody w pozycji zero.</span><span class="sxs-lookup"><span data-stu-id="cb95b-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="cb95b-109">określoną Wskaźnik do tokenu ParamDef, który reprezentuje żądany parametr.</span><span class="sxs-lookup"><span data-stu-id="cb95b-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb95b-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cb95b-110">Requirements</span></span>  

 <span data-ttu-id="cb95b-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb95b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb95b-112">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cb95b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cb95b-113">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb95b-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cb95b-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb95b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb95b-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cb95b-115">See also</span></span>

- [<span data-ttu-id="cb95b-116">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cb95b-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="cb95b-117">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cb95b-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
