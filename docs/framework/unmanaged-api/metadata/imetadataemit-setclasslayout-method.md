---
title: IMetaDataEmit::SetClassLayout — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
ms.openlocfilehash: ee10907fb7f5d90db1bdce845272cd3de38e35a6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718699"
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout — Metoda

Uzupełnia układ pól dla klasy, która została zdefiniowana przez poprzednie wywołanie [metody DefineTypeDef —](imetadataemit-definetypedef-method.md).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a>Parametry  

 `td`  
 podczas `mdTypeDef` Token określający klasę, która ma zostać ustanowiona.  
  
 `dwPackSize`  
 podczas Rozmiar pakowania: 1, 2, 4, 8 lub 16 bajtów. Rozmiar pakowania to liczba bajtów między sąsiednimi polami.  
  
 `rFieldOffsets`  
 podczas Tablica struktur [COR_FIELD_OFFSET](cor-field-offset-structure.md) , z których każdy określa pole klasy i przesunięcie pola w klasie. Przerwij tablicę za pomocą `mdTokenNil` .  
  
 `ulClassSize`  
 podczas Rozmiar klasy w bajtach.  
  
## <a name="remarks"></a>Uwagi  

 Klasa jest początkowo definiowana przez wywołanie metody [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md) i określenie jednego z trzech układów dla pól klasy: automatyczne, sekwencyjne lub jawne. Zwykle należy używać automatycznego układu i pozwolić, aby środowisko uruchomieniowe było najlepszym sposobem ułożenia pól.  
  
 Jednakże można chcieć, aby pola zostały określone zgodnie z rozmieszczeniem, które jest używane w kodzie niezarządzanym. W takim przypadku wybierz Układ sekwencyjny lub jawny i Wywołaj, `SetClassLayout` Aby zakończyć układ pól:  
  
- Układ sekwencyjny: Określ rozmiar pakowania. Pole jest wyrównane do rozmiaru naturalnego lub rozmiaru pakowania, w zależności od tego, czy jest to mniejsze przesunięcie pola. Ustaw wartość `rFieldOffsets` i `ulClassSize` na zero.  
  
- Układ jawny: Określ przesunięcie każdego pola lub Określ rozmiar klasy oraz rozmiar pakowania.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IMetaDataEmit — Interfejs](imetadataemit-interface.md)
- [IMetaDataEmit2 — Interfejs](imetadataemit2-interface.md)
