---
title: _CorExeMain — Funkcja
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
ms.openlocfilehash: af1d0e2039024a51341e30bec497c581a0bcacb3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673673"
---
# <a name="_corexemain-function"></a><span data-ttu-id="80998-102">_CorExeMain — Funkcja</span><span class="sxs-lookup"><span data-stu-id="80998-102">_CorExeMain Function</span></span>

<span data-ttu-id="80998-103">Inicjuje środowisko uruchomieniowe języka wspólnego (CLR), lokalizuje zarządzany punkt wejścia w nagłówku CLR zestawu wykonywalnego i rozpoczyna wykonywanie.</span><span class="sxs-lookup"><span data-stu-id="80998-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80998-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="80998-104">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="80998-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="80998-105">Remarks</span></span>  

 <span data-ttu-id="80998-106">Ta funkcja jest wywoływana przez moduł ładujący w ramach procesów utworzonych z zarządzanych zestawów plików wykonywalnych.</span><span class="sxs-lookup"><span data-stu-id="80998-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="80998-107">W przypadku zestawów bibliotek DLL moduł ładujący wywołuje funkcję [_CorDllMain](cordllmain-function.md) .</span><span class="sxs-lookup"><span data-stu-id="80998-107">For DLL assemblies, the loader calls the [_CorDllMain](cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="80998-108">Moduł ładujący systemu operacyjnego wywołuje tę metodę niezależnie od punktu wejścia określonego w pliku obrazu.</span><span class="sxs-lookup"><span data-stu-id="80998-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="80998-109">W systemach Windows 98, Windows ME, Windows NT i Windows 2000 `_CorExeMain` Funkcja jest wywoływana pośrednio przez korektę w module ładującym systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="80998-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="80998-110">We wszystkich innych wersjach systemu Windows jest on wywoływany bezpośrednio przez program ładujący systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="80998-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="80998-111">Aby uzyskać dodatkowe informacje, zobacz sekcję Uwagi w temacie [_CorValidateImage](corvalidateimage-function.md) .</span><span class="sxs-lookup"><span data-stu-id="80998-111">For additional information, see the Remarks section in the [_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80998-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="80998-112">Requirements</span></span>  

 <span data-ttu-id="80998-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80998-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80998-114">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="80998-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80998-115">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80998-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80998-116">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80998-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80998-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="80998-117">See also</span></span>

- [<span data-ttu-id="80998-118">Statyczne funkcje globalne metadanych</span><span class="sxs-lookup"><span data-stu-id="80998-118">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
