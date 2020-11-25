---
title: IMetaDataTables::GetCodedTokenInfo — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
ms.openlocfilehash: b79ac7f71ec0551336298a90829e1f37e2e30b20
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711089"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a>IMetaDataTables::GetCodedTokenInfo — Metoda

Pobiera wskaźnik do tablicy tokenów skojarzonych z określonym indeksem wiersza.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ixCdTkn`  
 podczas Rodzaj zakodowanego tokenu do zwrócenia.  
  
 `pcTokens`  
 określoną Wskaźnik do długości `ppTokens` .  
  
 `ppTokens`  
 określoną Wskaźnik do wskaźnika do tablicy zawierającej listę zwracanych tokenów.  
  
 `ppName`  
 określoną Wskaźnik do wskaźnika do nazwy tokenu w `ixCdTkn` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataTables — Interfejs](imetadatatables-interface.md)
- [IMetaDataTables2 — Interfejs](imetadatatables2-interface.md)
