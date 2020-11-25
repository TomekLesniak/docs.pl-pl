---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod — Metoda
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
ms.openlocfilehash: 2d4515087812b2b7c9303228ac5e5bbf34e8aa91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707194"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="73241-102">ISymUnmanagedAsyncMethod::GetKickoffMethod — Metoda</span><span class="sxs-lookup"><span data-stu-id="73241-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>

<span data-ttu-id="73241-103">Zobacz [DefineKickoffMethod —](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="73241-103">See [DefineKickoffMethod Method](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73241-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="73241-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73241-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="73241-105">Parameters</span></span>  
  
|<span data-ttu-id="73241-106">Parametr</span><span class="sxs-lookup"><span data-stu-id="73241-106">Parameter</span></span>|<span data-ttu-id="73241-107">Opis</span><span class="sxs-lookup"><span data-stu-id="73241-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="73241-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="73241-108">Return Value</span></span>  

 <span data-ttu-id="73241-109">Zwraca wartość `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="73241-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73241-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="73241-110">Requirements</span></span>  

 <span data-ttu-id="73241-111">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="73241-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73241-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="73241-112">See also</span></span>

- [<span data-ttu-id="73241-113">ISymUnmanagedAsyncMethod — Interfejs</span><span class="sxs-lookup"><span data-stu-id="73241-113">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
