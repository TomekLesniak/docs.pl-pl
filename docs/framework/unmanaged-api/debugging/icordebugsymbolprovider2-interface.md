---
title: ICorDebugSymbolProvider2, interfejs
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: 3bef03e9e85224058bc17e1f0ce8746e98aa30f6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688344"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="80215-102">ICorDebugSymbolProvider2, interfejs</span><span class="sxs-lookup"><span data-stu-id="80215-102">ICorDebugSymbolProvider2 Interface</span></span>

<span data-ttu-id="80215-103">Logicznie rozszerza interfejs [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) w celu pobrania dodatkowych informacji o symbolach debugowania.</span><span class="sxs-lookup"><span data-stu-id="80215-103">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80215-104">Metody</span><span class="sxs-lookup"><span data-stu-id="80215-104">Methods</span></span>  
  
|<span data-ttu-id="80215-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="80215-105">Method</span></span>|<span data-ttu-id="80215-106">Opis</span><span class="sxs-lookup"><span data-stu-id="80215-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80215-107">GetFrameProps, metoda</span><span class="sxs-lookup"><span data-stu-id="80215-107">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="80215-108">Zwraca metodę rozpoczynającą względny adres wirtualny metody i ramkę nadrzędną, w której znajduje się adres wirtualny względem kodu.</span><span class="sxs-lookup"><span data-stu-id="80215-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="80215-109">GetGenericDictionaryInfo, metoda</span><span class="sxs-lookup"><span data-stu-id="80215-109">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="80215-110">Pobiera mapę ogólnego słownika.</span><span class="sxs-lookup"><span data-stu-id="80215-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80215-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="80215-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80215-112">Ten interfejs jest dostępny tylko dla .NET Native.</span><span class="sxs-lookup"><span data-stu-id="80215-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="80215-113">W przypadku zaimplementowania tego interfejsu dla scenariuszy ICorDebug poza .NET Native, środowisko uruchomieniowe języka wspólnego zignoruje ten interfejs.</span><span class="sxs-lookup"><span data-stu-id="80215-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80215-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="80215-114">Requirements</span></span>  

 <span data-ttu-id="80215-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80215-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80215-116">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="80215-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80215-117">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="80215-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80215-118">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80215-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80215-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="80215-119">See also</span></span>

- [<span data-ttu-id="80215-120">ICorDebugSymbolProvider, interfejs</span><span class="sxs-lookup"><span data-stu-id="80215-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="80215-121">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="80215-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="80215-122">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="80215-122">Debugging</span></span>](index.md)
