---
title: INotifyConnection2::UnregisterNotifySource — Metoda
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
ms.openlocfilehash: 90220c2bfea683ff0472473e180c9e11ea568672
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720038"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="a4fd7-102">INotifyConnection2::UnregisterNotifySource — Metoda</span><span class="sxs-lookup"><span data-stu-id="a4fd7-102">INotifyConnection2::UnregisterNotifySource Method</span></span>

<span data-ttu-id="a4fd7-103">Usuwa określony obiekt źródłowy powiadomienia z połączenia.</span><span class="sxs-lookup"><span data-stu-id="a4fd7-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4fd7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a4fd7-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4fd7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a4fd7-105">Parameters</span></span>  

 `in_pNotifySource`  
 <span data-ttu-id="a4fd7-106">podczas Obiekt powiadomienia do wyrejestrowania.</span><span class="sxs-lookup"><span data-stu-id="a4fd7-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4fd7-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="a4fd7-107">Return Value</span></span>  

 <span data-ttu-id="a4fd7-108">S_OK, jeśli metoda zakończy się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="a4fd7-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4fd7-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a4fd7-109">Requirements</span></span>  

 <span data-ttu-id="a4fd7-110">**Nagłówek:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="a4fd7-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4fd7-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a4fd7-111">See also</span></span>

- [<span data-ttu-id="a4fd7-112">INotifyConnection2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a4fd7-112">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="a4fd7-113">INotifySource2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a4fd7-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="a4fd7-114">INotifySink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a4fd7-114">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="a4fd7-115">RegisterNotifySource, metoda</span><span class="sxs-lookup"><span data-stu-id="a4fd7-115">RegisterNotifySource Method</span></span>](inotifyconnection2-registernotifysource-method.md)
