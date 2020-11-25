---
title: ICLRMetaHost::ExitProcess — Metoda
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
ms.openlocfilehash: 6d601ac3ece801353b630c74ed852c2657f25d7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730467"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="b7b1d-102">ICLRMetaHost::ExitProcess — Metoda</span><span class="sxs-lookup"><span data-stu-id="b7b1d-102">ICLRMetaHost::ExitProcess Method</span></span>

<span data-ttu-id="b7b1d-103">Próbuje bezpiecznie zamknąć wszystkie ładowane środowiska uruchomieniowe, a następnie kończy proces.</span><span class="sxs-lookup"><span data-stu-id="b7b1d-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="b7b1d-104">Zastępuje funkcję [CorExitProcess —](corexitprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="b7b1d-104">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7b1d-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="b7b1d-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7b1d-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="b7b1d-106">Parameters</span></span>  

 `iExitCode`  
 <span data-ttu-id="b7b1d-107">podczas Kod zakończenia procesu.</span><span class="sxs-lookup"><span data-stu-id="b7b1d-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7b1d-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="b7b1d-108">Return Value</span></span>  

 <span data-ttu-id="b7b1d-109">Ta metoda nigdy nie zwraca, więc jej wartość zwracana jest niezdefiniowana.</span><span class="sxs-lookup"><span data-stu-id="b7b1d-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7b1d-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b7b1d-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7b1d-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b7b1d-111">Requirements</span></span>  

 <span data-ttu-id="b7b1d-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7b1d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7b1d-113">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="b7b1d-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b7b1d-114">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7b1d-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7b1d-115">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7b1d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7b1d-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b7b1d-116">See also</span></span>

- [<span data-ttu-id="b7b1d-117">ICLRMetaHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b7b1d-117">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="b7b1d-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="b7b1d-118">Hosting</span></span>](index.md)
