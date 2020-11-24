---
title: 'ICorDebugSymbolProvider2:: GetFrameProps, Metoda'
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
ms.openlocfilehash: ba1fd104c35b6e6dfdfd771f71eb19f8d532a1d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672014"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="33dd1-102">ICorDebugSymbolProvider2:: GetFrameProps, Metoda</span><span class="sxs-lookup"><span data-stu-id="33dd1-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>

<span data-ttu-id="33dd1-103">Zwraca metodę rozpoczynającą względny adres wirtualny metody i ramkę nadrzędną, w której znajduje się adres wirtualny względem kodu.</span><span class="sxs-lookup"><span data-stu-id="33dd1-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33dd1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="33dd1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33dd1-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="33dd1-105">Parameters</span></span>  

 `codeRva`  
 <span data-ttu-id="33dd1-106">podczas Względny adres wirtualny.</span><span class="sxs-lookup"><span data-stu-id="33dd1-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="33dd1-107">określoną Wskaźnik do początkowego adresu wirtualnego względnej metody.</span><span class="sxs-lookup"><span data-stu-id="33dd1-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="33dd1-108">określoną Wskaźnik do początkowego adresu wirtualnego ramki.</span><span class="sxs-lookup"><span data-stu-id="33dd1-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33dd1-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="33dd1-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33dd1-110">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="33dd1-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33dd1-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="33dd1-111">Requirements</span></span>  

 <span data-ttu-id="33dd1-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33dd1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33dd1-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="33dd1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33dd1-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="33dd1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33dd1-115">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33dd1-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33dd1-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="33dd1-116">See also</span></span>

- [<span data-ttu-id="33dd1-117">ICorDebugSymbolProvider2, interfejs</span><span class="sxs-lookup"><span data-stu-id="33dd1-117">ICorDebugSymbolProvider2 Interface</span></span>](icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="33dd1-118">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="33dd1-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
