---
title: ICorPublishProcess::GetDisplayName — Metoda
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
ms.openlocfilehash: 5a037695892252042d7827165595f7bad0feba56
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693167"
---
# <a name="icorpublishprocessgetdisplayname-method"></a>ICorPublishProcess::GetDisplayName — Metoda

Pobiera pełną ścieżkę pliku wykonywalnego dla procesu, do którego odwołuje się ten [ICorPublishProcess](icorpublishprocess-interface.md).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `cchName`  
 podczas Rozmiar `szName` tablicy.  
  
 `pcchName`  
 określoną Liczba znaków dwubajtowych zwracanych w `szName` tablicy.  
  
 `szName`  
 określoną Tablica do przechowywania nazwy, łącznie z pełną ścieżką pliku wykonywalnego. Nazwa jest zakończona wartością null.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorPub. idl, CorPub. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorPublishProcess — Interfejs](icorpublishprocess-interface.md)
