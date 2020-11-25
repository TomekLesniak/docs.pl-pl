---
title: CompareAssemblyIdentity — Funkcja
ms.date: 03/30/2017
api_name:
- CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CompareAssemblyIdentity
helpviewer_keywords:
- CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type:
- apiref
ms.openlocfilehash: da32ce6a40378a6f88cf71bd7707be2079d71068
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717601"
---
# <a name="compareassemblyidentity-function"></a>CompareAssemblyIdentity — Funkcja

Porównuje dwie tożsamości zestawów, aby określić, czy są one równoważne.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a>Parametry  

 `pwzAssemblyIdentity1`  
 podczas Tożsamość tekstowa pierwszego zestawu w porównaniu.  
  
 `fUnified1`  
 podczas Flaga logiczna wskazująca, że nie jest to określone przez użytkownika `pwzAssemblyIdentity1` .  
  
 `pwzAssemblyIdentity2`  
 podczas Tożsamość tekstowa drugiego zestawu w porównaniu.  
  
 `fUnified2`  
 podczas Flaga logiczna wskazująca, że nie jest to określone przez użytkownika `pwzAssemblyIdentity2` .  
  
 `pfEquivalent`  
 określoną Flaga logiczna wskazująca, czy dwa zestawy są równoważne.  
  
 `pResult`  
 określoną Wyliczenie [AssemblyComparisonResult —](assemblycomparisonresult-enumeration.md) , które zawiera szczegółowe informacje na temat porównania.  
  
## <a name="return-value"></a>Wartość zwracana  

 `pfEquivalent` Zwraca wartość logiczną wskazującą, czy dwa zestawy są równoważne. `pResult` zwraca jedną z `AssemblyComparisonResult` wartości, aby bardziej szczegółowo przyczynić się do wartości `pfEquivalent` .  
  
## <a name="remarks"></a>Uwagi  

 `CompareAssemblyIdentity` sprawdza `pwzAssemblyIdentity1` , czy i `pwzAssemblyIdentity2` są równoważne. `pfEquivalent` jest ustawiony na `true` co najmniej jeden z następujących warunków:  
  
- Dwie tożsamości zestawów są równoważne. W przypadku zestawów o silnych nazwach wartość równoważności wymaga, aby nazwa zestawu, wersja, token klucza publicznego i kultura była taka sama. W przypadku po prostu nazwane zestawy równoważności wymagają dopasowania w nazwie zestawu i kulturze.  
  
- Obie tożsamości zestawów odnoszą się do zestawów, które są uruchamiane na .NET Framework. Ten warunek zwraca, `true` nawet jeśli numery wersji zestawu nie są zgodne.  
  
- Dwa zestawy nie są zestawami zarządzanymi, ale `fUnified1` lub `fUnified2` zostały ustawione na `true` .  
  
 `fUnified`Flaga wskazuje, że wszystkie numery wersji do numeru wersji silnie nazwanego zestawu są uważane za równoważne zestawowi o silnej nazwie. Na przykład, jeśli wartość jest równa `pwzAssemblyIndentity1` "". Assembly, Version = 3.0.0.0, Culture = neutral, PublicKeyToken =... "i wartość `fUnified1` is `true` , oznacza to, że wszystkie wersje zestawu elementów z wersji 0.0.0.0 do 3.0.0.0 powinny być traktowane jako równoważne. W takim przypadku, jeśli `pwzAssemblyIndentity2` odwołuje się do tego samego zestawu `pwzAssemblyIndentity1` , z tą różnicą, że ma niższy numer wersji, `pfEquivalent` jest ustawiony na `true` . Jeśli `pwzAssemblyIdentity2` odwołuje się do wyższego numeru wersji, `pfEquivalent` jest ustawiana tylko wtedy, `true` gdy wartość `fUnified2` jest `true` .  
  
 `pResult`Parametr zawiera szczegółowe informacje o tym, dlaczego te dwa zestawy są uważane za równoważne lub nierównoważne. Aby uzyskać więcej informacji, zobacz [AssemblyComparisonResult — Enumeration](assemblycomparisonresult-enumeration.md).  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Łączenie statycznych funkcji globalnych](fusion-global-static-functions.md)
- [AssemblyComparisonResult — Wyliczenie](assemblycomparisonresult-enumeration.md)
