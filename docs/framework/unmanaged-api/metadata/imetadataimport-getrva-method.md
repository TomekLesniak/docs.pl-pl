---
title: IMetaDataImport::GetRVA — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
ms.openlocfilehash: b4e7209c357f21a3f0de5770b483b673d5a5570b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729216"
---
# <a name="imetadataimportgetrva-method"></a>IMetaDataImport::GetRVA — Metoda

Pobiera względny adres wirtualny (RVA) oraz flagi implementacji metody lub pola reprezentowanego przez określony token.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `tk`  
 podczas Token metadanych MethodDef lub FieldDef reprezentujący obiekt kodu do zwrócenia adresu RVA. Jeśli token jest FieldDef, pole musi być zmienną globalną.  
  
 `pulCodeRVA`  
 określoną Wskaźnik do względnego adresu wirtualnego obiektu kodu reprezentowanego przez token.  
  
 `pdwImplFlags`  
 określoną Wskaźnik do flag implementacji dla metody. Ta wartość jest maska bitowa z wyliczenia [CorMethodImpl —](cormethodimpl-enumeration.md) . Wartość `pdwImplFlags` jest prawidłowa tylko wtedy, gdy `tk` jest tokenem MethodDef.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataImport — Interfejs](imetadataimport-interface.md)
- [IMetaDataImport2 — Interfejs](imetadataimport2-interface.md)
