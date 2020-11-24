---
title: ICoreClrDebugTarget::EnumRuntimes — Metoda
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumRuntimes
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type:
- apiref
ms.openlocfilehash: 093f49508e8e96a4003f1aab8eed59e2fd196ba9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679276"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a>ICoreClrDebugTarget::EnumRuntimes — Metoda

Wylicza środowisko uruchomieniowe języka wspólnego (CLRs) w określonym procesie, który jest uruchomiony na komputerze zdalnym.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
## <a name="parameters"></a>Parametry  

 `dwInternalProcessID`  
 podczas Wewnętrzny identyfikator procesu, dla którego mają zostać wyliczone środowiska uruchomieniowe. Będzie to `m_dwInternalID` z odpowiednich [CoreClrDebugProcInfo —](coreclrdebugprocinfo-structure.md).  
  
 `pcRuntimes`  
 określoną Liczba zwróconych w czasie wykonywania `ppRuntimes` . Ta wartość może być równa 0 (zero).  
  
 `ppRuntimes`  
 określoną Tablica struktur [CoreClrDebugRuntimeInfo](coreclrdebugruntimeinfo-structure.md) , które reprezentują środowiska uruchomieniowe ładowane w zdalnym procesie docelowym.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK  
 Powodzenie.  
  
 S_FALSE  
 `dwInternalProcessID` nie pasuje do żadnego procesu uruchomionego na komputerze, prawdopodobnie dlatego, że proces został zakończony. `pcRuntimes` i `ppRuntimes` będą mieć wartość null.  
  
 E_OUTOFMEMORY  
 Nie można przydzielić wystarczającej ilości pamięci dla `ppRuntimes` .  
  
 E_FAIL (lub inne kody powrotne E_)  
 Inne błędy.  
  
## <a name="remarks"></a>Uwagi  

 Aby zwolnić pamięć, która została przypisana przez tę metodę, wywołaj metodę [ICoreClrDebugTarget:: freememory —](icoreclrdebugtarget-freememory-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Biblioteka:** mscordbi_macx86.dll  
  
 **.NET Framework wersje:** 3,5 SP1  
  
## <a name="see-also"></a>Zobacz także

- [ICoreClrDebugTarget — Interfejs](icoreclrdebugtarget-interface.md)
