---
title: _EFN_GetManagedObjectFieldInfo — Funkcja
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
ms.openlocfilehash: 4c088b7e1096f8b4cad11a3e27b4045e233989ae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676221"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a><span data-ttu-id="13aab-102">\_\_Funkcja EFN GetManagedObjectFieldInfo</span><span class="sxs-lookup"><span data-stu-id="13aab-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>

<span data-ttu-id="13aab-103">Pobiera przesunięcie od początku obiektu do pola i wartości pola przy użyciu podanego wskaźnika obiektu i nazwy pola.</span><span class="sxs-lookup"><span data-stu-id="13aab-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13aab-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="13aab-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13aab-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="13aab-105">Parameters</span></span>  

 `Client`  
 <span data-ttu-id="13aab-106">podczas Wskaźnik do klienta debugowania.</span><span class="sxs-lookup"><span data-stu-id="13aab-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="13aab-107">podczas Wskaźnik obiektu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="13aab-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="13aab-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="13aab-108">szFieldName</span></span>  
 <span data-ttu-id="13aab-109">podczas Wskaźnik obiektu zarządzanego do nazwy pola.</span><span class="sxs-lookup"><span data-stu-id="13aab-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="13aab-110">określoną Wartość pola.</span><span class="sxs-lookup"><span data-stu-id="13aab-110">[out] The field value.</span></span> <span data-ttu-id="13aab-111">Ten parametr może mieć wartość null.</span><span class="sxs-lookup"><span data-stu-id="13aab-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="13aab-112">określoną Przesunięcie od `objAddr` do pola.</span><span class="sxs-lookup"><span data-stu-id="13aab-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="13aab-113">Ten parametr może mieć wartość null.</span><span class="sxs-lookup"><span data-stu-id="13aab-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13aab-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="13aab-114">Remarks</span></span>  

 <span data-ttu-id="13aab-115">Jeśli przesunięcie ma wartość 0, przesunięcie nie jest zapisywane.</span><span class="sxs-lookup"><span data-stu-id="13aab-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="13aab-116">W przypadku braku kodu zarządzanego w wątku, który jest obecnie w kontekście, funkcja zwraca wartość HRESULT SOS_E_NOMANAGEDCODE z wartością instrumentu 0xa0 i kodem błędu 0x1000.</span><span class="sxs-lookup"><span data-stu-id="13aab-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13aab-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="13aab-117">Requirements</span></span>  

 <span data-ttu-id="13aab-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13aab-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13aab-119">**Nagłówek:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="13aab-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="13aab-120">**Wersja .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13aab-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13aab-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="13aab-121">See also</span></span>

- [<span data-ttu-id="13aab-122">Debugowanie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="13aab-122">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
