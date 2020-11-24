---
title: CorExitProcess — Funkcja
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
ms.openlocfilehash: f6d8114732a3b7c15d0a0258a28a362d661b030a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673633"
---
# <a name="corexitprocess-function"></a>CorExitProcess — Funkcja

Zamyka bieżący proces niezarządzany.  
  
 Ta funkcja jest przestarzała w .NET Framework 4. Zamiast tego użyj metody [ICLRMetaHost:: ExitProcess —](iclrmetahost-exitprocess-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `exitCode`  
 Liczba całkowita, która określa kod zakończenia procesu.  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Począwszy od .NET Framework 4, `CorExitProcess` zamyka wszystkie uruchomione środowisko uruchomieniowe w procesie, a nie tylko środowisko uruchomieniowe, do którego zostały powiązane starsze interfejsy API.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Przestarzałe funkcje hostingu środowiska CLR](deprecated-clr-hosting-functions.md)
