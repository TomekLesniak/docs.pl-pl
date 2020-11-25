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
# <a name="lpoverlapped_completion_routine-function-pointer"></a>LPOVERLAPPED_COMPLETION_ROUTINE — Wskaźnik funkcji

Wskazuje funkcję, która powiadamia hosta, gdy nakładają się (czyli asynchroniczne) operacje wejścia/wyjścia do urządzenia.  
  
 Ten wskaźnik funkcji został uznany za przestarzały w .NET Framework 4.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `dwErrorCode`  
 podczas Wartość, która jest kodem błędu, jeśli urządzenie zostało zamknięte; w przeciwnym razie ta wartość jest równa zero.  
  
 Zamknięcie urządzenia powoduje natychmiastowe zakończenie wszystkich oczekujących operacji we/wy na urządzeniu.  
  
 `dwNumberOfBytesTransfered`  
 podczas Liczba bajtów przesłanych przez operację we/wy.  
  
 `lpOverlapped`  
 podczas Wskaźnik do struktury zawierającej informacje, które mają zostać użyte do ukończenia żądania we/wy.  
  
## <a name="remarks"></a>Uwagi  

 Funkcja, do której `LPOVERLAPPED_COMPLETION_ROUTINE` punkty jest funkcją wywołania zwrotnego i musi być implementowana przez moduł zapisujący aplikacji hostingowej. Funkcja wywołania zwrotnego umożliwia hostowi przetwarzanie ukończonego żądania we/wy.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorWks.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Przestarzałe funkcje hostingu środowiska CLR](deprecated-clr-hosting-functions.md)
