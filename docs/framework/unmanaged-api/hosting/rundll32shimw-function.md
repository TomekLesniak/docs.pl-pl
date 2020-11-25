---
title: RunDll32ShimW — Funkcja
ms.date: 03/30/2017
api_name:
- RunDll32ShimW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- RunDll32ShimW
helpviewer_keywords:
- RunDll32ShimW function [.NET Framework hosting]
ms.assetid: 9ea07b57-96e2-44df-8711-8fe6c119087f
topic_type:
- apiref
ms.openlocfilehash: dd053134792b80a006849e465bc0025cf77a9ad8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729957"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="8f82c-102">RunDll32ShimW — Funkcja</span><span class="sxs-lookup"><span data-stu-id="8f82c-102">RunDll32ShimW Function</span></span>

<span data-ttu-id="8f82c-103">Wykonuje określone polecenie.</span><span class="sxs-lookup"><span data-stu-id="8f82c-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="8f82c-104">Ta funkcja jest przestarzała w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="8f82c-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f82c-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="8f82c-105">Syntax</span></span>  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f82c-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="8f82c-106">Parameters</span></span>  

 `hwnd`  
 <span data-ttu-id="8f82c-107">podczas Dojście do okna, w którym będą wyświetlane dane wyjściowe polecenia.</span><span class="sxs-lookup"><span data-stu-id="8f82c-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="8f82c-108">podczas Dojście do biblioteki zawierającej polecenie.</span><span class="sxs-lookup"><span data-stu-id="8f82c-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="8f82c-109">podczas Ciąg określający polecenie, które ma zostać wykonane.</span><span class="sxs-lookup"><span data-stu-id="8f82c-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="8f82c-110">podczas Liczba całkowita, która określa tryb wyświetlania okna danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="8f82c-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f82c-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8f82c-111">Requirements</span></span>  

 <span data-ttu-id="8f82c-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f82c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f82c-113">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8f82c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f82c-114">**Biblioteka:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8f82c-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f82c-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f82c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f82c-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8f82c-116">See also</span></span>

- [<span data-ttu-id="8f82c-117">Przestarzałe funkcje hostingu środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="8f82c-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
