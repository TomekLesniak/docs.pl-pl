---
title: ICorDebugILFrame, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
ms.openlocfilehash: 4f34fdf9a0eeb47e027cc874afee5bd04f5bd9bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712394"
---
# <a name="icordebugilframe-interface"></a>ICorDebugILFrame, interfejs

Przedstawia ramkę stosu kodu języka pośredniego firmy Microsoft (MSIL). Ten interfejs jest podklasą interfejsu ICorDebugFrame.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[CanSetIP, metoda](icordebugilframe-cansetip-method.md)|Pobiera wartość wskazującą, czy jest bezpieczna, aby ustawić wskaźnik instrukcji na określoną lokalizację przesunięcia.|  
|[EnumerateArguments, metoda](icordebugilframe-enumeratearguments-method.md)|Pobiera moduł wyliczający dla argumentów w tej ramce.|  
|[EnumerateLocalVariables, metoda](icordebugilframe-enumeratelocalvariables-method.md)|Pobiera moduł wyliczający dla zmiennych lokalnych w tej ramce.|  
|[GetArgument, metoda](icordebugilframe-getargument-method.md)|Pobiera wartość określonego argumentu w tej ramce stosu MSIL.|  
|[GetIP, metoda](icordebugilframe-getip-method.md)|Pobiera wartość wskaźnika instrukcji i wartość kombinacji bitowej opisującą sposób uzyskiwania wartości wskaźnika instrukcji.|  
|[GetLocalVariable, metoda](icordebugilframe-getlocalvariable-method.md)|Pobiera wartość określonej zmiennej lokalnej w tej ramce stosu MSIL.|  
|[GetStackDepth, metoda](icordebugilframe-getstackdepth-method.md)|Nie zaimplementowano.|  
|[GetStackValue, metoda](icordebugilframe-getstackvalue-method.md)|Nie zaimplementowano.|  
|[SetIP — Metoda](icordebugilframe-setip-method.md)|Ustawia wskaźnik instrukcji na określoną lokalizację przesunięcia w kodzie MSIL.|  
  
## <a name="remarks"></a>Uwagi  

 `ICorDebugILFrame`Interfejs jest wyspecjalizowanym interfejsem ICorDebugFrame. Jest używana w przypadku ramek kodu MSIL lub dla ramek skompilowanych w trybie just-in-Time (JIT). Ramki skompilowane JIT implementują `ICorDebugILFrame` interfejs i interfejs ICorDebugNativeFrame.  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
