---
title: ICorDebugSymbolProvider, interfejs
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: ff1f39be3d3db43f70cfa4a0711a3f42c180bc1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672087"
---
# <a name="icordebugsymbolprovider-interface"></a>ICorDebugSymbolProvider, interfejs

Dostarcza metody, których można użyć do pobrania informacji o symbolach debugowania.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetAssemblyImageBytes, metoda](icordebugsymbolprovider-getassemblyimagebytes-method.md)|Odczytuje dane z scalonego zestawu, uwzględniając względny adres wirtualny (RVA) w scalonym zestawie.|  
|[GetAssemblyImageMetadata, metoda](icordebugsymbolprovider-getassemblyimagemetadata-method.md)|Zwraca metadane z scalonego zestawu.|  
|[GetCodeRange, metoda](icordebugsymbolprovider-getcoderange-method.md)|Pobiera adres początkowy i rozmiar metody z przyznanym adresem wirtualnym (RVA) w metodzie.|  
|[GetInstanceFieldSymbols, metoda](icordebugsymbolprovider-getinstancefieldsymbols-method.md)|Pobiera symbole pól wystąpienia, które odpowiadają sygnaturze elementu TypeSpec.|  
|[GetMergedAssemblyRecords, metoda](icordebugsymbolprovider-getmergedassemblyrecords-method.md)|Pobiera rekordy symboli dla wszystkich scalonych zestawów.|  
|[GetMethodLocalSymbols, metoda](icordebugsymbolprovider-getmethodlocalsymbols-method.md)|Pobiera symbole lokalne metody z uwzględnieniem względnego adresu wirtualnego (RVA) tej metody.|  
|[GetMethodParameterSymbols, metoda](icordebugsymbolprovider-getmethodparametersymbols-method.md)|Pobiera symbole parametrów metody z uwzględnieniem względnego adresu wirtualnego (RVA) tej metody.|  
|[GetMethodProps — Metoda](icordebugsymbolprovider-getmethodprops-method.md)|Zwraca informacje o właściwościach metody, takich jak token metadanych metody i informacje o jego ogólnych parametrach, w którym znajduje się względny adres wirtualny (RVA) w tej metodzie.|  
|[GetObjectSize, metoda](icordebugsymbolprovider-getobjectsize-method.md)|Zwraca rozmiar obiektu na podstawie jego podpisu elementu TypeSpec.|  
|[GetStaticFieldSymbols, metoda](icordebugsymbolprovider-getstaticfieldsymbols-method.md)|Pobiera symbole pól statycznych, które odpowiadają sygnaturze elementu TypeSpec.|  
|[GetTypeProps, metoda](icordebugsymbolprovider-gettypeprops-method.md)|Zwraca informacje o właściwościach typu, takich jak liczba podpisów jego parametrów ogólnych, z uwzględnieniem względnego adresu wirtualnego (RVA) w tabeli jednoelementowej.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ten interfejs jest dostępny tylko dla .NET Native. W przypadku zaimplementowania tego interfejsu dla scenariuszy ICorDebug poza .NET Native, środowisko uruchomieniowe języka wspólnego zignoruje ten interfejs.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
