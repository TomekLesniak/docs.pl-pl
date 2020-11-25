---
title: IMetaDataImport::GetCustomAttributeByName — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
ms.openlocfilehash: 3eb894aaf8ccdc99ea23ddf946f39f3ec71773d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711211"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a>IMetaDataImport::GetCustomAttributeByName — Metoda

Pobiera atrybut niestandardowy, uwzględniając jego nazwę i właściciela.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `tkObj`  
 podczas Token metadanych reprezentujący obiekt będący właścicielem atrybutu niestandardowego.  
  
 `szName`  
 podczas Nazwa atrybutu niestandardowego.  
  
 `ppData`  
 określoną Wskaźnik do tablicy danych, która jest wartością atrybutu niestandardowego.  
  
 `pcbData`  
 określoną Rozmiar w bajtach danych zwróconych w * `ppData` .  
  
## <a name="remarks"></a>Uwagi  

 Istnieje możliwość zdefiniowania wielu atrybutów niestandardowych dla tego samego właściciela; mogą nawet mieć taką samą nazwę. Jednakże `GetCustomAttributeByName` zwraca tylko jedno wystąpienie. ( `GetCustomAttributeByName` zwraca pierwsze wystąpienie, które napotka.) Aby znaleźć wszystkie wystąpienia atrybutu niestandardowego, wywołaj metodę [IMetaDataImport:: EnumCustomAttributes —](imetadataimport-enumcustomattributes-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataImport — Interfejs](imetadataimport-interface.md)
- [IMetaDataImport2 — Interfejs](imetadataimport2-interface.md)
