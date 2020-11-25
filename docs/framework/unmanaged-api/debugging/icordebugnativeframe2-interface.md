---
title: ICorDebugNativeFrame2 — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2
helpviewer_keywords:
- ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type:
- apiref
ms.openlocfilehash: ddf5af0bc0a5e5e21d837d8b2f3f76185ed7e2b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724718"
---
# <a name="icordebugnativeframe2-interface"></a>ICorDebugNativeFrame2 — Interfejs

Dostarcza metody testowania relacji podrzędnych i nadrzędnych ramek.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[IsChild, metoda](icordebugnativeframe2-ischild-method.md)|Określa, czy bieżąca ramka jest ramką podrzędną.|  
|[IsMatchingParentFrame, metoda](icordebugnativeframe2-ismatchingparentframe-method.md)|Określa, czy określona ramka jest elementem nadrzędnym bieżącej ramki.|  
|[GetStackParameterSize, metoda](icordebugnativeframe2-getstackparametersize-method.md)|Zwraca skumulowany rozmiar parametrów na stosie w systemach operacyjnych x86.|  
  
## <a name="remarks"></a>Uwagi  

 Ten interfejs logicznie rozszerza interfejs "ICorDebugNativeFrame".  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
