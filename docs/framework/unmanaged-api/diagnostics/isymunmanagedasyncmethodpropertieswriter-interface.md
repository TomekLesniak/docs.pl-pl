---
title: ISymUnmanagedAsyncMethodPropertiesWriter — Interfejs
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
ms.openlocfilehash: 779b737da43f61d1023a0a640dce936e11c4704c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707038"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="b9636-102">ISymUnmanagedAsyncMethodPropertiesWriter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b9636-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>

<span data-ttu-id="b9636-103">Umożliwia zdefiniowanie opcjonalnych informacji o metodzie asynchronicznej dla każdego symbolu metody.</span><span class="sxs-lookup"><span data-stu-id="b9636-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="b9636-104">Zawsze używaj z otwartą metodą; oznacza to, między wywołaniami [metody OpenMethod —](isymunmanagedwriter-openmethod-method.md) i [CloseMethod —](isymunmanagedwriter-closemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="b9636-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9636-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="b9636-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="b9636-106">Metody</span><span class="sxs-lookup"><span data-stu-id="b9636-106">Methods</span></span>  

 <span data-ttu-id="b9636-107">Ten interfejs zawiera następujące metody:</span><span class="sxs-lookup"><span data-stu-id="b9636-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="b9636-108">Metoda</span><span class="sxs-lookup"><span data-stu-id="b9636-108">Method</span></span>|<span data-ttu-id="b9636-109">Opis</span><span class="sxs-lookup"><span data-stu-id="b9636-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b9636-110">DefineAsyncStepInfo, metoda</span><span class="sxs-lookup"><span data-stu-id="b9636-110">DefineAsyncStepInfo Method</span></span>](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="b9636-111">Zdefiniuj grupę asynchronicznych operacji await w bieżącej metodzie.</span><span class="sxs-lookup"><span data-stu-id="b9636-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="b9636-112">Każde przesunięcie Yield pasuje do instrukcji return oczekującej, identyfikując potencjalną rentowność.</span><span class="sxs-lookup"><span data-stu-id="b9636-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="b9636-113">Każda `breakpointMethod` / `breakpointOffset` para identyfikuje lokalizację operacji asynchronicznej, która może być w innej metodzie.</span><span class="sxs-lookup"><span data-stu-id="b9636-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="b9636-114">DefineCatchHandlerILOffset, metoda</span><span class="sxs-lookup"><span data-stu-id="b9636-114">DefineCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="b9636-115">Ustawia przesunięcie IL dla wygenerowanego przez kompilator procedury obsługi catch, która otacza metodę asynchroniczną.</span><span class="sxs-lookup"><span data-stu-id="b9636-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="b9636-116">Przesunięcie IL wygenerowanego catch jest używane przez debuger do obsługi catch tak, jakby był kodem innym niż użytkownik, nawet jeśli może wystąpić w metodzie kodu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b9636-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="b9636-117">W szczególności jest używany w odpowiedzi na zdarzenie wyjątku **CatchHandlerFound** .</span><span class="sxs-lookup"><span data-stu-id="b9636-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="b9636-118">DefineKickoffMethod, metoda</span><span class="sxs-lookup"><span data-stu-id="b9636-118">DefineKickoffMethod Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="b9636-119">Ustawia metodę początkową inicjującą operację asynchroniczną.</span><span class="sxs-lookup"><span data-stu-id="b9636-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b9636-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b9636-120">Requirements</span></span>  

 <span data-ttu-id="b9636-121">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b9636-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9636-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b9636-122">See also</span></span>

- [<span data-ttu-id="b9636-123">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="b9636-123">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
