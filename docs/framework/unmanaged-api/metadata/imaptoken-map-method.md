---
title: IMapToken::Map — Metoda
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
ms.openlocfilehash: 51cca1ab61027090b0d22781dfd740038bc9372d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718205"
---
# <a name="imaptokenmap-method"></a>IMapToken::Map — Metoda

Mapuje relacje między zestawami przy użyciu podpisów metadanych.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `tkImp`  
 podczas Token metadanych reprezentujący zaimportowany obiekt kodu.  
  
 `tkEmit`  
 podczas Token metadanych reprezentujący emitowany obiekt kodu.  
  
## <a name="remarks"></a>Uwagi  

 Gdy ponowne mapowanie tokenu odbywa się podczas scalania, oryginalny token jest objęty zakresem zaimportowanego (źródłowego) zakresu metadanych, a nowy token jest objęty zakresem metadanych emitowanych (docelowych).  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMapToken — Interfejs](imaptoken-interface.md)
