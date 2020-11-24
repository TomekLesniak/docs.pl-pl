---
title: IHostMemoryManager::CreateMAlloc — Metoda
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
ms.openlocfilehash: 79580170d544cd3763992a4bc67fd20e3446bb1d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685724"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a>IHostMemoryManager::CreateMAlloc — Metoda

Pobiera wskaźnik interfejsu do wystąpienia [IHostMAlloc](ihostmalloc-interface.md) , które jest używane do tworzenia żądań alokacji ze sterty utworzonej przez hosta.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `dwMallocType`  
 podczas Kombinacja [MALLOC_TYPE](malloc-type-enumeration.md) flag, która określa charakterystykę przydzielenia pamięci.  
  
 `ppMAlloc`  
 określoną Wskaźnik do adresu `IHostMAlloc` wystąpienia dostarczonego przez hosta.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|`CreateMAlloc` pomyślnie zwrócono.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Za mało dostępnej pamięci fizycznej, aby ukończyć żądanie alokacji.|  
  
## <a name="remarks"></a>Uwagi  

 `CreateMAlloc` zwraca obiekt, który umożliwia CLR wykonywanie żądań alokacji za pośrednictwem hosta zamiast korzystania ze standardowych funkcji Win32.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IHostMalloc — Interfejs](ihostmalloc-interface.md)
- [IHostMemoryManager — Interfejs](ihostmemorymanager-interface.md)
