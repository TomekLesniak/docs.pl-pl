---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset — Metoda
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: a37d319a39b959700944f9e111d2945e286c99ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707142"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="93ea6-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset — Metoda</span><span class="sxs-lookup"><span data-stu-id="93ea6-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>

<span data-ttu-id="93ea6-103">Ustawia przesunięcie IL dla wygenerowanego przez kompilator procedury obsługi catch, która otacza metodę asynchroniczną.</span><span class="sxs-lookup"><span data-stu-id="93ea6-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="93ea6-104">Przesunięcie IL wygenerowanego catch jest używane przez debuger do obsługi catch tak, jakby była kodem nieużytkownika, nawet jeśli może wystąpić w metodzie kodu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="93ea6-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="93ea6-105">W szczególności jest używany w odpowiedzi na zdarzenie wyjątku **CatchHandlerFound** .</span><span class="sxs-lookup"><span data-stu-id="93ea6-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93ea6-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="93ea6-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93ea6-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="93ea6-107">Parameters</span></span>  
  
|<span data-ttu-id="93ea6-108">Parametr</span><span class="sxs-lookup"><span data-stu-id="93ea6-108">Parameter</span></span>|<span data-ttu-id="93ea6-109">Opis</span><span class="sxs-lookup"><span data-stu-id="93ea6-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="93ea6-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="93ea6-110">Return Value</span></span>  

 <span data-ttu-id="93ea6-111">Zwraca wartość `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="93ea6-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93ea6-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="93ea6-112">Requirements</span></span>  

 <span data-ttu-id="93ea6-113">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="93ea6-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93ea6-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="93ea6-114">See also</span></span>

- [<span data-ttu-id="93ea6-115">ISymUnmanagedAsyncMethodPropertiesWriter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="93ea6-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
