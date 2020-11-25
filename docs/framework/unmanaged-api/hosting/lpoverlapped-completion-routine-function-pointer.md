---
title: LPOVERLAPPED_COMPLETION_ROUTINE — Wskaźnik funkcji
ms.date: 03/30/2017
api_name:
- LPOVERLAPPED_COMPLETION_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type:
- apiref
ms.openlocfilehash: a3a45a13073cf422064d28554a274e068db6f517
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727513"
---
# <a name="lpoverlapped_completion_routine-function-pointer"></a><span data-ttu-id="bf3bf-102">LPOVERLAPPED_COMPLETION_ROUTINE — Wskaźnik funkcji</span><span class="sxs-lookup"><span data-stu-id="bf3bf-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>

<span data-ttu-id="bf3bf-103">Wskazuje funkcję, która powiadamia hosta, gdy nakładają się (czyli asynchroniczne) operacje wejścia/wyjścia do urządzenia.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="bf3bf-104">Ten wskaźnik funkcji został uznany za przestarzały w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf3bf-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="bf3bf-105">Syntax</span></span>  
  
```cpp  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf3bf-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="bf3bf-106">Parameters</span></span>  

 `dwErrorCode`  
 <span data-ttu-id="bf3bf-107">podczas Wartość, która jest kodem błędu, jeśli urządzenie zostało zamknięte; w przeciwnym razie ta wartość jest równa zero.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="bf3bf-108">Zamknięcie urządzenia powoduje natychmiastowe zakończenie wszystkich oczekujących operacji we/wy na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="bf3bf-109">podczas Liczba bajtów przesłanych przez operację we/wy.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="bf3bf-110">podczas Wskaźnik do struktury zawierającej informacje, które mają zostać użyte do ukończenia żądania we/wy.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf3bf-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bf3bf-111">Remarks</span></span>  

 <span data-ttu-id="bf3bf-112">Funkcja, do której `LPOVERLAPPED_COMPLETION_ROUTINE` punkty jest funkcją wywołania zwrotnego i musi być implementowana przez moduł zapisujący aplikacji hostingowej.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="bf3bf-113">Funkcja wywołania zwrotnego umożliwia hostowi przetwarzanie ukończonego żądania we/wy.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf3bf-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="bf3bf-114">Requirements</span></span>  

 <span data-ttu-id="bf3bf-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf3bf-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf3bf-116">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bf3bf-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bf3bf-117">**Biblioteka:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="bf3bf-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="bf3bf-118">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf3bf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf3bf-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="bf3bf-119">See also</span></span>

- [<span data-ttu-id="bf3bf-120">Przestarzałe funkcje hostingu środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="bf3bf-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
