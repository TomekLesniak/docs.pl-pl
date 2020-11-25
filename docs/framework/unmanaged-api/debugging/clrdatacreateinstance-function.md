---
title: CLRDataCreateInstance — Funkcja
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
ms.openlocfilehash: 2ffc575cfcef1089a70ef3b6d38787a5b4c50443
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729827"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="c1d79-102">CLRDataCreateInstance — Funkcja</span><span class="sxs-lookup"><span data-stu-id="c1d79-102">CLRDataCreateInstance Function</span></span>

<span data-ttu-id="c1d79-103">Tworzy obiekt interfejsu dla określonego elementu docelowego.</span><span class="sxs-lookup"><span data-stu-id="c1d79-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1d79-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c1d79-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,
    [in]  ICLRDataTarget  *target,
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1d79-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c1d79-105">Parameters</span></span>  

 `iid`  
 <span data-ttu-id="c1d79-106">podczas Identyfikator interfejsu, który ma zostać utworzony.</span><span class="sxs-lookup"><span data-stu-id="c1d79-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="c1d79-107">podczas Wskaźnik do obiektu [ICLRDataTarget](iclrdatatarget-interface.md) zaimplementowanego przez użytkownika, który reprezentuje element docelowy, dla którego ma zostać utworzony obiekt interfejsu.</span><span class="sxs-lookup"><span data-stu-id="c1d79-107">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="c1d79-108">określoną Wskaźnik do adresu zwróconego obiektu interfejsu.</span><span class="sxs-lookup"><span data-stu-id="c1d79-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1d79-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c1d79-109">Remarks</span></span>  

 <span data-ttu-id="c1d79-110">`ICLRDataTarget`Obiekt jest implementowany przez moduł zapisujący aplikacji debugowania.</span><span class="sxs-lookup"><span data-stu-id="c1d79-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="c1d79-111">Implementacja zależy od typu reprezentowanego elementu docelowego.</span><span class="sxs-lookup"><span data-stu-id="c1d79-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="c1d79-112">Element docelowy może być procesem, zrzutem pamięci, maszyną zdalną i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="c1d79-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1d79-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c1d79-113">Requirements</span></span>  

 <span data-ttu-id="c1d79-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1d79-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1d79-115">**Nagłówek:** ClrData. idl</span><span class="sxs-lookup"><span data-stu-id="c1d79-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="c1d79-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c1d79-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1d79-117">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1d79-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1d79-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c1d79-118">See also</span></span>

- [<span data-ttu-id="c1d79-119">Debugowanie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="c1d79-119">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
