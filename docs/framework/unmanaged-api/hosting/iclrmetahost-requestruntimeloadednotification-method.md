---
title: ICLRMetaHost::RequestRuntimeLoadedNotification — Metoda
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
ms.openlocfilehash: ac40e203cf7d32c1fe30c9915bac3171139403e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723288"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a>ICLRMetaHost::RequestRuntimeLoadedNotification — Metoda

Zapewnia funkcję wywołania zwrotnego, która jest gwarantowana, gdy wersja środowiska uruchomieniowego języka wspólnego (CLR) jest najpierw ładowana, ale jeszcze nie została uruchomiona. Ta metoda zastępuje funkcję [LockClrVersion —](lockclrversion-function.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a>Parametry  

 `pCallbackFunction`  
 podczas Funkcja wywołania zwrotnego, która jest wywoływana po załadowaniu nowego środowiska uruchomieniowego.  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Metoda została ukończona pomyślnie.|  
|E_POINTER|`pCallbackFunction` ma wartość null.|  
  
## <a name="remarks"></a>Uwagi  

 Wywołanie zwrotne działa w następujący sposób:  
  
- Wywołanie zwrotne jest wywoływane tylko wtedy, gdy środowisko uruchomieniowe jest ładowane po raz pierwszy.  
  
- Wywołanie zwrotne nie jest wywoływane dla obciążeń współużytkowanych tego samego środowiska uruchomieniowego.  
  
- W przypadku obciążeń środowiska uruchomieniowego, które nie są współużytkowane, wywołania funkcji wywołania zwrotnego są serializowane.  
  
 Funkcja wywołania zwrotnego ma następujący prototyp:  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 Prototypy funkcji wywołania zwrotnego są następujące:  
  
- `pfnCallbackThreadSet`:  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- `pfnCallbackThreadUnset`:  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 Jeśli host zamierza załadować lub spowodować załadowanie innego środowiska uruchomieniowego w sposób współużytkowany, `pfnCallbackThreadSet` Parametry i, `pfnCallbackThreadUnset` które są dostępne w funkcji wywołania zwrotnego, muszą być używane w następujący sposób:  
  
- `pfnCallbackThreadSet` musi być wywoływana przez wątek, który może spowodować obciążenie w czasie wykonywania przed próbą takiego obciążenia.  
  
- `pfnCallbackThreadUnset` musi być wywoływana, gdy wątek nie będzie już powodował obciążenia w czasie wykonywania (i przed powrotem z początkowego wywołania zwrotnego).  
  
- `pfnCallbackThreadSet` i `pfnCallbackThreadUnset` nie są współużytkowane.  
  
> [!NOTE]
> Aplikacje hosta nie mogą wywoływać i znajdować `pfnCallbackThreadSet` `pfnCallbackThreadUnset` się poza zakresem `pCallbackFunction` parametru.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Obiekt ServiceHost. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRMetaHost — Interfejs](iclrmetahost-interface.md)
- [Hosting](index.md)
