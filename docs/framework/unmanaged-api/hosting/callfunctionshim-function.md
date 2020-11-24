---
title: CallFunctionShim — Funkcja
ms.date: 03/30/2017
api_name:
- CallFunctionShim
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CallFunctionShim
helpviewer_keywords:
- CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type:
- apiref
ms.openlocfilehash: f72c987294d7768eacf112c622ab15494fb75e34
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685789"
---
# <a name="callfunctionshim-function"></a>CallFunctionShim — Funkcja

Wywołuje funkcję, która ma określoną nazwę i parametry w określonej bibliotece.  
  
 Ta funkcja jest przestarzała w .NET Framework 4.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `szDllName`  
 podczas Nazwa biblioteki zawierającej funkcję.  
  
 `szFunctionName`  
 podczas Nazwa funkcji.  
  
 `lpvArgument1`  
 podczas Pierwszy argument do przekazania do funkcji.  
  
 `lpvArgument2`  
 podczas Drugi argument do przekazania do funkcji.  
  
 `szVersion`  
 podczas Wersja biblioteki, która zawiera funkcję.  
  
 `pvReserved`  
 podczas Zarezerwowane do użytku w przyszłości. Przekaż zero w tym parametrze.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Przestarzałe funkcje hostingu środowiska CLR](deprecated-clr-hosting-functions.md)
