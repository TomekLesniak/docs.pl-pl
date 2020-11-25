---
title: IMetaDataImport::GetNativeCallConvFromSig — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNativeCallConvFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type:
- apiref
ms.openlocfilehash: d44ad493a786aaa35150515b7c254965490bd714
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701708"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="ab533-102">IMetaDataImport::GetNativeCallConvFromSig — Metoda</span><span class="sxs-lookup"><span data-stu-id="ab533-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>

<span data-ttu-id="ab533-103">Pobiera natywną konwencję wywoływania dla metody reprezentowanej przez określony wskaźnik podpisu.</span><span class="sxs-lookup"><span data-stu-id="ab533-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab533-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ab533-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab533-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ab533-105">Parameters</span></span>  

 `pvSig`  
 <span data-ttu-id="ab533-106">podczas Wskaźnik do sygnatury metadanych metody zwracającej konwencję wywoływania.</span><span class="sxs-lookup"><span data-stu-id="ab533-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="ab533-107">podczas Rozmiar w bajtach `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="ab533-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="ab533-108">określoną Wskaźnik do natywnej konwencji wywoływania.</span><span class="sxs-lookup"><span data-stu-id="ab533-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab533-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ab533-109">Requirements</span></span>  

 <span data-ttu-id="ab533-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab533-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab533-111">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ab533-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab533-112">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ab533-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ab533-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab533-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab533-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ab533-114">See also</span></span>

- <xref:System.Runtime.InteropServices.CallingConvention>
- [<span data-ttu-id="ab533-115">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ab533-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ab533-116">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ab533-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
