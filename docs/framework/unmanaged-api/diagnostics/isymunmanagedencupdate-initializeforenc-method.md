---
title: ISymUnmanagedENCUpdate::InitializeForEnc — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.InitializeForEnc
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc
helpviewer_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc method [.NET Framework debugging]
- InitializeForEnc method [.NET Framework debugging]
ms.assetid: 796b2154-b53c-4d07-9e67-80fd6064725a
topic_type:
- apiref
ms.openlocfilehash: 96ac27bfd155eaf95b1880c2f4dee0e24330e446
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729047"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a><span data-ttu-id="22257-102">ISymUnmanagedENCUpdate::InitializeForEnc — Metoda</span><span class="sxs-lookup"><span data-stu-id="22257-102">ISymUnmanagedENCUpdate::InitializeForEnc Method</span></span>

<span data-ttu-id="22257-103">Umożliwia obliczenia granic metod przed pierwszym wywołaniem metody [ISymUnmanagedENCUpdate:: UpdateSymbolStore2 —](isymunmanagedencupdate-updatesymbolstore2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="22257-103">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22257-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="22257-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a><span data-ttu-id="22257-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="22257-105">Return Value</span></span>  

 <span data-ttu-id="22257-106">S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub inny kod błędu.</span><span class="sxs-lookup"><span data-stu-id="22257-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22257-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="22257-107">Requirements</span></span>  

 <span data-ttu-id="22257-108">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="22257-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22257-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="22257-109">See also</span></span>

- [<span data-ttu-id="22257-110">ISymUnmanagedENCUpdate — Interfejs</span><span class="sxs-lookup"><span data-stu-id="22257-110">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
