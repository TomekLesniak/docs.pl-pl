---
title: CreateICeeFileGen — Funkcja
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: 454cfa2dd1b676f32649050625b1074fbd776d54
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673335"
---
# <a name="createiceefilegen-function"></a>CreateICeeFileGen — Funkcja

Tworzy obiekt [ICeeFileGen](iceefilegen-class.md) .  
  
 Ta funkcja jest przestarzała w .NET Framework 4.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ceeFileGen`  
 określoną Wskaźnik do adresu nowego `ICeeFileGen` obiektu.  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca standardowe kody błędów COM.  
  
## <a name="remarks"></a>Uwagi  

 `ICeeFileGen`Obiekt jest używany do tworzenia przenośnych plików wykonywalnych (PE) środowiska uruchomieniowego języka wspólnego (CLR).  
  
 Wywołaj funkcję [DestroyICeeFileGen —](destroyiceefilegen-function.md) , aby zniszczyć `ICeeFileGen` obiekt po zakończeniu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** ICeeFileGen. h  
  
 **Biblioteka:** MSCorPE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Przestarzałe funkcje hostingu środowiska CLR](deprecated-clr-hosting-functions.md)
