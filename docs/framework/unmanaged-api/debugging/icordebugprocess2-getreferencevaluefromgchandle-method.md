---
title: ICorDebugProcess2::GetReferenceValueFromGCHandle — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
ms.openlocfilehash: a5b9d57aab834ba3ca72a2ea8576ec70cd88eb77
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713577"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="0e7b1-102">ICorDebugProcess2::GetReferenceValueFromGCHandle — Metoda</span><span class="sxs-lookup"><span data-stu-id="0e7b1-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>

<span data-ttu-id="0e7b1-103">Pobiera wskaźnik odwołania do określonego obiektu zarządzanego, który ma dojście do wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="0e7b1-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e7b1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0e7b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e7b1-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="0e7b1-105">Parameters</span></span>  

 `handle`  
 <span data-ttu-id="0e7b1-106">podczas Wskaźnik do zarządzanego obiektu, który ma dojście do wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="0e7b1-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="0e7b1-107">Ta wartość jest <xref:System.IntPtr> obiektem i można ją pobrać z <xref:System.Runtime.InteropServices.GCHandle> elementu dla obiektu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="0e7b1-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="0e7b1-108">określoną Wskaźnik do adresu obiektu ICorDebugReferenceValue, który reprezentuje odwołanie do określonego obiektu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="0e7b1-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e7b1-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0e7b1-109">Remarks</span></span>  

 <span data-ttu-id="0e7b1-110">Nie należy mylić zwróconej wartości odniesienia z wartością referencyjną wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="0e7b1-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="0e7b1-111">Zwrócone odwołanie zachowuje się jak normalne odwołanie.</span><span class="sxs-lookup"><span data-stu-id="0e7b1-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="0e7b1-112">Jest ono wyłączone, gdy wykonanie kodu jest kontynuowane po punkcie przerwania.</span><span class="sxs-lookup"><span data-stu-id="0e7b1-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="0e7b1-113">Okres istnienia obiektu docelowego nie ma wpływ na czas istnienia wartości referencyjnej.</span><span class="sxs-lookup"><span data-stu-id="0e7b1-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e7b1-114">`GetReferenceValueFromGCHandle`Metoda nie sprawdza poprawności dojścia.</span><span class="sxs-lookup"><span data-stu-id="0e7b1-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="0e7b1-115">W związku z tym, `GetReferenceValueFromGCHandle` Metoda może potencjalnie uszkodzić debuger i kod debugowany w przypadku przekazanie nieprawidłowego dojścia.</span><span class="sxs-lookup"><span data-stu-id="0e7b1-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e7b1-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0e7b1-116">Requirements</span></span>  

 <span data-ttu-id="0e7b1-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e7b1-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e7b1-118">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="0e7b1-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e7b1-119">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0e7b1-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e7b1-120">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e7b1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
