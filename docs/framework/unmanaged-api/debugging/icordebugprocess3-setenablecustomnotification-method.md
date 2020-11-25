---
title: ICorDebugProcess3::SetEnableCustomNotification — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
ms.openlocfilehash: 078e5cb03848564b42e30a079101d5a61e0074bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734026"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="b8e9d-102">ICorDebugProcess3::SetEnableCustomNotification — Metoda</span><span class="sxs-lookup"><span data-stu-id="b8e9d-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>

<span data-ttu-id="b8e9d-103">Włącza i wyłącza niestandardowe powiadomienia debugera określonego typu.</span><span class="sxs-lookup"><span data-stu-id="b8e9d-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8e9d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b8e9d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8e9d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b8e9d-105">Parameters</span></span>  

 `pClass`  
 <span data-ttu-id="b8e9d-106">podczas Typ, który określa niestandardowe powiadomienia debugera.</span><span class="sxs-lookup"><span data-stu-id="b8e9d-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="b8e9d-107">[w] `true` Aby włączyć niestandardowe powiadomienia debugera; `false` Aby wyłączyć powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="b8e9d-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="b8e9d-108">Wartość domyślna to `false`.</span><span class="sxs-lookup"><span data-stu-id="b8e9d-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8e9d-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b8e9d-109">Remarks</span></span>  

 <span data-ttu-id="b8e9d-110">Gdy `fEnable` jest ustawiona na `true` , wywołania <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> metody wyzwalają wywołanie zwrotne [ICorDebugManagedCallback3:: CustomNotification —](icordebugmanagedcallback3-customnotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b8e9d-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="b8e9d-111">Powiadomienia są domyślnie wyłączone; w związku z tym debuger musi określić wszelkie typy powiadomień, o których wie i który chce obsłużyć.</span><span class="sxs-lookup"><span data-stu-id="b8e9d-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="b8e9d-112">Ponieważ Klasa [ICorDebugClass](icordebug-interface.md) jest objęta zakresem przez domenę aplikacji, debuger musi wywołać `SetEnableCustomNotification` dla każdej domeny aplikacji w procesie, jeśli chce otrzymywać powiadomienie przez cały proces.</span><span class="sxs-lookup"><span data-stu-id="b8e9d-112">Because the [ICorDebugClass](icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="b8e9d-113">Począwszy od .NET Framework 4, jedyne obsługiwane powiadomienie to powiadomienie obejmujące zależność między wątkami.</span><span class="sxs-lookup"><span data-stu-id="b8e9d-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8e9d-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b8e9d-114">Requirements</span></span>  

 <span data-ttu-id="b8e9d-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8e9d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8e9d-116">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="b8e9d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8e9d-117">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b8e9d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8e9d-118">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8e9d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8e9d-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b8e9d-119">See also</span></span>

- [<span data-ttu-id="b8e9d-120">ICorDebugProcess3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b8e9d-120">ICorDebugProcess3 Interface</span></span>](icordebugprocess3-interface.md)
- [<span data-ttu-id="b8e9d-121">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="b8e9d-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b8e9d-122">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="b8e9d-122">Debugging</span></span>](index.md)
