---
title: IMetaDataImport::FindMethod — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
ms.openlocfilehash: 111e42a6d8f413c616779bc44e0722ab38781588
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711341"
---
# <a name="imetadataimportfindmethod-method"></a>IMetaDataImport::FindMethod — Metoda

Pobiera wskaźnik do tokenu MethodDef dla metody, która jest ujęta w określonym <xref:System.Type> i która ma określoną nazwę i sygnaturę metadanych.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `td`  
 podczas `mdTypeDef` Token dla typu (klasy lub interfejsu), który obejmuje element członkowski do wyszukania. Jeśli ta wartość jest `mdTokenNil` , wyszukiwanie jest wykonywane dla funkcji globalnej.  
  
 `szName`  
 podczas Nazwa metody do wyszukania.  
  
 `pvSigBlob`  
 podczas Wskaźnik do binarnego podpisu metadanych metody.  
  
 `cbSigBlob`  
 podczas Rozmiar w bajtach `pvSigBlob` .  
  
 `pmb`  
 określoną Wskaźnik do zgodnego tokenu MethodDef.  
  
## <a name="remarks"></a>Uwagi  

 Należy określić metodę przy użyciu jej klasy lub interfejsu ( `td` ), jej nazwy ( `szName` ) i opcjonalnie jej sygnatury ( `pvSigBlob` ). Może istnieć wiele metod o tej samej nazwie w klasie lub interfejsie. W takim przypadku Przekaż podpis metody, aby znaleźć unikatowe dopasowanie.  
  
 Sygnatura przekazano do `FindMethod` musi być wygenerowana w bieżącym zakresie, ponieważ sygnatury są powiązane z konkretnym zakresem. Podpis może osadzić token, który identyfikuje otaczającą klasę lub typ wartości. Token jest indeksem tabeli lokalnych TypeDef. Nie można utworzyć podpisu w czasie wykonywania poza kontekstem bieżącego zakresu i użyć tej sygnatury jako danych wejściowych do `FindMethod` .  
  
 `FindMethod` znajduje tylko metody, które zostały zdefiniowane bezpośrednio w klasie lub interfejsie; nie znaleziono dziedziczonych metod.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Reflection.MethodInfo>
- [IMetaDataImport — Interfejs](imetadataimport-interface.md)
- [IMetaDataImport2 — Interfejs](imetadataimport2-interface.md)
