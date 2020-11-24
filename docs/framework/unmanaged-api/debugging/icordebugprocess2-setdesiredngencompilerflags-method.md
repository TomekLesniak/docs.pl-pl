---
title: ICorDebugProcess2::SetDesiredNGENCompilerFlags — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
ms.openlocfilehash: 40b944f6a1204bfe506ed64408be30f68adf3170
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675259"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="dab11-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags — Metoda</span><span class="sxs-lookup"><span data-stu-id="dab11-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>

<span data-ttu-id="dab11-103">Ustawia flagi, które muszą być osadzone we wstępnie skompilowanym obrazie, aby środowisko uruchomieniowe ładowało ten obraz do bieżącego procesu.</span><span class="sxs-lookup"><span data-stu-id="dab11-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dab11-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="dab11-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dab11-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="dab11-105">Parameters</span></span>  

 `pdwFlags`  
 <span data-ttu-id="dab11-106">podczas Wartość wyliczenia [CorDebugJITCompilerFlags —](cordebugjitcompilerflags-enumeration.md) , która określa flagi kompilatora używane do wybierania poprawnego prekompilowanego obrazu.</span><span class="sxs-lookup"><span data-stu-id="dab11-106">[in] A value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dab11-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dab11-107">Remarks</span></span>  

 <span data-ttu-id="dab11-108">`SetDesiredNGENCompilerFlags`Metoda określa flagi, które muszą być osadzone we wstępnie skompilowanym obrazie, aby środowisko uruchomieniowe załadowało ten obraz do tego procesu.</span><span class="sxs-lookup"><span data-stu-id="dab11-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="dab11-109">Flagi ustawione za pomocą tej metody są używane tylko do wybierania poprawnego prekompilowanego obrazu.</span><span class="sxs-lookup"><span data-stu-id="dab11-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="dab11-110">Jeśli taki obraz nie istnieje, środowisko uruchomieniowe załaduje obraz języka pośredniego firmy Microsoft (MSIL) oraz kompilator just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="dab11-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="dab11-111">W takim przypadku debuger musi nadal używać metody [ICorDebugModule2:: SetJITCompilerFlags —](icordebugmodule2-setjitcompilerflags-method.md) , aby ustawić flagi zgodnie z potrzebami kompilacji JIT.</span><span class="sxs-lookup"><span data-stu-id="dab11-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="dab11-112">Jeśli obraz jest ładowany, ale niektóre kompilacje JIT muszą mieć miejsce dla tego obrazu (w przypadku, gdy obraz zawiera ogólne) flagi kompilatora określone przez `SetDesiredNGENCompilerFlags` metodę zostaną zastosowane do kompilacji dodatkowej JIT.</span><span class="sxs-lookup"><span data-stu-id="dab11-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="dab11-113">`SetDesiredNGENCompilerFlags`Metoda musi być wywoływana podczas wywołania zwrotnego [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dab11-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="dab11-114">Próby wywołania `SetDesiredNGENCompilerFlags` metody później zakończą się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="dab11-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="dab11-115">Ponadto program próbuje ustawić flagi, które nie są zdefiniowane w `CorDebugJITCompilerFlags` wyliczeniu lub które nie są dozwolone dla danego procesu, zakończą się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="dab11-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dab11-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="dab11-116">Requirements</span></span>  

 <span data-ttu-id="dab11-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dab11-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dab11-118">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="dab11-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dab11-119">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="dab11-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dab11-120">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dab11-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab11-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="dab11-121">See also</span></span>

- [<span data-ttu-id="dab11-122">ICorDebug — Interfejs</span><span class="sxs-lookup"><span data-stu-id="dab11-122">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="dab11-123">ICorDebugManagedCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="dab11-123">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
