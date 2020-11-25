---
title: GetAssemblyRefHash — Metoda
ms.date: 03/30/2017
api_name:
- IALink.GetAssemblyRefHash
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetAssemblyRefHash
helpviewer_keywords:
- GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type:
- apiref
ms.openlocfilehash: af040c4a6c9b85930d2d9261f8587ba69eb204e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721481"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="9c90d-102">GetAssemblyRefHash — Metoda</span><span class="sxs-lookup"><span data-stu-id="9c90d-102">GetAssemblyRefHash Method</span></span>

<span data-ttu-id="9c90d-103">Pobiera obiekt BLOB mieszania dla danego zestawu.</span><span class="sxs-lookup"><span data-stu-id="9c90d-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c90d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9c90d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c90d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="9c90d-105">Parameters</span></span>  

 `FileToken`  
 <span data-ttu-id="9c90d-106">Identyfikator zestawu, do którego odwołuje się skrót.</span><span class="sxs-lookup"><span data-stu-id="9c90d-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="9c90d-107">Odbiera wynikowy obiekt BLOB.</span><span class="sxs-lookup"><span data-stu-id="9c90d-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="9c90d-108">Odbiera rozmiar, w bajtach, obiektu BLOB mieszania.</span><span class="sxs-lookup"><span data-stu-id="9c90d-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c90d-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="9c90d-109">Return Value</span></span>  

 <span data-ttu-id="9c90d-110">Zwraca S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="9c90d-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c90d-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9c90d-111">Requirements</span></span>  

 <span data-ttu-id="9c90d-112">Wymaga Alink. h</span><span class="sxs-lookup"><span data-stu-id="9c90d-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c90d-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9c90d-113">See also</span></span>

- [<span data-ttu-id="9c90d-114">IALink — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9c90d-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="9c90d-115">IALink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9c90d-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="9c90d-116">ALink — interfejs API</span><span class="sxs-lookup"><span data-stu-id="9c90d-116">ALink API</span></span>](index.md)
