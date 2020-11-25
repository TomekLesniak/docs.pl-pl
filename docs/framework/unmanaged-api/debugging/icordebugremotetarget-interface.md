---
title: ICorDebugRemoteTarget — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
ms.openlocfilehash: 4212597b5ba43f0e4767aa585ca28a011e73e07a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711991"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="4ca6e-102">ICorDebugRemoteTarget — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4ca6e-102">ICorDebugRemoteTarget Interface</span></span>

<span data-ttu-id="4ca6e-103">Dostarcza metody, które umożliwiają deweloperom debugowanie aplikacji opartych na technologii Silverlight w środowisku środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="4ca6e-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ca6e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4ca6e-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4ca6e-105">Metody</span><span class="sxs-lookup"><span data-stu-id="4ca6e-105">Methods</span></span>  
  
|<span data-ttu-id="4ca6e-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="4ca6e-106">Method</span></span>|<span data-ttu-id="4ca6e-107">Opis</span><span class="sxs-lookup"><span data-stu-id="4ca6e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4ca6e-108">ICorDebugRemoteTarget::GetHostName — Metoda</span><span class="sxs-lookup"><span data-stu-id="4ca6e-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="4ca6e-109">Zwraca nazwę hosta lub adres IP komputera zdalnego.</span><span class="sxs-lookup"><span data-stu-id="4ca6e-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ca6e-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4ca6e-110">Remarks</span></span>  

 <span data-ttu-id="4ca6e-111">Debugowanie w trybie mieszanym (czyli kod zarządzany i natywny) nie jest obsługiwane w systemach Windows 95, Windows 98 lub Windows ME ani na platformach innych niż x86 (takich jak IA-64 i AMD64).</span><span class="sxs-lookup"><span data-stu-id="4ca6e-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ca6e-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4ca6e-112">Requirements</span></span>  

 <span data-ttu-id="4ca6e-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ca6e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ca6e-114">**Nagłówek:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="4ca6e-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="4ca6e-115">**Library:** : CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4ca6e-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ca6e-116">**.NET Framework wersje:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="4ca6e-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca6e-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4ca6e-117">See also</span></span>

- [<span data-ttu-id="4ca6e-118">ICorDebugRemote — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4ca6e-118">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="4ca6e-119">ICorDebug — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4ca6e-119">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="4ca6e-120">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="4ca6e-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
