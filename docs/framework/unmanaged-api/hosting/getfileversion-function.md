---
title: GetFileVersion — Funkcja
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
ms.openlocfilehash: 57b30824c7849127f48d4da61872945366e7141e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733246"
---
# <a name="getfileversion-function"></a><span data-ttu-id="74751-102">GetFileVersion — Funkcja</span><span class="sxs-lookup"><span data-stu-id="74751-102">GetFileVersion Function</span></span>

<span data-ttu-id="74751-103">Pobiera informacje o wersji środowiska uruchomieniowego języka wspólnego (CLR) określonego pliku przy użyciu określonego buforu.</span><span class="sxs-lookup"><span data-stu-id="74751-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="74751-104">Ta funkcja jest przestarzała w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="74751-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74751-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="74751-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74751-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="74751-106">Parameters</span></span>  

 `szFilename`  
 <span data-ttu-id="74751-107">podczas Ścieżka pliku, który ma zostać zbadany.</span><span class="sxs-lookup"><span data-stu-id="74751-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="74751-108">[in. out] Bufor przydzielony dla zwracanych informacji o wersji.</span><span class="sxs-lookup"><span data-stu-id="74751-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="74751-109">podczas Rozmiar, w postaci znaków dwubajtowych, z `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="74751-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="74751-110">określoną Rozmiar zwracanych wartości (w bajtach) `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="74751-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74751-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="74751-111">Requirements</span></span>  

 <span data-ttu-id="74751-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74751-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74751-113">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="74751-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74751-114">**.NET Framework wersje:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74751-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74751-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="74751-115">See also</span></span>

- [<span data-ttu-id="74751-116">Przestarzałe funkcje hostingu środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="74751-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
