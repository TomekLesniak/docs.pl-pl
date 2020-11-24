---
title: ICorPublishProcess::IsManaged — Metoda
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: dfe247bda75c3695c7c09b85729b4e057c13c62d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692634"
---
# <a name="icorpublishprocessismanaged-method"></a>ICorPublishProcess::IsManaged — Metoda

Pobiera wartość wskazującą, czy proces, do którego odwołuje się ten [ICorPublishProcess](icorpublishprocess-interface.md) , ma znany kod zarządzany.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pbManaged`  
 określoną Wskaźnik do wartości logicznej wskazującej, czy proces ma kod zarządzany. Wartość jest w `true` przypadku, gdy proces ma kod zarządzany; w przeciwnym razie `false` .  
  
## <a name="remarks"></a>Uwagi  

 Ponieważ bieżąca wersja programu `ICorPublishProcess` zezwala na dostęp tylko do procesów, które mają kod zarządzany, `IsManaged` zawsze zwraca `true` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorPub. idl, CorPub. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorPublishProcess — Interfejs](icorpublishprocess-interface.md)
