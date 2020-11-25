---
title: StrongNameHashSize — Funkcja
ms.date: 03/30/2017
api_name:
- StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameHashSize
helpviewer_keywords:
- StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type:
- apiref
ms.openlocfilehash: 1116fcde754f966a783f4fdca85df8bd3ca1b0ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724445"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="0e7cb-102">StrongNameHashSize — Funkcja</span><span class="sxs-lookup"><span data-stu-id="0e7cb-102">StrongNameHashSize Function</span></span>

<span data-ttu-id="0e7cb-103">Pobiera rozmiar buforu wymagany dla skrótu przy użyciu określonego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="0e7cb-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="0e7cb-104">Ta funkcja jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="0e7cb-104">This function has been deprecated.</span></span> <span data-ttu-id="0e7cb-105">Zamiast tego użyj metody [ICLRStrongName:: StrongNameHashSize —](../hosting/iclrstrongname-strongnamehashsize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0e7cb-105">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e7cb-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="0e7cb-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e7cb-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="0e7cb-107">Parameters</span></span>  

 `ulHashAlg`  
 <span data-ttu-id="0e7cb-108">podczas Algorytm wyznaczania wartości skrótu używany do obliczania rozmiaru buforu.</span><span class="sxs-lookup"><span data-stu-id="0e7cb-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="0e7cb-109">określoną Zwrócony rozmiar buforu w bajtach.</span><span class="sxs-lookup"><span data-stu-id="0e7cb-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e7cb-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="0e7cb-110">Return Value</span></span>  

 <span data-ttu-id="0e7cb-111">`true` Po pomyślnym zakończeniu; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="0e7cb-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e7cb-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0e7cb-112">Remarks</span></span>  

 <span data-ttu-id="0e7cb-113">Jeśli `StrongNameHashSize` Funkcja nie zakończy się pomyślnie, wywołaj funkcję [StrongNameErrorInfo —](strongnameerrorinfo-function.md) w celu pobrania ostatniego wygenerowanego błędu.</span><span class="sxs-lookup"><span data-stu-id="0e7cb-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e7cb-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0e7cb-114">Requirements</span></span>  

 <span data-ttu-id="0e7cb-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e7cb-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e7cb-116">**Nagłówek:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="0e7cb-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0e7cb-117">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0e7cb-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0e7cb-118">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e7cb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e7cb-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0e7cb-119">See also</span></span>

- [<span data-ttu-id="0e7cb-120">StrongNameHashSize, metoda</span><span class="sxs-lookup"><span data-stu-id="0e7cb-120">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="0e7cb-121">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0e7cb-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
