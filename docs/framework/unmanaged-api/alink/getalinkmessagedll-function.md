---
title: GetALinkMessageDll — Funkcja
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
ms.openlocfilehash: 554bd32ae965b21a88a09577749bbd7975f5ec7e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684749"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="d3bc1-102">GetALinkMessageDll — Funkcja</span><span class="sxs-lookup"><span data-stu-id="d3bc1-102">GetALinkMessageDll Function</span></span>

<span data-ttu-id="d3bc1-103">Umożliwia znalezienie i załadowanie biblioteki DLL komunikatów.</span><span class="sxs-lookup"><span data-stu-id="d3bc1-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="d3bc1-104">Zwraca wartość 0, jeśli nie można odnaleźć lub załadować biblioteki DLL komunikatu.</span><span class="sxs-lookup"><span data-stu-id="d3bc1-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="d3bc1-105">Biblioteka DLL komunikatów powinna znajdować się w podkatalogu, którego nazwa jest IDENTYFIKATORem języka lub w bieżącym katalogu.</span><span class="sxs-lookup"><span data-stu-id="d3bc1-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3bc1-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="d3bc1-106">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="d3bc1-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d3bc1-107">Requirements</span></span>  

 <span data-ttu-id="d3bc1-108">**Nagłówek:** Alink. h</span><span class="sxs-lookup"><span data-stu-id="d3bc1-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="d3bc1-109">**Biblioteka**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="d3bc1-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3bc1-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d3bc1-110">See also</span></span>

- [<span data-ttu-id="d3bc1-111">Al.exe (Konsolidator zestawu)</span><span class="sxs-lookup"><span data-stu-id="d3bc1-111">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
