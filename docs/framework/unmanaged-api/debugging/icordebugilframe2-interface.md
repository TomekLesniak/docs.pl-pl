---
title: ICorDebugILFrame2, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
ms.openlocfilehash: 3ada9e19bb1a92b3bd7e41340b99bf81b651dd37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725017"
---
# <a name="icordebugilframe2-interface"></a>ICorDebugILFrame2, interfejs

Logiczne rozszerzenie interfejsu ICorDebugILFrame.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[EnumerateTypeParameters, metoda](icordebugilframe2-enumeratetypeparameters-method.md)|Pobiera obiekt ICorDebugTypeEnum, który zawiera <xref:System.Type> Parametry w tej ramce.|  
|[RemapFunction, metoda](icordebugilframe2-remapfunction-method.md)|Ponownie mapuje edytowaną funkcję przez określenie nowego przesunięcia MSIL.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
