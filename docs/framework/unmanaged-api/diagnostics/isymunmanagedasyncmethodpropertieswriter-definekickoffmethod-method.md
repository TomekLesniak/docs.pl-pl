---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod — Metoda
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: 418a77855d1cb34a07f5957059b5a6f5a106c321
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707090"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="19a03-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod — Metoda</span><span class="sxs-lookup"><span data-stu-id="19a03-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>

<span data-ttu-id="19a03-103">Ustawia metodę początkową inicjującą operację asynchroniczną.</span><span class="sxs-lookup"><span data-stu-id="19a03-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19a03-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="19a03-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19a03-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="19a03-105">Parameters</span></span>  
  
|<span data-ttu-id="19a03-106">Parametr</span><span class="sxs-lookup"><span data-stu-id="19a03-106">Parameter</span></span>|<span data-ttu-id="19a03-107">Opis</span><span class="sxs-lookup"><span data-stu-id="19a03-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="19a03-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="19a03-108">Return Value</span></span>  

 <span data-ttu-id="19a03-109">Zwraca wartość `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="19a03-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19a03-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="19a03-110">Requirements</span></span>  

 <span data-ttu-id="19a03-111">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="19a03-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19a03-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="19a03-112">See also</span></span>

- [<span data-ttu-id="19a03-113">ISymUnmanagedAsyncMethodPropertiesWriter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="19a03-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
