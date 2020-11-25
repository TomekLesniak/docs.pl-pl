---
title: IMetaDataImport2::GetGenericParamProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
ms.openlocfilehash: 16f69d571ffed87a2e848124ce16ac942d319c37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702697"
---
# <a name="imetadataimport2getgenericparamprops-method"></a>IMetaDataImport2::GetGenericParamProps — Metoda

Pobiera metadane skojarzone z parametrem ogólnym reprezentowanym przez określony token.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `gp`  
 podczas Token reprezentujący parametr generyczny, dla którego mają być zwracane metadane.  
  
 `pulParamSeq`  
 określoną Pozycja porządkowa `Type` parametru w konstruktorze nadrzędnym lub metodzie.  
  
 `pdwParamFlags`  
 określoną Wartość wyliczenia [CorGenericParamAttr —](corgenericparamattr-enumeration.md) , która opisuje `Type` parametr dla parametru generycznego.  
  
 `ptOwner`  
 określoną Token TypeDef lub MethodDef, który reprezentuje właściciela parametru.  
  
 `reserved`  
 określoną Zarezerwowane do użytku w przyszłości.  
  
 `wzName`  
 określoną Nazwa parametru generycznego.  
  
 `cchName`  
 podczas Rozmiar `wzName` buforu.  
  
 `pchName`  
 określoną Zwrócony rozmiar nazwy w znaki dwubajtowe.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataImport2 — Interfejs](imetadataimport2-interface.md)
- [IMetaDataImport — Interfejs](imetadataimport-interface.md)
