---
title: IHostMAlloc::DebugAlloc — Metoda
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
ms.openlocfilehash: 49de0398dd32970bd8ceb0fd24178e75df5d14b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713499"
---
# <a name="ihostmallocdebugalloc-method"></a>IHostMAlloc::DebugAlloc — Metoda

Żąda, aby Host przydzielił określoną ilość pamięci ze sterty, a także śledzić miejsce przydzielenia pamięci.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `cbSize`  
 podczas Rozmiar (w bajtach) bieżącego żądania alokacji pamięci.  
  
 `dwCriticalLevel`  
 podczas Jedna z wartości [EMemoryCriticalLevel —](ememorycriticallevel-enumeration.md) , co wskazuje na wpływ błędu alokacji.  
  
 `pszFileName`  
 podczas Plik kodu debugowanego pliku wykonywalnego.  
  
 `iLineNo`  
 podczas Numer wiersza, w `pszFileName` którym zażądano alokacji.  
  
 `ppMem`  
 określoną Wskaźnik do przydzieloną pamięci lub wartość null, jeśli nie można ukończyć żądania.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|`DebugAlloc` pomyślnie zwrócono.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Za mało dostępnej pamięci, aby ukończyć żądanie alokacji.|  
  
## <a name="remarks"></a>Uwagi  

 Środowisko CLR Pobiera wskaźnik interfejsu do wystąpienia [IHostMAlloc](ihostmalloc-interface.md) przez wywołanie metody [IHostMemoryManager::](ihostmemorymanager-createmalloc-method.md) CreateInstance. `DebugAlloc` umożliwia środowisko uruchomieniowe pobieranie informacji o pliku kodu do użycia podczas debugowania.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IHostMemoryManager — Interfejs](ihostmemorymanager-interface.md)
- [IHostMalloc — Interfejs](ihostmalloc-interface.md)
