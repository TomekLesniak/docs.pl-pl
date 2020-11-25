---
title: SetManifestFile — Metoda
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
ms.openlocfilehash: a4518e93db887dbdc4397636479be8bf5a705c2d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733727"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="c87e2-102">SetManifestFile — Metoda</span><span class="sxs-lookup"><span data-stu-id="c87e2-102">SetManifestFile Method</span></span>

<span data-ttu-id="c87e2-103">Umożliwia określenie lub zresetowanie pliku manifestu używanego przez konsolidatora podczas tworzenia zestawu.</span><span class="sxs-lookup"><span data-stu-id="c87e2-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c87e2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c87e2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c87e2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c87e2-105">Parameters</span></span>  

 `pszFile`  
  
 <span data-ttu-id="c87e2-106">Nazwa pliku manifestu, którego zawartość jest umieszczana w obiekcie blob zasobów Win32.</span><span class="sxs-lookup"><span data-stu-id="c87e2-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c87e2-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="c87e2-107">Return Value</span></span>  

 <span data-ttu-id="c87e2-108">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="c87e2-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c87e2-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c87e2-109">Remarks</span></span>  

 <span data-ttu-id="c87e2-110">Wywołaj to przed pytaniem o Win32ResBlob.</span><span class="sxs-lookup"><span data-stu-id="c87e2-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="c87e2-111">Wartość `pszFile` parametru jest nazwą pliku manifestu, którego zawartość jest odczytywana i umieszczana w zasobach Win32 o identyfikatorze RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="c87e2-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="c87e2-112">Gdy wywoływana przy użyciu parametru o wartości NULL, każdy poprzednio odczytany manifest jest czyszczony.</span><span class="sxs-lookup"><span data-stu-id="c87e2-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="c87e2-113">Umożliwia to jednemu resetowaniu stanu konsolidatora do czasu inicjacji.</span><span class="sxs-lookup"><span data-stu-id="c87e2-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c87e2-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c87e2-114">Requirements</span></span>  

 <span data-ttu-id="c87e2-115">Wymaga aLink. h</span><span class="sxs-lookup"><span data-stu-id="c87e2-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c87e2-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c87e2-116">See also</span></span>

- [<span data-ttu-id="c87e2-117">IALink3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c87e2-117">IALink3 Interface</span></span>](ialink3-interface.md)
- [<span data-ttu-id="c87e2-118">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="c87e2-118">ALink API</span></span>](index.md)
- [<span data-ttu-id="c87e2-119">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c87e2-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c87e2-120">Al.exe (Konsolidator zestawu)</span><span class="sxs-lookup"><span data-stu-id="c87e2-120">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
