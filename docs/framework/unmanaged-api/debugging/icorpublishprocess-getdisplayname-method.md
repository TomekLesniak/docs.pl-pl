---
title: ICorPublishProcess::GetDisplayName — Metoda
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
ms.openlocfilehash: 5a037695892252042d7827165595f7bad0feba56
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693167"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="453ff-102">ICorPublishProcess::GetDisplayName — Metoda</span><span class="sxs-lookup"><span data-stu-id="453ff-102">ICorPublishProcess::GetDisplayName Method</span></span>

<span data-ttu-id="453ff-103">Pobiera pełną ścieżkę pliku wykonywalnego dla procesu, do którego odwołuje się ten [ICorPublishProcess](icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="453ff-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="453ff-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="453ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="453ff-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="453ff-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="453ff-106">podczas Rozmiar `szName` tablicy.</span><span class="sxs-lookup"><span data-stu-id="453ff-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="453ff-107">określoną Liczba znaków dwubajtowych zwracanych w `szName` tablicy.</span><span class="sxs-lookup"><span data-stu-id="453ff-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="453ff-108">określoną Tablica do przechowywania nazwy, łącznie z pełną ścieżką pliku wykonywalnego.</span><span class="sxs-lookup"><span data-stu-id="453ff-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="453ff-109">Nazwa jest zakończona wartością null.</span><span class="sxs-lookup"><span data-stu-id="453ff-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="453ff-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="453ff-110">Requirements</span></span>  

 <span data-ttu-id="453ff-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="453ff-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="453ff-112">**Nagłówek:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="453ff-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="453ff-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="453ff-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="453ff-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="453ff-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="453ff-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="453ff-115">See also</span></span>

- [<span data-ttu-id="453ff-116">ICorPublishProcess — Interfejs</span><span class="sxs-lookup"><span data-stu-id="453ff-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
