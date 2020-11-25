---
title: IHostAssemblyStore::ProvideModule — Metoda
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
ms.openlocfilehash: 35805d277774e1de03bb7dee1740a2e1305a97c9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732999"
---
# <a name="ihostassemblystoreprovidemodule-method"></a>IHostAssemblyStore::ProvideModule — Metoda

Rozpoznaje moduł wewnątrz zestawu lub połączony (ale nie osadzony) plik zasobów.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pBindInfo`  
 podczas Wskaźnik do wystąpienia [ModuleBindInfo —](modulebindinfo-structure.md) , który opisuje żądany moduł <xref:System.AppDomain> , zestaw i nazwę modułu.  
  
 `pdwModuleId`  
 określoną Wskaźnik do unikatowego identyfikatora `IStream` zawierającego załadowany moduł.  
  
 `ppStmModuleImage`  
 określoną Wskaźnik do adresu `IStream` obiektu, który zawiera obraz przenośnego pliku wykonywalnego (PE), który ma zostać załadowany lub ma wartość null, jeśli nie można znaleźć modułu.  
  
 `ppStmPDB`  
 określoną Wskaźnik do adresu `IStream` obiektu, który zawiera informacje o debugowaniu programu (PDB) dla żądanego modułu, lub wartość null, jeśli nie można znaleźć pliku. pdb.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|`ProvideModule` pomyślnie zwrócono.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0x80070002)|Nie można zlokalizować żądanego zestawu lub połączonego zasobu.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId` nie jest wystarczająco duży, aby można było zawierać identyfikator, który chce zwrócić host.|  
  
## <a name="remarks"></a>Uwagi  

 Zwracana wartość tożsamości `pdwModuleId` jest określana przez hosta. Identyfikatory muszą być unikatowe w okresie istnienia procesu. Środowisko CLR używa tej wartości jako unikatowego identyfikatora skojarzonego strumienia. Sprawdza każdą wartość dla wartości `pAssemblyId` zwracanych przez wywołania do [ProvideAssembly —](ihostassemblystore-provideassembly-method.md) i wartości `pdwModuleId` zwracanych przez inne wywołania do `ProvideModule` . Jeśli host zwraca tę samą wartość identyfikatora dla innego `IStream` , środowisko CLR sprawdza, czy zawartość tego strumienia została już zamapowana. Jeśli tak, środowisko CLR ładuje istniejącą kopię obrazu zamiast mapowania nowej. W związku z tym, identyfikator nie może również nakładać się na identyfikatory zestawu zwrócone z `ProvideAssembly` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRAssemblyReferenceList — Interfejs](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager — Interfejs](ihostassemblymanager-interface.md)
- [IHostAssemblyStore — Interfejs](ihostassemblystore-interface.md)
