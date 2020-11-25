---
title: ClrCreateManagedInstance — Funkcja
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
ms.openlocfilehash: 9aed79138499f1aa7b6fa3a28ad4505edd51b041
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731775"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="c43c2-102">ClrCreateManagedInstance — Funkcja</span><span class="sxs-lookup"><span data-stu-id="c43c2-102">ClrCreateManagedInstance Function</span></span>

<span data-ttu-id="c43c2-103">Tworzy wystąpienie określonego typu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="c43c2-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="c43c2-104">Ta funkcja jest przestarzała w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c43c2-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="c43c2-105">Przy użyciu aktywacji COM można utworzyć wystąpienie typu zarządzanego lub użyć hostingu (zobacz [Interfejsy hostingu środowiska CLR dodane w .NET Framework 4 i 4,5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span><span class="sxs-lookup"><span data-stu-id="c43c2-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c43c2-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="c43c2-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c43c2-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="c43c2-107">Parameters</span></span>  

 `pTypeName`  
 <span data-ttu-id="c43c2-108">podczas Wskaźnik do nazwy żądanego typu wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="c43c2-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="c43c2-109">podczas `IID` Typ żądanego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="c43c2-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="c43c2-110">określoną Wskaźnik do wskaźnika do wystąpienia typu zarządzanego, który zażądał obiekt wywołujący.</span><span class="sxs-lookup"><span data-stu-id="c43c2-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c43c2-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c43c2-111">Remarks</span></span>  

 <span data-ttu-id="c43c2-112">Środowisko uruchomieniowe języka wspólnego powinno być już załadowane do procesu.</span><span class="sxs-lookup"><span data-stu-id="c43c2-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="c43c2-113">Na przykład można go załadować przy użyciu wywołania funkcji [CorBindToRuntimeEx](corbindtoruntimeex-function.md) przed `ClrCreateManagedInstance` wywołaniem funkcji.</span><span class="sxs-lookup"><span data-stu-id="c43c2-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="c43c2-114">Jeśli środowisko uruchomieniowe nie zostało załadowane, program `ClrCreateManagedInstance` najpierw podejmie próbę załadowania 1.0.3705 środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="c43c2-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="c43c2-115">Jeśli to się nie powiedzie, zostanie podjęta próba załadowania najnowszej wersji środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="c43c2-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c43c2-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c43c2-116">Requirements</span></span>  

 <span data-ttu-id="c43c2-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c43c2-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c43c2-118">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c43c2-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c43c2-119">**Biblioteka:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c43c2-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c43c2-120">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c43c2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c43c2-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c43c2-121">See also</span></span>

- [<span data-ttu-id="c43c2-122">Przestarzałe funkcje hostingu środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="c43c2-122">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="c43c2-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="c43c2-123">Hosting</span></span>](index.md)
