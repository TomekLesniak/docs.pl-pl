---
title: IBindingDisplay::GetCurrentDisplay — Metoda
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
ms.openlocfilehash: db2474741012c4fd1734adafed112821c42c099c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541711"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a>IBindingDisplay::GetCurrentDisplay — Metoda
Zwraca bieżące informacje o wyświetlaniu powiązania.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `display`  
 [out, retval] Wskaźnik do elementu SAFEARRAY zawierającego informacje o wyświetlaniu powiązania.  
  
## <a name="remarks"></a>Uwagi  
 Metoda [IBindingDisplay:: InitializeForProcess —](ibindingdisplay-initializeforprocess-method.md) musi być wcześniej zakończona pomyślnie, a program musi być zatrzymany przez debuger.  
  
 Obiekt wywołujący musi cofnąć alokację zwróconej `SAFEARRAY` pamięci za pomocą [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** BindingDisplay. h  
  
 **Biblioteka:** BindingDisplay. idl  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IBindingDisplay — Interfejs](ibindingdisplay-interface.md)
- [InitializeForProcess, metoda](ibindingdisplay-initializeforprocess-method.md)
