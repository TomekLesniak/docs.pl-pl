---
title: IMetaDataEmit2 — Interfejs
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
ms.openlocfilehash: b8ad159dace734c343297b256092162f17ab829b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726486"
---
# <a name="imetadataemit2-interface"></a>IMetaDataEmit2 — Interfejs

Rozszerza interfejs [IMetaDataEmit](imetadataemit-interface.md) przede wszystkim, aby zapewnić możliwość pracy z typami ogólnymi.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[DefineGenericParam, metoda](imetadataemit2-definegenericparam-method.md)|Tworzy definicję parametru typu ogólnego i pobiera token do tego parametru typu ogólnego.|  
|[DefineMethodSpec, metoda](imetadataemit2-definemethodspec-method.md)|Tworzy wystąpienie ogólne metody i pobiera token do definicji.|  
|[GetDeltaSaveSize, metoda](imetadataemit2-getdeltasavesize-method.md)|Pobiera wartość wskazującą różnicę rozmiaru danych, które są wymagane do wyrażenia zmian w bieżącej sesji Edit-and-Continue.|  
|[ResetENCLog, metoda](imetadataemit2-resetenclog-method.md)|Resetuje dziennik Edytuj i Kontynuuj i uruchamia nową sesję.|  
|[SaveDelta, metoda](imetadataemit2-savedelta-method.md)|Zapisuje zmiany z bieżącej sesji Edit-and-Continue do określonego pliku.|  
|[SaveDeltaToMemory, metoda](imetadataemit2-savedeltatomemory-method.md)|Zapisuje zmiany z bieżącej sesji edycji i kontynuowania w pamięci.|  
|[SaveDeltaToStream, metoda](imetadataemit2-savedeltatostream-method.md)|Zapisuje zmiany z bieżącej sesji Edit-and-Continue do określonego strumienia.|  
|[SetGenericParamProps, metoda](imetadataemit2-setgenericparamprops-method.md)|Ustawia wartości właściwości dla definicji parametru generycznego, do której odwołuje się określony token.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy metadanych](metadata-interfaces.md)
- [IMetaDataEmit — Interfejs](imetadataemit-interface.md)
