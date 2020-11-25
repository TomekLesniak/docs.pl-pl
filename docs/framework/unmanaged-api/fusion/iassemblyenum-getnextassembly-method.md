---
title: IAssemblyEnum::GetNextAssembly — Metoda
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
ms.openlocfilehash: af43d9cf4d5aa790036a13d060fc6ccf113f335d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719895"
---
# <a name="iassemblyenumgetnextassembly-method"></a>IAssemblyEnum::GetNextAssembly — Metoda

Pobiera wskaźnik do następnego [IAssemblyName](iassemblyname-interface.md) zawartego w tym obiekcie [IAssemblyEnum](iassemblyenum-interface.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pvReserved`  
 podczas Zarezerwowane do użytku w przyszłości. `pvReserved` musi być odwołaniem o wartości null.  
  
 `ppName`  
 określoną Zwrócony `IAssemblyName` wskaźnik.  
  
 `dwFlags`  
 podczas Zarezerwowane do użytku w przyszłości. `dwFlags` musi mieć wartość 0 (zero).  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IAssemblyName — Interfejs](iassemblyname-interface.md)
- [IAssemblyEnum — Interfejs](iassemblyenum-interface.md)
