---
title: IDebugAutoAttach::AutoAttach — Metoda
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
ms.openlocfilehash: 64dd653bb0d4e383075a999e0803e4acfd0fae3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720103"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="d2a6f-102">IDebugAutoAttach::AutoAttach — Metoda</span><span class="sxs-lookup"><span data-stu-id="d2a6f-102">IDebugAutoAttach::AutoAttach Method</span></span>

<span data-ttu-id="d2a6f-103">Wykonuje automatyczne dołączanie debugera wywoływanego przez serwer.</span><span class="sxs-lookup"><span data-stu-id="d2a6f-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2a6f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d2a6f-104">Syntax</span></span>  
  
```cpp  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2a6f-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d2a6f-105">Parameters</span></span>  

 `guidPort`  
 <span data-ttu-id="d2a6f-106">podczas Zawsze ustawiaj na `GUID_NULL` .</span><span class="sxs-lookup"><span data-stu-id="d2a6f-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="d2a6f-107">podczas Identyfikator procesu, zwykle pobierany z `GetCurrentProcessId` funkcją.</span><span class="sxs-lookup"><span data-stu-id="d2a6f-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="d2a6f-108">podczas Typ programu: `AUTOATTACH_PROGRAM_WIN32` , `AUTOATTACH_PROGRAM_COMPLUS` , lub `AUTOATTACH_PROGRAM_UNKNOWN` .</span><span class="sxs-lookup"><span data-stu-id="d2a6f-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="d2a6f-109">podczas Identyfikator programu.</span><span class="sxs-lookup"><span data-stu-id="d2a6f-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="d2a6f-110">podczas Ciąg przesłany przez czasownik debugowania.</span><span class="sxs-lookup"><span data-stu-id="d2a6f-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2a6f-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="d2a6f-111">Return Value</span></span>  

 <span data-ttu-id="d2a6f-112">S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="d2a6f-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2a6f-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d2a6f-113">Requirements</span></span>  

 <span data-ttu-id="d2a6f-114">**Nagłówek:** DbgAutoAttach. h</span><span class="sxs-lookup"><span data-stu-id="d2a6f-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2a6f-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d2a6f-115">See also</span></span>

- [<span data-ttu-id="d2a6f-116">IDebugAutoAttach — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d2a6f-116">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)
