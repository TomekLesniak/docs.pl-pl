---
title: CreateInstallReferenceEnum — Funkcja
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
ms.openlocfilehash: 0f62b05ebbd8b27dba160c8281c1d40748c90fc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688838"
---
# <a name="createinstallreferenceenum-function"></a>CreateInstallReferenceEnum — Funkcja

Pobiera wskaźnik do wystąpienia [IInstallReferenceEnum](iinstallreferenceenum-interface.md) , które reprezentuje listę odwołań aplikacji do określonego zestawu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a>Parametry  

 `ppRefEnum`  
 określoną Zwrócony `IInstallReferenceEnum` wskaźnik.  
  
 `pName`  
 podczas [IAssemblyName](iassemblyname-interface.md) , który identyfikuje zestaw, dla którego mają zostać wyliczone odwołania.  
  
 `dwFlags`  
 podczas Flagi wpływające na zachowanie modułu wyliczającego.  
  
 `pvReserved`  
 podczas Zarezerwowane do użytku w przyszłości. `pvReserved` musi być odwołaniem o wartości null.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion. h  
  
 **Biblioteka:** Fusion.dll i Mscorwks.dll. Użyj Fusion.dll zamiast Mscorwks.dll, aby upewnić się, że docelowa jest poprawna wersja .NET Framework.  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IInstallReferenceEnum — Interfejs](iinstallreferenceenum-interface.md)
- [IAssemblyName — Interfejs](iassemblyname-interface.md)
- [Łączenie statycznych funkcji globalnych](fusion-global-static-functions.md)
