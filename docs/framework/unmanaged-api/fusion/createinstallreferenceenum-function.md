---
title: CreateInstallReferenceEnum — Funkcja
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
ms.openlocfilehash: 0f62b05ebbd8b27dba160c8281c1d40748c90fc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688838"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="2f6df-102">CreateInstallReferenceEnum — Funkcja</span><span class="sxs-lookup"><span data-stu-id="2f6df-102">CreateInstallReferenceEnum Function</span></span>

<span data-ttu-id="2f6df-103">Pobiera wskaźnik do wystąpienia [IInstallReferenceEnum](iinstallreferenceenum-interface.md) , które reprezentuje listę odwołań aplikacji do określonego zestawu.</span><span class="sxs-lookup"><span data-stu-id="2f6df-103">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f6df-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2f6df-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f6df-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2f6df-105">Parameters</span></span>  

 `ppRefEnum`  
 <span data-ttu-id="2f6df-106">określoną Zwrócony `IInstallReferenceEnum` wskaźnik.</span><span class="sxs-lookup"><span data-stu-id="2f6df-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="2f6df-107">podczas [IAssemblyName](iassemblyname-interface.md) , który identyfikuje zestaw, dla którego mają zostać wyliczone odwołania.</span><span class="sxs-lookup"><span data-stu-id="2f6df-107">[in] The [IAssemblyName](iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2f6df-108">podczas Flagi wpływające na zachowanie modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="2f6df-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="2f6df-109">podczas Zarezerwowane do użytku w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="2f6df-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="2f6df-110">`pvReserved` musi być odwołaniem o wartości null.</span><span class="sxs-lookup"><span data-stu-id="2f6df-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f6df-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2f6df-111">Requirements</span></span>  

 <span data-ttu-id="2f6df-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f6df-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f6df-113">**Nagłówek:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="2f6df-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2f6df-114">**Biblioteka:** Fusion.dll i Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="2f6df-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="2f6df-115">Użyj Fusion.dll zamiast Mscorwks.dll, aby upewnić się, że docelowa jest poprawna wersja .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f6df-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="2f6df-116">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f6df-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f6df-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2f6df-117">See also</span></span>

- [<span data-ttu-id="2f6df-118">IInstallReferenceEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2f6df-118">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
- [<span data-ttu-id="2f6df-119">IAssemblyName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2f6df-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="2f6df-120">Łączenie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="2f6df-120">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
