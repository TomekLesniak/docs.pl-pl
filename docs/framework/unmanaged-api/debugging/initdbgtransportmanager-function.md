---
title: InitDbgTransportManager — Funkcja
ms.date: 03/30/2017
api_name:
- InitDbgTransportManager
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- InitDbgTransportManager
helpviewer_keywords:
- remote debugging API [Silverlight]
- InitDbgTransportManager function
- Silverlight, remote debugging
ms.assetid: a30102ff-c52e-48c9-b3a9-aa14286a42b2
topic_type:
- apiref
ms.openlocfilehash: a5b4783eadb8045733b9ebd6d10c4e31f7829498
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716684"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="751ce-102">InitDbgTransportManager — Funkcja</span><span class="sxs-lookup"><span data-stu-id="751ce-102">InitDbgTransportManager Function</span></span>

<span data-ttu-id="751ce-103">Inicjuje menedżera transportu, aby połączyć się ze zdalnym elementem docelowym na potrzeby wyliczenia procesu i środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="751ce-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="751ce-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="751ce-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="751ce-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="751ce-105">Return Value</span></span>  

 <span data-ttu-id="751ce-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="751ce-106">S_OK</span></span>  
 <span data-ttu-id="751ce-107">Powodzenie.</span><span class="sxs-lookup"><span data-stu-id="751ce-107">Success.</span></span>  
  
 <span data-ttu-id="751ce-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="751ce-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="751ce-109">Funkcja nie może przydzielić pamięci dla menedżera transportu.</span><span class="sxs-lookup"><span data-stu-id="751ce-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="751ce-110">E_FAIL (lub inne kody powrotne E_)</span><span class="sxs-lookup"><span data-stu-id="751ce-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="751ce-111">Inne błędy.</span><span class="sxs-lookup"><span data-stu-id="751ce-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="751ce-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="751ce-112">Requirements</span></span>  

 <span data-ttu-id="751ce-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="751ce-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="751ce-114">**Nagłówek:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="751ce-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="751ce-115">**Biblioteka:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="751ce-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="751ce-116">**.NET Framework wersje:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="751ce-116">**.NET Framework Versions:** 3.5 SP1</span></span>
